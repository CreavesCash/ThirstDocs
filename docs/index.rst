Welcome to Thirst Script
===========================

This is ThirstScript, my stupid little work-in-progress programming language.

QUICK CHANGELOG

**Version 1.0.0  27/03/2020**

Inital Lexer and Parser mostly done, statements "OUTPT", "INPUT" "IF" "THEN" "$VARIABLE"

INTRODUCTION
===========================
ThirstScript is my first attempt at creating a programming language. I am 14 years old, so manage your expectations.
I wanted to combine the ease of parsing with python, with programs like AutoHotKey. So that's what this is, really. A hot mess.

INSTALLATION
==============================
I'll put the installation stuff here when I put a proper thing. For now, clone the git repo.

EDITING ENVIRONMENT
===========================
At the moment, ThirstScript is only suitable for Windows computers. Sorry. If you have a multi-purpouse programming environment like Sublime Text, I would encourage you to use that. Save your files with the .thsc file ending and move on to `My First Script <https://thirstdocs.readthedocs.io/en/latest/#id1>`_. If not, you probably have notepad. Follow along the Notepad instructions below.

NOTEPAD AS AN EDITOR
===========================
If you wish to use notepad as an editor, create a notepad file called "Test.thsc". It will create a file called "Test.thsc.exe". Rename it to "Test.thsc". If a popup comes up asking if you're sure, say yes. I hate those. Hooray you did it now move on to **My first script**.

MY FIRST SCRIPT
===========================
In the early stages, ThirstScript syntax is very similar to that of Python or BASIC, so a basic (haha) understanding of either would be useful. In python, the "print" command runs thusly::

  print ("Hello World!")

The syntax in ThirstScript is similar, as it runs like this::

  OUTPT "Hello World!"

The ```OUTPT``` command is the syntax for outputting anything, be it a string, a variable, a number or an expression.

The outpt command is not case sensitive, as it works in lowercase too.

Nice! So, you've created a script. Save it as "Test.thsc", then to run it, store it in the same folder as ThirstScript.exe. Next, go to the command line! To get to the command line, click on this bar at the top of the folder:

.. image:: /cmline.JPG
