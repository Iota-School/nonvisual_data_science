[<<< Previous](installation.md) | [Next >>>](review.md)

# Interacting with the Python REPL

## Starting the Console

At this point, you should have NVDA and Anaconda installed. (If not, [follow the instructions on the previous page](installation.md)).)

Throughout this workshop, you'll need to have NVDA on. To turn on NVDA, hit the Windows button, type NVDA, and press Enter.

We'll be working with Python in Anaconda Prompt. To open Anaconda Prompt, press the Windows button, type "anaconda prompt," and press Enter.

If NVDA is running when you open Anaconda prompt, you'll hear output that includes `C:\Users\<your username>`. You can also check that you're in the right place by hitting your NVDA button (`insert` by default) and `t` to get the title of the application, which should be Anaconda Prompt.

## Starting Python

When we open Anaconda Prompt, we are interacting with a special version of the `cmd` command line interface that comes with Windows. This version includes access to a lot of installed utilities related to Python.

To start Python, type the below line and press `Enter`.

```cmd
ipython
```

That's the word `python`" but with a letter `i` at the start. There are no spaces, and all the letters are lower case. (As you'll learn, you'll need to get things exactly right when working in the command line and with Python.)

After entering this command, you'll be interacting directly with a running Python process, and you're ready for the work we'll do in the next section. First, though, let's learn about what the command line is and what it's for.

## What is a REPL?

You'll hear the command line called many things: terminal, shell, CLI (short for command line interface), and console are common names for the command line. Fundamentally, the command line is a way of interacting with the computer through text commands. The command line interface, or CLI, can be contrasted with the graphical user interface, or GUI, that you may be more familiar with.

In programming, the command line is sometimes called a REPL, short for Read, Evaluate, Print, Loop. This refers to the basic way that you interact with the command line in four steps:

1. Read input from a user. (The user types a command and presses `Enter`.)
2. Evaluate the input. (The command line takes the input and performs some task.)
3. Print a response. (The command line provides some information back to the user.)
4. Loop back to the first step, where the command line waits for input from the user.

Fundamentally, the approach here is a conversation with the computer. You type something, and the computer performs some process and provides a response. You can then continue the conversation by providing more input, and so on.

In this workshop, we'll be using the Python REPL throughout. That means we'll be having a conversation with the machine, where we provide input and the computer provides output.

## A Note on Windows

By default, Windows comes with two command line interfaces. The first, called `cmd.exe` or command prompt, has been around for a long time. This interface is functionally similar to the command line interface on the DOS operating system. Windows also comes with a more modern command line interface called Powershell.

When you open Anaconda Prompt, you are interacting with a version of `cmd.exe` that has additional commands related to Python loaded in. We aren't interacting with Python directly until we type the `ipython` command.

[<<< Previous](installation.md) | [Next >>>](review.md)
