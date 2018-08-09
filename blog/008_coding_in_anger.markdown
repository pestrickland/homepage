Tags: Python
Title: Coding in Anger
Slug: coding-in-anger
Date: 2012-07-14 20:42:00
updated: 2013-05-18 12:30:00
Summary: I recently wrote my first Python script that was useful in my day job.It took a while to write and is horribly messy, but it does what I needed it to do. Based on this success, I plan to write more code to help solve simple problems. Developing small programs in this way should allow me to put together a toolbox of useful code that will improve my assessment ability at work.

Recently I used Python 'in anger' at work for the first time. I needed to
plot some basic trajectories and perform a few distance-time calculations.
It was something that was well within the capabilities of the default program
of choice where I work (MS Excel), but would have resulted in some unwieldy
spreadsheets and lots of nested conditional statements.

Up until this problem came about, my Python projects had purely been for my own
interest and to help learn the language. When this problem at work came along,
however, I thought I could probably make a reasonable job of it using Python,
NumPy and matplotlib.

##Messy, but functional (and fun)

I actually ended up spending about a day of my weekend on the bulk of the code,
so it wasn't exactly a speedy piece of work. In addition, the code I have ended
up with is also 'yuck', a technical term I have decided to use for code that
even I could write to be neater and more efficient. It is code that -- if I
started again -- I would write entirely differently. I would make it more
generic so that it (or elements of it) could be reused elsewhere. However,
despite it being messy and taking a long time, I did get it to work -- I was
able to produce plots of the trajectories I was interested in, and they look an
awful lot nicer than I would have ended up with by using Excel. I was also able
to generate multiple plots at once, save them as PNG and SVG files and include
them in my report. I was very pleased with myself.

After achieving this feat, I began to wonder when it will be possible for me to
write code on a regular basis that takes no longer than getting the result
using another method, for instance Excel. I think I have just about surpassed
Excel in terms of the functionality I can command, but Excel would still win
when it comes to the time taken to produce results. It's not half as fun as
writing Python though!

##Bulding a toolkit

With this piece of code under my belt, I decided to make an effort to write
more code for relatively simple problems like this one. I don't expect
that I will make coding a significant part of my job, but as an engineer I view
the ability to write a quick and dirty script as a very useful skill to have.

Another decision I made was to put all of my coding efforts under version
control. I have already been using [Bazaar](http://bazaar.canonical.com/en/) for my
Monte Carlo simulation software, and I
also use Bazaar for this blog. Given that there is not much overhead for doing
so, having my plotting script (and future programs) under version control will
allow me to keep track of how far I got with the code, and may even encourage me
to keep developing them.
