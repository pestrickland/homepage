---
title: "Angular"
date: 2018-09-03T21:02:27+01:00
showDate: true
draft: true
tags: ["blog","story"]
---

Recently I've been trying to learn a bit about modern web app develop, and have therefore been writing a small application using Angular, based on the Heroes tutorial at angular.io.

Once I thought I'd understood the basic principles, I tried to convert the application to be able to connect to a Firebase Firestore database. It took a lot longer than I'd like to admit, but these notes hopefully explain what I needed to change to get it to work.

## Heroes Service

Fortunately, the tutorial explained how using separate components and services helps make the code more usable. In this case, keeping the HTTP functions contained within the `HeroService` class should mean that minimal changes are needed elsewhere in the project. *Should...*

### Setting up the class

We need to import the Firestore symbols from angularfire2. These should be able to replace the HTTP symbols used in the tutorial.

{{< highlight typescript >}}
import { AngularFirestore, AngularFirestoreCollection, AngularFirestoreDocument } from 'angularfire2/firestore'
{{< / highlight >}}

Rather than an `http` property, the constructor for our service class has an `AngularFirestore` private property injected into it as `db`.

The web API URL is no longer needed, but we define two variables that will contain our Firestore collection and individual documents.

The start of the service class therefore looks like this:

{{< highlight typescript >}}
@Injectable({ providedIn: 'root' })
export class HeroService {
    heroesList: AngularFirestoreCollection<Hero>;
    private heroDoc: AngularFirestoreDocument<Hero>;

    constructor(
        private messageService: MessageService,
        private db: AngularFirestore) {
            this.heroesList = this.db.collection('heroes');
        }
}
{{< / highlight >}}

## Getting a list of documents

`getHeroes()` uses an `http.get()` method. With Firestore, we use the `valueChanges()` method on our list of heroes. Everything else can stay the same:

{{< highlight typescript >}}
// Get heroes from the server.
  getHeroes(): Observable<Hero[]> {
    return this.heroesList.valueChanges()
      .pipe(
        tap(heroes => this.log('fetched heroes')),
        catchError(this.handleError('getHeroes', []))
      );
  }
  {{< / highlight >}}

Note, however, that the easy-to-use `valueChanges()` method only returns the basic data displayed. It gets more complicated when we try to access the document id.

## Adding documents

The method used in the Heroes tutorial looks like this:

{{< highlight typescript >}}
// POST: Add a new hero to the server.
  addhero(hero: Hero): Observable<Hero> {
    return this.http.post<Hero>(this.heroesUrl, hero, httpOptions)
      .pipe(
        tap((hero: Hero) => this.log(`Added hero with id=${hero.id}`)),
        catchError(this.handleError<Hero>('addHero'))
        );
  }
{{< / highlight }}

The `add` method in AngularFire2 is used instead of the `http.post` method. However, whilst `post` returns an Observable, `add` returns a Promise (when adding to a Firestore Collection). Since Promises cannot be subscribed to or piped, we need to use the `.then()` clause. In addition, since using `valueChanges()` only gives us access to basic data, we need to change the approach to log the id.

So it looks like this:

{{< highlight typescript >}}
addHero(hero: Hero): Promise<any> {
  const id = this.heroesList.createId();
  const name = hero.name;
  const hero: Hero = { id, name };
  return this.heroesList.doc(id).set(hero);
  .then(
      _ => this.log(`Added hero with id=${hero.id}`),
      catchError(this.handleError<any>('addHero'))
      );
  }
{{< / highlight >}}

This will work, but the id of the document will not be available for logging. In order to get the id, we need a different approach which we'll look at later.

## Getting a specific document

The Heroes tutorial uses an `http.get` method. 

{{< highlight typescript >}}
// GET hero by id. Will 404 if id not found.
  getHero(id: string): Observable<Hero> {
    const url = `${this.heroesUrl}/${id}`;
    return this.http.get<Hero>(url).pipe(
      tap(_ => this.log(`Fetched Hero id=${id}`)),
      catchError(this.handleError<Hero>(`getHero id=${id}`))
      );
  }
{{< / highlight >}}

We need to use `snapshotChanges()`. The `snapshotChanges()` method returns metadata along with the document. However, using it looks quite convoluted at first:

{{< highlight typescript >}}
getHeroes(id: string) {
  this.heroessList.snapshotChanges()
      .pipe(
        map(actions => actions.map( a => {
          const data = a.payload.doc.data() as Hero;
          const id = a.payload.doc.id;
          return { id, ...data };
        })))
{{< / highlight >}}

I'm not very experienced with Javascript/Typescript -- my only programming to date has been with Python. However, the `=>` operator defines an *arrow function* which is apparently similar to a lambda function. And in this case we seem to have two nested functions. Working from the inside out, we see:

{{< highlight typescript >}}
a => {
  const data = a.payload.doc.data() as Hero;
  const id = a.payload.doc.id;
  return { id, ...data };
  }
{{< / highlight >}}

Let's see if we can put this into a console.

