Tags: Python
Title: Try-Except or If-Else Statements in Python?
Slug: try-except-in-python
Date: 2012-08-13 21:35:00
updated: 2012-08-13 21:35:00
Summary: After reading a post at paltman.com that tested the speed of try-except and if-else statements in Python, I repeated the test using the timeit module. The test attempts to get a dictionary key in cases where the key does and doesn't exist. The try-except statement simply tries to retrieve the key from the dictionary, whilst the if-else statement uses the has_key() method. The results are similar to the previous work, and the conclusions remain the same. If the key is likely to exist, try-except statements offer a slight advantage. If the key is unlikely to exist, if-else offers a marked improvement.

During my free time, I have been writing and rewriting more code for my ongoing
[Monte Carlo simulation project](/blog/2012/05/third-party-risk-3 "Introducing Impact").
Lately I have been including more and more error handling. I could probably have
avoided it -- I am not expecting the code to be used outside of my control --
but as my code became more complex, I found it useful if only for my own
debugging work.

Since I was writing more code to handle errors, I decided to think a bit more
carefully about it. One of the questions I had was whether it was preferable to
use ``try...except``, or ``if...else`` statements for controlling the flow of
the code. I was mainly concerned with what was deemed the 'correct' way to write
code, but during my research I also started thinking about whether there were
any speed benefits from one way over the other. In this post I discuss the
performance of the two statements.

##The tests
Whilst I was searching for guidance on which types of statement were deemed
preferable, I found [an article by Patrick
Altman](http://paltman.com/2008/01/18/try-except-performance-in-python-a-simple-test
"Try/Except Performance in Python: A Simple Test").[^1] The code tested whether a
dictionary element existed or not. Four methods of testing for this were
written:

* Try/Except with any exception passed
* Try/Except with an exception *e* being instantiated but not raised
* If/Else
* If Not/Else

The code was iterated 1000, 100,000 and 1000,000 times, and the system time was
used to indicate how long each test took. Each test was run for keys that did
and didn't exist.

The results[^1] showed that there was a speed advantage from using `if...else`
statements (with `has_key()` in this case) where the key didn't exist. Where the
key did exist, the `try...except` statements were faster.

##Using timeit
One of the problems with using the system time for timing small blocks of code
is well described in *Dive into Python*[^2], a useful guide to programming
with Python. In short, there are so many processes that could be running when
you try to time a piece of code that it is unreliable to just use the clock.

Python comes with a timing framework called `timeit`, and I decided to use it
to time the tests described above. In order to use Altman's code with
`timeit`, I simply took the core statements from each function, discarding the
*iterations* argument and the related `for` loop. This is simply because
`timeit` by default performs 1000,000 iterations of the code passed to it.

The modified code looks like this:

    :::python3
    # Key does not exist.
    def with_try():
        d = {'somekey': 123}
        try:
            get = d['notexist']
        except:
            pass

    def with_try_exc():
        d = {'somekey': 123}
        try:
            get = d['notexist']
        except Exception as e:
            pass

    def with_if():
        d = {'somekey': 123}
        if d.has_key('notexist'):
            pass
        else:
            pass

    def with_if_not():
        d = {'somekey': 123}
        if not d.has_key('notexist'):
            pass
        else:
            pass

    # Key exists.
    def exists_with_try():
        d = {'somekey': 123}
        try:
            get = d['somekey']
        except:
            pass

    def exists_with_try_exc():
        d = {'somekey': 123}
        try:
           get = d['somekey']
        except Exception as e:
            pass

    def exists_with_if():
        d = {'somekey': 123}
        if d.has_key('somekey'):
            pass
        else:
            pass

    def exists_with_if_not():
        d = {'somekey': 123}
        if not d.has_key('somekey'):
            pass
        else:
            pass

To run the tests, I created a second script that simply called the `Timer.repeat` method, using
the function being tested as an argument. `repeat` just runs `timeit` multiple
times on the piece of code. I then took the minimum result as my answer:

    :::python3
    import timeit

    t1 = timeit.Timer("statements.with_try()", "import statements")
    t1_time = t1.repeat()
    t2 = timeit.Timer("statements.with_try_exc()", "import statements")
    t2_time = t2.repeat()
    t3 = timeit.Timer("statements.with_if()", "import statements")
    t3_time = t3.repeat()
    t4 = timeit.Timer("statements.with_if_not()", "import statements")
    t4_time = t4.repeat()
    t5 = timeit.Timer("statements.exists_with_try()", "import statements")
    t5_time = t5.repeat()
    t6 = timeit.Timer("statements.exists_with_try_exc()", "import statements")
    t6_time = t6.repeat()
    t7 = timeit.Timer("statements.exists_with_if()", "import statements")
    t7_time = t7.repeat()
    t8 = timeit.Timer("statements.exists_with_if_not()", "import statements")
    t8_time = t8.repeat()

    print("The case where the key does not exist:")
    print("with_try (%0.3f ms)" % min(t1_time) * 1000))
    print("with_try_exc (%0.3f ms)" % min(t2_time) * 1000))
    print("with_if (%0.3f ms)" % min(t3_time) * 1000))
    print("with_if_not (%0.3f ms)" % min(t4_time) * 1000))
    print("The case where the key does exist:")
    print("with_try (%0.3f ms)" % min(t5_time) * 1000))
    print("with_try_exc (%0.3f ms)" % min(t6_time) * 1000))
    print("with_if (%0.3f ms)" % min(t7_time) * 1000))
    print("with_if_not (%0.3f ms)" % min(t8_time) * 1000))

##Results
###Keys that don't exist
    :::python3
    with_try (2473.079 ms)
    with_try_exc (2813.476 ms)
    with_if (507.681 ms)
    with_if_not (527.287 ms)

###Keys that do exist:
    :::python3
    exists_with_try (415.812 ms)
    exists_with_try_exc (413.473 ms)
    exists_with_if (514.404 ms)
    exists_with_if_not (531.845 ms)

The results are similar to those obtained by Altman.[^1] Where a key doesn't
exist, it is faster to use the `if...else` statement with the `has_key()`
function than to use `try...except` to attempt to get the key. Whether a
named exception is created or not has less of an effect on the speed than was
seen in the original test, but I don't know why this would be the case.

If the key exists, using `try...except` is faster than `if...else`, but the
difference is not large.

My conclusion is very similar to that of the original test: if you are
expecting elements to not exist, using `if...else` with `has_key()` appears to
be faster. `try...except` is slightly more suited to cases where the key is
likely to exist, but not by much.

In my own code I tend to use `if...else` by default. Not because of the speed
benefits, but as a result of learning to write code. It took me a while to find
out that `try...except` existed and how it could be used. However, I do find
myself using it more frequently and find it quite useful.

In a future post I plan to write a bit about the virtues of writing error handling code from the start, rather than adding it later once things have started to go wrong. Before that though, I need to get better at writing error handling code...

##References
[^1]: Altman, P.  *Try / Except Performance in Python: A Simple Test*,
available at
<http://paltman.com/2008/01/18/try-except-performance-in-python-a-simple-test>
[accessed 11 August 2012].
[^2]: Pilgrim, M. *Dive into Python*, 20 May 2004, available at
<http://www.diveintopython.net> [accessed 13 August 2012].

