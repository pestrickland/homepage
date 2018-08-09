Tags: Cycling, Python
Title: Summer and Autumn Update
Slug: summer-autumn-update
Summary: I have had a fairly busy six months, including travelling to Spain and California, cycling and working on a number of personal projects. I have been interested in robotics, quadcopters and have enjoyed using IPython Notebook to document my learning and development.
Date: 2013-11-24 13:30:00
updated: 2013-11-24 15:10:00

Over the last six months I've been fairly busy with work, but also with a number of personal projects. I've been to Spain and California, and have continued to cycle the roads of Wiltshire. However, there hasn't been much that I considered worthy of writing about here.

This entry will summarise what I've been up to and link to some of my project work.

##Cycling

When the weather was warmer I cycled quite a lot. My fitness improved to the point where I was as fit as I was at my peak last year, before falling ill. So far this year I have ridden 1860 km, with July being my best month at 543 km.
And with an overall average speed of 27.2 km/h I have been quite pleased with
myself.

The approach of winter has made motivation a problem for continued cycling, but
I have noticed a correlation between the amount of hard exercise and my general
well-being. As that in itself has been a big challenge since I was in hospital,
I should try to make an effort to keep physically active throughout the winter.

##My travels

In August I travelled to the north of Spain with my parents. We stayed in the
city of Pamplona, famous for its bull run, and ventured out into the Pyrenees
mountains for day trips. Despite our car suffering a double puncture at the top
of a mountain somewhere on the French-Spanish border, it was a very nice week.

Between September and October I spent three weeks in the USA with work. We were
based in the Mojave desert but managed to spend our weekends away. We went to
San Francisco for three days and visited Las Vegas for two days. For me, San
Francisco was the definite highlight and I am keen to go back there at some
point in the future.

##Personal projects

Several projects have occupied my free time recently, and probably too many to
progress if I'm honest.

###Robotics

In the past few years I have been fascinated by the idea of an autonomous
aircraft, a UAV or drone as commonly known. Although they can now be purchased
and used almost straight away, my interest lay deeper. I always want to know
*how* something works and why it was designed that way, and I thought I could
embark on a journey to learn exactly that. Aircraft are expensive to learn
with, however, as crashes are likely and costly, not to mention dangerous. I
therefore decided I should start with a ground-based robot.

I quickly purchased some hardware and started programming an Arduino to control
my robot. It was refreshing to include hardware into my projects as a lot of my
previous work had been exclusively software.

Once I get a robot built that can successfully navigate and avoid obstacles,
there are several potential avenues to explore. Ultimately my goal is to have a
number of vehicles that can manoeuvre autonomously but that have the ability to
build a mesh network and transfer data between themselves and some sort of base
station. The application I had in mind was to explore a disaster area -- many
low-cost vehicles could be sent to explore and maybe map a dangerous area. And
they could carry a payload of sensors to determine different sorts of hazards.
It might also be possible for them to construct a temporary communications
network to augment damaged or overwhelmed infrastructure.

I have started to document my ideas and Arduino source code on GitHub,
accessible [here](http://github.com/pestrickland/robot "GitHub robot repository").

###Quadcopters

As the robot project developed, the idea for flight didn't go away. I bought a
cheap micro-quadcopter and had a great time flying it around the office. This
inspired me to build a bigger one, and that's what I did in October. It was
built using off-the-shelf components and I'm still trying to tune the control
system, but it is very fun to fly provided I have enough space.

Rather than just build and fly a quadcopter, I've also been trying to
understand how it is controlled, and refresh my poor knowledge of control
theory in the process. And I also have an aspiration to link a future
autonomous quadcopter to my ground-based robots to further increase the
possibilities of disaster area surveying and sampling.

###IPython Notebook

I have been completely won over by the
[IPython Notebook](http://ipython.org/notebook.html "IPython Notebook") concept
recently. All of my learning and development now takes place within a notebook,
and I store most of them on [GitHub](http://github.com/pestrickland/notebooks
"GitHub notebook repository"). Together with Python libraries such as NumPy,
SciPy and SymPy, the support of LaTeX and the ability to view notebooks in the
browser using [nbviewer](http://nbviewer.ipython.org "IPython Notebook Viewer"),
I can document my work with a mixture of formatted text and equations, Python
example code and charts of results.
