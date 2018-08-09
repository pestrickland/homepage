Tags: Health and fitness, Python
Title: Summing up January
Slug: summing-up-january
Summary: January has been spent getting back up to speed with work and my projects. I have been gradually starting to exercise again, aiming to continue training indoors until I feel fit enough to cycle outside. I've also been rewriting my Impact code to use Python 3, and to try to be more object oriented. I've also been starting to adopt a more test driven development process to writing.
Date: 2013-02-02 11:29:00
updated: 2013-02-02 11:40:00

January has now been and gone, and without anything specific to write about, 
I thought I would summarise what I have spent my time on so far this year.

##Health and fitness
Since I had my surgery last September, I have been on the slow road to 
recovery. Although I am still not completely recovered, I can now go about my 
life without too much problem. Jaunuary saw my return to work full time, and
it's been a busy one too. It's been quite a tiring month in that respect, and
the end of each week has brought a sense of relief that I get to rest a bit
before the next working day starts.

Last year, I rode a total of 2,500 km. It was by far my most productive year in
terms of distance covered and height climbed, eclipsing the previous three
years combined. And yet I only rode for two thirds of the year, stopping
abruptly at the beginning of September.

During my time off work, I bought a turbo trainer, with the aim of using it to
aid my recovery. Towards the end of last year I rode a few hours on the
trainer, but it took a lot out of me. So far this year I have made a more
valiant effort, but still only managed 4 hours on the trainer, plus a couple of
gym sessions. Although not a great achievement, I was able to train without
feeling too exhausted afterwards, which is a small sign of progress. I even
reached the point of *enjoying* the feeling of completing an hour on the
trainer.

My aspiration for the next month or two is to continue training indoors until I
can comfortably manage about 5 hours a week. After that I should hopefully be
able to begin cycling to work again -- the weather should be a bit more
favourable by then as well, so that will be nice!

##Python
During my programming work this year, I've been trying to learn more about
programming in several areas, specifically:

* PyQt
* Unit testing
* Object Oriented Programming best practice

###PyQt
Before Christmas I was busy trying to knock out a GUI for some of my Impact
code. Using the PyQt toolkit, I managed to achieve this, and I even got as far
as building the GUI as a Windows executable. It was a messy process, however,
and during that time I decided that I really needed to learn more about what
was going on. I therefore purchased [*Rapid GUI Programming with Python and
Qt*](http://www.qtrac.eu/pyqtbook.html "Rapid GUI Programming with Python and
Qt at Qtrac Ltd.")
by Mark Summerfield, and spent several hours over the Christmas break reading
and learning. What struck me during that time was how much more I learned about
Python itself. In fact, I decided that pursuing a GUI application with my
existing code might be more difficult than if I tried to improve my non-GUI
code. I therefore began looking carefully at my code written to date, and 
promptly started to rewrite it. This sounds like quite a rash decision, but 
there were a couple of other factors to consider as well. 

I had always wanted to write my code for Python 3 from the beginning. At that
point though, [NumPy](http://numpy.scipy.org "NumPy") and 
[matplotlib](http://matplotlib.sourceforge.net "matplotlib") were only
available for Python 2.7. Towards the end of last year I noticed that both
packages now supported Python 3. My code could now be written for Python 3.

Simply porting my existing code to Python 3 was a viable option. There was
little to do except change sequences built using `xrange` to use `range`, and
check all my `print` statements were written as functions. 

When I looked through my code, it was not as decoupled as I would have liked it
to be. Since it had been written originally with a command line interface, I
had a lot of code that handled user inputs, raised warnings and had default
values to fall back on. Attempting to bolt on some GUI code didn't seem like
the most elegant solution. I therefore went back to the beginning and started
to write my modules from scratch. Currently I am still writing `model.py`, the
core of the Monte Carlo aspects of my program, but I am quite pleased with my
progress so far.

###Unit testing
During the rewriting of my code, [Packt Publishing](http://www.packtpub.com
"Packt Publishing") had a tempting offer for its ebooks. I took advantage of 
the offer and bought several books, among them [*Python
Testing*](http://www.packtpub.com/python-testing-beginners-guide/book) by Daniel
Arbuckle. This book helped guide me into the world of test driven development.
What I found particularly useful was being able to use the doctest module to
write tests. In a simple text file I could write down what I wanted my code to
do and how I wanted it to behave, providing code examples as I went. I could
then write the code to provide that functionality, and use the text file to
test that the code worked as I specified. 

I am now using the `unittest` module as well, and in some cases trying to use
`mock`, although I am struggling a bit the the latter. 

The subtleties of test driven development are probably lost on me, but as a
broad concept I quite like it. I don't think I will be able to work purely by
writing tests first, and writing code second, as it's too tempting to me to try a few
lines of code to prove a concept, rather than formally write what I want the
code to do. However, once I have an idea of what a particular method should do,
writing unit tests for that desired functionality does seem very useful.

###Object Oriented Programming
Another book from Packt, [*Python 3 Object Oriented
Programming*](http://www.packtpub.com/python-3-object-oriented-programming/book), 
has been provding me with a bit more insight into object oriented programming.
The `model` module in my code has always been based on the idea, but I am now
trying to rewrite it in such a way that as much code as possible is reusable. I
would like to be able to gradually build up a library of various tools for use
during my assessments, both at work and home, so being able to write code that
can be reused seems like a very good idea. 

##Summary
January has been a month of small amounts of progress, but in several areas.
I've certainly not been idle, but I could do with narrowing my focus a little
bit if I want to make any tangible progress with my projects. 
