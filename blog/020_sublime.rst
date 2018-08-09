#####################################
Sublime Text in a Windows Environment
#####################################

:slug: sublime-text-at-work
:summary: I use Sublime Text 3 at work to keep a record of my day. I love its minimal interface and its features. When I write using reStructuredText I get great syntax highlighting, and fortunately I can run it on my locked-down corporate laptop.
:tags: Work
:date: 20140614

.. |ST| replace:: Sublime Text

For over a year I've been using `Sublime Text`_ to record my workdays. I love its clean minimal interface. I love the fact it has a Python interpreter built in, that it can be customised and extended. And fortunately, I can run it on my locked-down corporate laptop.

.. _Sublime Text: http://www.sublimetext.com

Logbooks
========

When I started my job about six years ago, I was given some advice: *keep a logbook*. I started to do this by hand, but it soon got tiresome; trying to spend time at the end of every day writing what I'd done just wasn't appealing.

About 15 months ago I found out about the |ST| editor, and was intrigued by so many people raving about it. I downloaded a copy and started to use it. Soon enough it was my favourite text editor at home, and I also took it to work.

I don't know quite what it was about |ST|, but I started to enjoy typing notes a lot more than I used to. I went from only writing down notes at meetings to keeping a fairly comprehensive narrative of my day. After more than a year of doing this I have quite a useful record of my life at work.

What I love about using Sublime Text
====================================

No distractions
---------------

In a cluttered Windows/Office environment, the most refreshing part of |ST| is its distraction-free interface. Nothing but a small menu bar and your text, and you can even get rid of the menu if you want. It's *brilliant*. I sometimes now take my laptop to a meeting to take notes, and I split the screen so that I have notes at the top of the file and actions at the bottom. And there is nothing else to distract me.

Customisation
-------------

You can customise so much with |ST|. I spent more time than I'd like to admit searching for the "perfect" settings file, containing a good theme, great syntax highlighting and the best font. In the end I found `this article <http://piotr.banaszkiewicz.org/blog/2013/08/24/sublime-text-3-for-python-development/>`_ and based my own settings on that. (My own settings are available `here <https://gist.github.com/pestrickland/0e53a61f836fc87a25cd>`_.)

Plain text
----------

Text formatting distracts me when I type. If I opened a new Word document to write down some notes, I'd be likely to spend ages setting up some styles, or else I'd use a template that we use to produce technical reports (and then spend ages removing all the boilerplate pages).

When I use |ST| I write in reStructuredText_. For general text it is similar to plain text, with some syntax for headings, lists, and so on. It is quite readable as plain text, especially with a monospaced font. |ST| (with the right theme) highlights the syntax which makes the experience even better. reStructuredText is also used for `Sphinx Documentation`_ source files, which I use to build my logbook entries into a logical system.

.. _reStructuredText: http://docutils.sourceforge.net/rst.html
.. _Sphinx Documentation: http://sphinx-doc.org/

I can use it with Windows 7
---------------------------

The IT system where I work is Microsoft-based, and recently we had our laptops upgraded to Windows 7. Whilst that's a fairly unremarkable change for day-to-day work, the biggest problem for me was User Access Control -- I can no longer install a lot of software (or fonts!). Fortunately, |ST| is available as a portable version. This means that all I need to do is extract a zip file and I can run the software directly -- everything is contained within one folder that can be put wherever I have permission.

For some reason, installing fonts now requires administrator privileges, and that meant that I couldn't install my monospaced font of choice: `Ubuntu Mono`_. Luckily the internet provided a workaround that allows me to install fonts as an ordinary user for the duration of my session. By including a batch file in my startup folder, all the fonts I want to use will be registered each time I start my laptop.

.. _Ubuntu Mono: http://font.ubuntu.com/
