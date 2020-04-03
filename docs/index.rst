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
What follows is something of a "Beginner's guide" to using thirst. Please try.

Installation
~~~~~~~~~~~~~~~~~~~~
I'll put the installation stuff here when I put a proper thing. For now, clone the git repo.

Editing Environment
~~~~~~~~~~~~~~~~~~~~
At the moment, ThirstScript is only suitable for Windows computers. Sorry. If you have a multi-purpose programming environment like Sublime Text, I would encourage you to use that. Save your files with the .thsc file ending and move on to `My First Script <https://thirstdocs.readthedocs.io/en/latest/#id1>`_. If not, you probably have notepad. Follow along the Notepad instructions below.

Notepad as an editor
~~~~~~~~~~~~~~~~~~~~
If you wish to use notepad as an editor, create a notepad file called "Test.thsc". It will create a file called "Test.thsc.exe". Rename it to "Test.thsc". If a popup comes up asking if you're sure, say yes. I hate those. Hooray you did it now move on to **My first script**.

MY FIRST SCRIPT
===========================
In the early stages, ThirstScript syntax is very similar to that of Python or BASIC, so a basic (haha) understanding of either would be useful. In **Python**, the "print" command runs thusly::

  print ("Hello World!")

The syntax in **ThirstScript** is similar, as it runs like this::

  OUTPT "Hello World!"

The ```OUTPT``` command is the syntax for outputting anything, be it a string, a variable, a number or an expression.

The outpt command is not case sensitive, as it works in lowercase too.

Nice! So, you've created a script. Save it as "Test.thsc", then to run it, store it in the same folder as **ThirstScript.exe.** Next, go to the command line! To get to the command line, click on this bar at the top of the folder:

.. image:: /cmline.JPG

Click to select it, delete it all and write "**cmd**". Press enter. Now type this into the command prompt::

  thirst.exe Test.thsc

Press enter and you should get this output::
  
  Hello World!

Pretty neat, eh? Now let's talk about other syntax!

Outputting with "OUTPT"
~~~~~~~~~~~~~~~~~~~~
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
~~~~~~~~~~~~~~~~~~~~
In **Python**, variables are defined and then referenced like this::

  myvariable = 1
  print (myvariable)

That will output "1". In **Thirst**, it's almost the same::

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

Keep in mind though, if you reference a variable before it's defined::

	OUTPT $myvariable
	$myvariable = "Hello"

You will wind up with this message::

  VARIABLE ERROR: Variable "myvariable" undefined, you numpty!

Yes, I did put "You numpty" in the error message. I want to make the errors as jovial as possible to put my users at ease when they make a mistake.

INPUTTING WITH "INPUT"
~~~~~~~~~~~~~~~~~~~~
If you want the user to input something, use "INPUT". Wow!

When a user inputs something, they type it in, and the program stores that as a variable. Here's the syntax **in Python**::

	name = input("What's your name?")

That means it's storing the user's **answer** to the "name" variable. **In Thirst**, use this syntax::

	input "Whats your name?" $name

