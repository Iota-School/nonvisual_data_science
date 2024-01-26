[<<< Previous](repl.md) | [Next >>>](math.md)

# Interaction and Review

## Starting IPython

For this section of the workshop, you should be in the IPython REPL. That means you should have followed these steps:

1. Open Anaconda prompt from the Start menu. A window with a console should open.
2. Type `ipython` (all lower case) and press Enter.
3. You will be ready to continue when you perceive the following message:

	```
	Python 3.8.8 (default, Apr 13 2021,
	15:08:03) [MSC v.1916 64 bit (AMD64)]
	Type 'copyright', 'credits' or 'license' for more information

	IPython 7.22.0 -- An enhanced Interactive Python. Type '?' for help.
	In [1]:
	```

## A Little Math

Let's start our conversation with Python by doing a little math. Type the following into the prompt:

```
2 + 2
```

and then hit `Enter`. You should hear something like the following:

```
Out[1]: 4

In [2]: 
```

The output can be a little confusing at first, as some of the numbers we're hearing are related to where we are in our conversation with Python. The output we can back consists of three lines. The first like reads as follows:

```
Out[1]: 4
```

The `Out[1]` part tells us that this is the output of our first interaction with the Python process. The `4` is our output, the result of adding `2 + 2`.

After our result, there is a blank line. Then IPython asks us for more input with the following: `In [2]: `.

Let's try another input. Type a double quote, then write the word `hello`, then type another double quote. Your input should be as follows:

```
"hello"
```

You should now hear the following:

```
Out[2]: 'hello'

In [3]: 
```

Here, we gave `"hello"` as an input. Python has echoed our input back at us.

Every interaction with the IPython REPL consists of two parts: an input and an output. Lines with input start with the word `In` and a number in brackets. Lines with output start with the word `Out` and a number in brackets. THe number indicates where we are in the session, starting with the number `1` and counting up.

In the IPython and Jupyter ecosystem, the pairing of an input and output are called `cells`. In IPython, each cell (input and output) are separated by a blank line.

## Exploring the Output

Let's use NVDA's review cursor to explore what we've written so far. This skill will become more important as Python returns more complex output to us.

NVDA has two modes, desktop and laptop. The desktop mode requires that your machine have a numpad or that you have an external numpad plugged in. I find that the desktop shortcuts are more intuitive in general. However, the laptop layout will work on all machines and does not require a numpad. 

By default, the NVDA key is `Insert`. However, this can be changed in NVDA preferences. I find that, on laptops, the `Capslock` key makes a good NVDA key. When describing shortcuts, I'll simply say the NVDA key.

The first three review shortcuts we'll use allow us to review line by line. 

To review the current line:

NVDA + shift + .
NVDA + NUMPAD 8

That's NVDA, shift, period for laptop layouts and NVDA and numpad 8 for desktop layouts. This command will read aloud the line where the review cursor is currently situated.

To move the review cursor up one line:

NVDA + up
NVDA + NUMPAD7
flick up on touchscreen

On a laptop, hit NVDA and the up arrow. On desktop, hit NVDA and numpad 7. If you have a touchscreen, you can also flick up once.

To move the review cursor down one line:

NVDA + down
NVDA + NUMPAD9
flick down on touchscreen

On laptop, that's NVDA plus the down arrow. On Desktop, that's NVDA and numpad 9. On a touchscreen, you can flick down once.

## Exercise 1: Explore the REPL

Now we'll take five minutes to use these shortcuts to explore our current REPL. There should be two "cells," one with a little math and one with the word "hello" as input and output. Remember that input/output pairs (cells) are separated by a blank line (in NVDA, you'll hear the word `blank` when reviewing). If you go back far enough, you'll start reviewing the text that appears when the REPL session starts. The top line should tell you the current version of Python you're using.

We'll learn a few more review shortcuts as we move on in the workshop, but if you already know other NVDA review commands, feel free to use them. 

[<<< Previous](repl.md) | [Next >>>](math.md)
