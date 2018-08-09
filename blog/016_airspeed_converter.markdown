Tags: Python
Title: A Simple Airspeed Converter Part 1
Slug: airspeed-converter-1
Summary: This article describes my experience at writing my first complete Python application. It consists of a module of code that is fully covered by unit tests, a GUI built using PyQt4 and it is packaged using cx_Freeze and compiled into an installer using Inno Setup. In the first article I write about the reasons for writing the program and my experience of writing the underlying code module. The next article will detail the GUI and packaging aspects.
Date: 2013-05-18 14:30:00
updated: 2013-05-18 14:53:00

The screenshot below shows the end result of my first "complete" programming project. It is a simple calculator that converts airspeeds between some commonly used units. I wrote all the code from scratch, and the module that contains the conversion code is the first I've written to be fully covered by unit tests. The module exists as the first code in my new toolkit, but I also managed to build the converter as a standalone application using cx_Freeze and Inno Setup, allowing it to be installed as a Windows application. The basic GUI is the first that I built with a decent understanding of how everything works, gained largely from reading *Rapid GUI Programming with Python and Qt*. [^3]

<figure>
<a href="/images/wiat_airspeed_01.png">
<img src="/images/wiat_airspeed_01_small.png" title="Simple GUI to convert airspeeds" alt="Airspeed Converter GUI">
</a>
<figcaption>
A simple GUI to convert airspeeds
</figcaption>
</figure>

In this article, I describe my reasons for the converter and how I set about writing the module. In part two I'll outline the process I used to build an application that can be installed on Windows without having to separately install the dependencies.

## The WIAT package
Following a few experiments using Python to help with my day job, such as the
[trajectory calculator](/blog/2012/07/14/coding-in-anger "Coding in Anger") I
wrote last year, I began to consider the idea of building a toolkit containing a
few useful tools and utilities.

A toolkit needs a name, and in the absence of anything more imaginative I came
up with the name of WIAT -- Weapons Integration Assessment Toolkit.

Since I hacked together the trajectory calculator in a horribly messy way, I
couldn't start my toolkit with code like that. I therefore decided to choose
something a bit more simple that I could produce relatively quickly, and also in
a more complete state than anything I've written so far. In addition, a tool
with a simple GUI would help me to continue learning PyQt4. Finally, I wanted to
be able to package my code so that I could simply install it on a Windows
computer without having to separately install Python and third party packages.
This would also make it easier to share with other people where I work.

## An airspeed converter

The speed of an aircraft can be represented in several different forms. For fast
jet aircraft, speed can be measured as
[true airspeed](http://en.wikipedia.org/wiki/True_airspeed "True airspeed on Wikipedia"),
[calibrated airspeed](http://en.wikipedia.org/wiki/Calibrated_airspeed "Calibrated airspeed on Wikipedia")
and as a [Mach number](http://en.wikipedia.org/wiki/Mach_number "Mach number on Wikipedia")
among others.

Each measurement is useful for different reasons, and there is often a need to
convert between them. Such conversions are non-linear, however, and additional
parameters such as temperature and altitude may need to be considered.

The first tool in my toolkit, therefore, would be an airspeed converter.
I would be able to develop a simple GUI that I could use to quickly perform
standard conversions, and I would also have a Python module that I could use in
future projects.

## Writing the module

For the purposes of this project, I wrote my own module to perform the required
calculations. However, a much more comprehensive package exists called
[AeroCalc](https://pypi.python.org/pypi/AeroCalc "AeroCalc on PyPI"). Whilst I
could have used that, I wanted to write everything myself this time.

### Atmosphere Model

A key feature of airspeed calculations is the atmosphere model. The model
represents the changes in temperature, pressure, density and so on at different
altitudes. Several models exist, but I chose to use the *US Standard Atmosphere,
1976* [^1]. Produced by NASA, it is available in the public domain.

The model consists of a number of equations that determine the change in
temperature with altitude, and from that several other parameters are derived.

I wrote this module by first writing the unit tests that I required my code to
pass. Correct values for each test were obtained from the look-up tables within
the atmosphere model.

To test my conversions between true and calibrated airspeed I used another NASA
document, *Measurement of Aircraft Speed and Altitude* [^2]

### Accuracy

One problem I encountered when writing unit tests was the changing level of
accuracy. Using look-up tables for reference values provides a limited level of
precision, typically 4 or 5 significant figures. Whilst this works for units
such as temperature, for others, such as dynamic pressure, there can be varying
levels of rounding errors to handle.

Fortunately the built-in `unittest` framework includes the [`assertAlmostEqual` method](http://docs.python.org/3.3/library/unittest.html#unittest.TestCase.assertAlmostEqual). This allows
the test to be specified to an acceptable level of accuracy.

## References
[^3]: Summerfield, M., *Rapid GUI Programming with Python and Qt*, Prentice Hall,
2008.
[^1]: NASA, *U.S. Standard Atmosphere, 1976*, available at
<http://www.everyspec.com/NASA/NASA-General/NASA_TM-X-74335_37294/>
[accessed 09 March 2013].
[^2]: NASA, *Measurement of Aircraft Speed and Altitude*, available at
<http://www1gtm.nasa.gov.speedera.net/centers/.../pdf/88377main_H-2044.pdf‎>
[accessed 17 March 2013].