That's esentially the same thing. (Unfortunately, you can't yet use apostrophes (') yet in strings. Sorry.)) If you ever want to reference that variable::

	OUTPT $name

Yup, that's it. Easy as pieeee.

"IF" statements
~~~~~~~~~~~~~~~~~~~~
You're probably familiar with "if" statements. If not, here's how they're handled in **Python**::

  if x == 1:
    print ("X is equal to 1! Wow!")

That means *if* the variable "x" is equal to 1 *then* print this. It's quite similar in **Thirst**::

  if x == 1 let:
    OUTPT "X is equal to 1! Wow!"
  endif

Note the "endif" to mark the end of the If statement.

AND GATES
~~~~~~~~~~~~~~~~~~~~
In **Python**, if you want to make two conditions filled, you would write::

	if x == 1 and y == 1:
		print ("Two conditions whaaat")

However, in **Thirst** you need to use an AND GATE. An AND GATE is a way of showing more than one condition. The syntax is as follows::

	ANDG-2-x == 1-y == 1:
		OUTPT "Two conditions whaaat"

Let's break this down. First the ```ANDG``` signifies that it's an AND GATE. Then the following number means the amount of conditions that need to be fulfilled. Then afterwards come the conditions. Each argument is seperated by a hyphen (-). So to recap::

	ANDG-[ConditionNumber]-[Condition 1]-[Condition 2] etc.

May look a little confusing at first, but you'll get the hang of it.

OR GATES
~~~~~~~~~~~~~~~~~~~~
OR GATES are very similar to AND GATES, exept only one of the conditions has to be fulfillied. **Python syntax**::

	if x == 1 or y == 1:
		print ("One of them equals one... Magical!")

**In Thirst**::

	ORG-2-x == 1-y == 1:
		OUTPUT "One of them equals one... Magical!"

Incredible. There are no NOT GATES yet unfortunately. Wait for now.

ADVANCED SYNTAX
===========================
There are a few more bits of syntax that don't fit into "My First Script". That's because they're a little more complicated.

Sleep function
~~~~~~~~~~~~~~~~~~~~
Use the sleep function like the python time.sleep function. It simply creates a delay between commands for however long you tell it. Using::

	sleep 2

Will delay your code by two seconds. For example if your code is::

	OUTPT "Hey!"
	OUTPT "Wassup?"

Then it will just output them both straight away. But if you do::

	OUTPT "Hey!"
	sleep 2
	OUTPT "Wassup?"

Then it will wait 2 seconds inbetween. Nice.

An introduction to Potato Variables
~~~~~~~~~~~~~~~~~~~~
Now, "Potato" Variables as I've decided to call them, cos it's funny, or call 'em "slash" variables if you're boring. Potato Variables are types of variables that are different from "regular variables". Regular Variables contain either strings, numbers or expressions. Potato variables can handle:


• Hotkeys

• Sprites/Images

• `Discord Bot Clients <https://thirstdocs.readthedocs.io/projects/Discord_Bots/en/latest/>`_

• Music/Sound Files


So let's break down the different syntax for Potato Variables. As you may remember, **Regular Variables** are handled like this::

	$myvariable = "hi"

But **Potato Variables** are defined like this::

	/myvariable

I left the space aftewards intentionally blank for different syntax.

.HotKey Potatoes
~~~~~~~~~~~~~~~~~~~~
Hotkeys are keystrokes simulated by a script. Say you wanted it so when you ran a script, the script would type "Hello World!" without you having to do anything. Sound amazing? First you have to define the potato variable::

	/myhotkey = .HotKey("Hello World!")

Let's break this down. First, the name of the variable is "myhotkey". Then comes the definition. It's a hotkey potato, so you use .HotKey. We will explore other kinds of hotkeys soon. Then what keystrokes you want the hotkey to simulate. If it's a string, a letter or a number, like above, keep it in quotes. If it is a modifier or function key, other syntax applies. For example, if you want it to simulate pressing *ctrl* then use::

	/myhotkey = .HotKey(^)

The modifier keys synatx are:

• *^* - Ctrl

• *+* - Shift

Ok, there aren't any more yet. Now if you want to output this HotKey, use this command::

	HKOUT /myhotkey

Then it will do your hotkey for a default of 1 second. You can't change that yet, but wait for the next update.

Now lets learn how to INPUT hotkeys.

You still need to use that syntax for defining Hotkeys. When you input though, you need to open and close the hotkey input.::

	HKINPT OPEN

That command will make it so after it's executed, Hotkey input is allowed. Underneath it, to check an input use::

	if HKINPT == /myhotkey let:
		OUTPT "You pressed my HotKey!"

Nice. If you want that to not work anymore, then just use::

	HKINPT CLOS

That's HotKeys done for now.

.image Potatoes
~~~~~~~~~~~~~~~~~~~~
These are potato variables that store images. Say I draw the following masterpiece:

.. image:: /Masterpiece.png

I know what you're thinking: "Wow what a renaissance man! Gifted in programming *and* art?" I know you're impressed at my prowess, but let's stay focused here, shall we?

Now say I'm composing a program that opens a window displaying this masterpiece for the world to see. I'd want to use a .image potato variable. Similar syntax to HotKey now, we want::

	/mymasterpiece = .image([filename])

Say the filename was "A study of ennui.png" then I would first store the image in the same folder as my script (and Thirst.exe, obvs). Then I would write in my script::

	/studyofennui = .image(A study of ennui.png)

Then I would use the image output command::

	IMOUT /studyofennui

Haha, I just noticed that command looks like "I'm Out". Oh, what fun.

.bot Potatoes
~~~~~~~~~~~~~~~~~~~~
If you want to learn the ways of creating discord bots and applications with Thirst, go to the special Discord Thirst docs at this link:
https://thirstdocs.readthedocs.io/projects/Discord_Bots/en/latest/

.sine Potatoes
~~~~~~~~~~~~~~~~~~~~
This kind of potato variable stores a **sine wave** sound. You can store it by specifying the hertz of the note you want to express. For example, middle C is 261.63 Hz, so you'd store it like this::

	/mynote = .sine(261.63)

Then, to play it, you also need to specify how many **seconds** you want it to last. So use "WAVOUT" to output the sine wave with the following syntax::

	WAVOUT /mynote(1)

That will play middle C for 1 second.

.audio Potatoes
~~~~~~~~~~~~~~~~~~~~
These are for storing audio files. I think .wav, .mp3 and .ogg will work fine, (might need to check that one). First, put the audio file you want in the same folder as your project and Thirst.exe. Now say my audio file is called "FuniculiFunicula.mp3", and it is a recording of the famous Italian song. First, to store it I would use this syntax::

	/myaudio = .audio(FuniculiFunicula.mp3)

It's as easy as that. Now to play it, use::

	AUDIOOUT /myaudio

Wow! Who'd have thunk it would be that easy to play Luigi Denza's masterpiece of the funicular railway commemoration genre!

That's kind of it for now
===========================
That's all the syntax and stuff for now. Hooray.
