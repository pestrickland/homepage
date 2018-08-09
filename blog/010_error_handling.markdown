Tags: Python
Title: Handling Errors in Python
Slug: error-handling
Status: draft
Date: 2012-08-12 19:30:00
Summary: Blah.

##Why bother?
Error handling makes a lot of sense for computer programs. A program that is
written to only handle expected inputs has a higher chance of crashing if
something unexpected is fed into it. A crashed program is not only frustrating
to the user, but also harder to fix without a pointer in the right direction.
Error handling helps alleviate these problems.

The code I have written so far has only ever been used by me. All the source
code is stored locally, and whilst it is being written under the GNU General Public
Licence, I am not sufficiently happy with it to store it elsewhere at the
moment. There is therefore an argument that I don't need to bother with
handling incorrect inputs, because I could assume that I will always use the
program as I intended. However, that assumption is not particularly strong.

What started as a single file program now comprises of about a dozen files and
about 2000 lines of code. This is obviously not a big program by any means, but
it is *big enough* that being aware of everything the code is quite difficult.
That isn't a problem if I get it right every time. Unfortunately that is not
the case.

My first attempt at simplifying my debugging activity was to define exceptions
that indicated which part of the code wasn't working. For example, if I was
constructing a model with a population and three towns and something was
wrong with the `set_area` method of the `Town` class, I would get a message
along the lines of `Town: No town radius specified`. This proved very helpful,
and I have been trying to write error-handling code ever since.

##References
[^2]: ActiveState Code, *Benchmark code with the with statement (Python
recipe)*, available at
<http://code.activestate.com/recipes/577896-benchmark-code-with-the-with-statement>
[accessed 11 August 2012].
[^3]: Preshing on Programming, *Timing Your Code Using Python's "with"
Statement*, available at
<http://preshing.com/20110924/timing-your-code-using-pythons-with-statement>
[accessed 11 August 2012].
