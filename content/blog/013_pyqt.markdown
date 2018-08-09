Tags: Python
Title: Getting started with PyQt
Slug: getting-started-with-pyqt
Date: 2012-12-06 20:31:00
updated: 2012-12-07 20:50:00
Summary: I decided to have a go at producing a GUI for my risk calculation tool Impact. I chose to use PyQt4, and found a useful set of tutorials to get to grips with the toolkit. So far I have been able to design a simple GUI and run it from my main program. I am just beginning to connect widgets in the GUI to useful methods in the existing code.

A few weeks ago I started to look at the code I had written for
[Impact]({filename}005_introducing_impact.markdown), my
long-term project aimed at calculating third party risk. I hadn't worked on it
for several months, so wanted to get an idea of where I had left it. As a
result of this, and wanting to get stuck into writing some code again, I
decided to learn about creating a graphical user interface (GUI) for the program.

##Why a GUI?
My program so far has been used through the command line. I tried to make it as
flexible as possible, so it can be run with command line options for specifying
modelling parameters, a configuration file could be loaded instead, or the user
can be asked to specify each parameter. I quite like what I have done with it
so far, but at some point I would like to be able to demonstrate my work to
other people.

Whilst opening up a command line and running python would
adequately demonstrate the software, some people would see that as too
complicated. Especially when the only command line they are likely to see is by
running `cmd.exe`. If, instead I could open an executable file and show a
window with a clear idea of what to do, I might get a better response.

The other reason for wanting to produce a GUI is that, although I tried to do
something like that the last time I tried to write code in anger, it never got
anywhere. I really wanted to see what could be done, and how simple (or
complex) it is.

##Which toolkit?
When I decided to learn about GUIs, I had two toolkits in mind:

 - [PyGTK](http://www.pygtk.org "PyGTK")
 - [PyQt](http://www.riverbankcomputing.co.uk/software/pyqt/intro "PyQt")

I had previously looked at PyGTK and designing an interface using
[Glade](http://glade.gnome.org "Glade"). I never got to the stage of linking an
interface design to actual working code, but I learned a bit about laying out
an interface using widgets and containers.

This time around, knowing that I wanted to be able to use the finished product
on Linux and Windows machines, I did a very brief bit of internet research. On
the whole, it seemed that PyQt was most recommended. I decided to try it,
thinking I could always start again with PyGTK if I didn't get on well.

##Learning to use PyQt

Whilst I was still recovering from my surgery, I spent little portions of time running through
[tutorials for PyQt4](http://zetcode.com/tutorials/pyqt4 "ZetCode PyQT4 tutorials") that I found at [Zetcode](http://zetcode.com "ZetCode"). In general, it all seemed fairly straightforward. I tried to understand the code in the examples as much as possible; the [PyQt Class Reference](http://www.riverbankcomputing.com/static/Docs/PyQt4/html/classes.html "PyQt Class Reference") was helpful in this respect, but unfortunately at this time a lot of the documentation still contains the C++ code fragments that are used to document the underlying [Qt](http://qt.digia.com/ "Qt") framework.

After typing out a lot of different examples of using widgets, signals and
slots and trying various layouts, I wanted to start designing a basic GUI for
my own code. Rather than type out the location of every widget, I did this
using the tool supplied with Qt, [Qt
Designer](http://doc.qt.digia.com/qt/designer-manual.html "Qt Designer Manual").
With a simple design saved, I needed to find out how to actually use this
design with my program. Some internet searches later, I found a [useful
example](http://lionel.textmalaysia.com/a-simple-tutorial-on-gui-programming-using-qt-designer-with-pyqt4.html
"GUI programming using Qt Designer with PyQt4") that cleared up the confusion I
had.

The output from Qt Designer needs to be converted from XML into Python source.
PyQt includes a utility called `pyuic4` that generates Python code from the
`.ui` file produced by Qt Designer.

##Connecting the pieces

In order to incorporate my newly-designed GUI into the existing code, I had to
edit the file that previously handled the command line input and then ran the
actual calculations. To get started I
just commented out the previous `main()` function and wrote a new one. As I
found later, the PyQt site has [documentation about using the generated Python
code](http://www.riverbankcomputing.com/static/Docs/PyQt4/html/designer.html#using-the-generated-code
"Using the generated code"). Basically, the generated code is a module that contains a class for
the object designed in Qt Designer. By importing that class, an instance can be
created and all the widgets set up. The various widgets, such as labels,
buttons and text edit boxes can then be accessed for use by the program.

I created a wrapper for the main window, in which I then set up the widgets:

    :::python
    from PyQt4 import QtCore, QtGui
    from basic_prob_ui import Ui_MainWindow

    class MainWindow(QtGui.QMainWindow):
        def __init__(self, parent=None):
            QtGui.QWidget.__init__(self, parent)
            self.ui = Ui_MainWindow()
            self.ui.setupUi(self)

Ui_MainWindow is the module generated by `pyuic`. All of its widgets can now be
accessed by using `self.ui.btn1` or similar. As I develop the GUI, I will need
the code to respond to triggers, such as button clicks or text entry. At the
moment I am experimenting with using methods as part of the MainWindow class to
do that. It has been relatively straightforward so far. If I want to perform a
calculation to calculate probability when a button is clicked, I can write
this:

    :::python
    self.ui.btn_calculate.clicked.connect(self.calculate_probability)

The `calculate_probability` method can then perform the calculation and return
the result, perhaps by updating a label widget.

My new
`main()` function looks like this:

    :::python
    def main():
        application = QtGui.QApplication(sys.argv)
        window = MainWindow()
        window.show()
        sys.exit(application.exec_())
        application.setMainWidget(window)

The `MainWindow` class is instantiated and instructed to show the window, and
the program simply runs.

##Summary
My most recent coding adventures have been focused around GUIs. It has given me
a reintroduction to the code I have been writing in the last year, and I have
had some success in producing a basic GUI.

After choosing to try PyQt4, I benefited a lot from the tutorials and
documentation I managed to find. The trickiest bit so far was working out how
to interact with the GUI I had designed from the existing code for my program.
After working that out (with the help of more useful documentation and blog
posts) I was able to begin connecting widgets in the GUI to methods in my code.
I don't have much of a useful program so far, but I am pleased with my progress
to date.
