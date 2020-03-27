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

Click to select it, delete it all and write "cmd". Press enter. Now type this into the command prompt::

  thirst.exe Test.thsc

Press enter and you should get this output::
  
  Hello World!

Pretty neat, eh? Now let's talk about other syntax!

Outputting with "OUTPT"
===========================
So as you saw before, to ouput a string you use the following syntax::

  OUTPT "Hello World!"

However, you can also you ```OUTPT``` to output numbers and expressions. If you input::

  OUTPT 12

Then your ouput will say "12". OUTPT automatically evaluates any expression you ask it to. For example::

  OUTPT 20 + 10

Will output::

  30

The OUTPT command will evaluate the correct order of operations, too. Isn't it magical?::

  OUTPT 6 + 2 * 2

Will Output::

  10

I know what you're thinking: "Wow! Calculation! Is there anything ThirstScript can't do?" Well hold on to your hats, because we're about to cover variables.

Variables
===========================
In Python, variables are defined and then referenced like this::

  myvariable = 1
  print (myvariable)

That will output "1". In Thirst, it's almost the same::

  $myvariable = 1
  OUTPT $myvariable

The $ sign means that the following statement is a variable. There are three kinds of "regular" variable. Numbers, strings and expressions, similar to OUTPT. So::

  $myvariable = 10 + 10
  OUTPT $myvariable

Will give you::

  20

And::

  $myvariable = "Hello World!"
  OUTPT $myvariable

Will give you::

  Hello World!
  
Pretty nifty, eh? You can redefine variables at any time. So writing::

  $myvariable = "Hello"
  OUTPT $myvariable
  $myvariable = "World!"
  OUTPT $myvariable

Will give you::

  Hello
  World!

Keep in mind tho, if you reference a variable before it's defined::

	OUTPT $myvariable
	$myvariable = "Hello"

You will wind up with this message::

  VARIABLE ERROR: Variable "myvariable" undefined, you numpty!

Yes, I did put "You numpty" in the error message. I want to make the errors as jovial as possible to put my users at ease when they make a mistake.

"IF" statements
===========================
You're probably familiar with "if" statements. If not, here's how they're handled in Python::

  if x == 1:
    print ("X is equal to 1! Wow!")

That means *if* the variable "x" is equal to 1 *then* print this. It's quite similar in Thirst::

  if x == 1 let:
    OUTPT "X is equal to 1! Wow!"

