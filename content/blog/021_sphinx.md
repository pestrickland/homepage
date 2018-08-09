title: Using Sphinx to build a Logbook
slug: sphinx-logbook
summary: In this post I write about using Sphinx to build my logbook into a set of HTML pages. On Windows I use the Anaconda distribution to provide a Python environment, and it also includes Sphinx as standard. I'd like to use Sphinx to produce a new handbook for our day-to-day work, and perhaps learn how to customise the Sphinx theme too.
tags: work, python
date: 20140628

In my [last post]({filename}020_sublime.rst "Sublime Text in a Windows Environment") I wrote about using Sublime Text to write a logbook of activities at work. This time I'm going to quickly explain how I build that into a local website using [Sphinx](http://sphinx-doc.org/ "Sphinx documentation generator").

## Why Sphinx?

I first started using Sphinx to build documentation for my slowly developing [WIAT]({filename}016_airspeed_converter.markdown "Simple Airspeed Converter") software package. With it, I could write comprehensive docstrings in my code and have the entire package automatically documented as HTML among other formats.

Sphinx is widely used for Python documentation and once I got started using it, it seemed like a good tool to build my logbook as well, rather than learning another.

## Installing Sphinx in Windows

As I wrote in my last post, installing non-corporate software is more difficult than it used to be. Fortunately, most Python software can still be installed. Even better, however, is installing [Anaconda](https://store.continuum.io/cshop/anaconda/ "Anaconda Scientific Python Distribution"), which produces a locally installed Python environment that includes almost 200 packages, including Sphinx.

Installing Sphinx, therefore, was simply a matter of installing Anaconda. Doing so adds Python to the Windows environment path, so the system will recognise `python` as an executable program.

## Layout

I use a chronological structure for my logbook, not differentiating between individual projects. It reflects the way I take notes manually and is basically just a diary.

Each week has its own reStructuredText file, and within that the structure is divided into days and topics.

Sphinx uses an index file to structure a table of contents, so mine might look like this:

    :::rst
    My Work Log
    ===========
    This is the index of my work log.

    .. Table of contents.
    .. toctree::
        :maxdepth: 2
        2013
        2014/201401
        20140203
        20140210
        20140217
        glossary

    Index
    =====
    * :ref:`genindex`
    * :ref:`search`

Once a month is complete, I produce a sub-index of the weeks in that month (such as `201401`), and after a year these go into a folder for the whole year. Meanwhile, the weeks of the current month are listed directly in the index file.

## Building the pages

When you run the `sphinx-quickstart` script, you can specify that Makefiles are produced (a batch file in the case of Windows). The idea then is that all you have to do is run `make html` on a command line to build the set of HTML files.

Using Sublime Text, it's possible to simplify that by using a [build system](http://sublime-text-unofficial-documentation.readthedocs.org/en/latest/reference/build_systems.html "Sublime Text build systems"). Build systems allow you to specify a series of commands to be executed from within Sublime Text itself.

I used to simply run `make html` as a build system, but after breaking it somehow, I invoke the Sphinx command directly. Build systems are written in JSON, and look something like this:

    :::JSON
    {
        "name": "Build work log",
        "working_dir": "C:\\Users\\pestrickland\\work_log",
        "cmd": ["sphinx-build.bat",
                "-b",
                "html",
                "-d",
                "_build/doctrees",
                ".",
                "_build/html"],
    }

## Future improvements and other applications

### Automation

The system I described has worked well for me so far, but it is still quite manual. I still create a new file every week and populate it with date information. And I still manually update my index file and move files around into month and year folders.

Eventually I would like to automate the majority of this process, so that building the latest logbook each week also moves files around and updates the index where necessary.

### A new theme

Sphinx supports theming, a nice example of which is shown on [Read the docs](http://sublime-text-unofficial-documentation.readthedocs.org/en/latest/index.html "Unofficial Sublime Text documentation"). So far I have only used one of the default themes, but it would be nice to customise the look and feel of my logbook, to make it feel more *like mine*.

### An online handbook

At work we often talk about producing a handbook of our internal processes, procedures and methods to estimating effort, assessing systems and writing reports. But not much happens beyond that talk.

A few years ago I started running a local MediaWiki site that I wanted to become a handbook. It proved very useful, but more of an evidence database than a handbook. It was also difficult to share as it was not installed onto the corporate network and wikis are not in favour with the IT decision-makers.

Using Sphinx could provide a simpler manual. Source content could be written and shared as with any other document, and the whole thing could then be built into a set of HTML pages, a single HTML file or even a PDF document. It's something that I haven't thought through in much detail so far, but I think it might be worth a shot.
