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

### Changes to the methods

`getHeroes()` uses an `http.get()` method. With Firestore, we use the `valueChanges()` method on our list of heroes. Everything else can stay the same:

{{< highlight typescript >}}
// Get heroes from the server.
  getHeroes(): Observable<Hero[]> {
    return this.http.get<Hero[]>(this.heroesUrl)
      .pipe(
        tap(heroes => this.log('fetched heroes')),
        catchError(this.handleError('getHeroes', []))
      );
  }
  {{< / highlight >}}

Note, however, that the easy-to-use `valueChanges()` method only returns the basic data displayed. It gets more complicated when we try to access the document id.

