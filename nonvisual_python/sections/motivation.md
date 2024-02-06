[<<< Previous](objects.md) | [Next >>>](magic.md)

# A Little Motivation

We're coming to the end of our workshop. To inspire you for the next in the series, let's create a simple application that will provide you with a little motivation when you need it.

First, we'll create an empty list and fill it with some motivational (or funny) quotes. Then, we'll use a randomizer to choose a quote from the list for us. To use this randomizer, we'll learn about importing libraries, arguably Python's most powerful feature.

## Creating Our Data

To start, let's create an empty list and assign it to the variable `motivational_quotes`. (That's the words `motivational` and the word `quotes` separated by an underscore.)

```python
motivational_quotes = []
```

That's our `motivational_quotes` variable name, a space, an equals sign, a space, an opening square bracket, and a closing square bracket.

We now have an empty list, ready for us to fill it with quotes. Let's use our `append` method to add some quotes to the list: (Remeber that you can use the tab key to fill in our long variable name.)

```python
motivational_quotes .append("I think I'm getting the hang of this Python stuff.")
```

That's one quote. Let's add two or three more:

```python
motivational_quotes .append("I love syntax errors. Bring on the challenge!")
```

```python
motivational_quotes .append("I eat bugs for breakfast. But not those kinds of bugs.")
```

```python
motivational_quotes .append("Look, Mom, I'm using the command line!")
```

You can use whatever quotes you'd like, just remember to start and end with a double quote.

Let's check out our list by typing our variable name `motivational_quotes` variable into the REPL by itself. You should receive back a list with the quotes we added.

```python
Out[6]: 
["I think I'm getting the hang of this Python stuff.",
 'I love syntax errors. Bring on the challenge!',
 'I eat bugs for breakfast. But not those kinds of bugs.',
 "Look, Mom, I'm using the command line!"]
```

## Importing a Library

Everything we've done so far in this workshop has used built-in features of the Python language. However, to choose a quote randomly from our list, we'll need to pull in a more specialized function from the `random` library. Let's add this functionality to our program, then we'll explain what libraries are and how we use them in Python.

First, let's import the `random` library.

```python
import random
```
This creates a new object accessible to us in the REPL. Try entering `random` by itself and you'll learn that it's a module called `random`.

Let's use a function from the `random` library to choose a random quote from our list:

```python
random.choice(motivational_quotes)
```

You will hear a quote from your list. Press up to fill in the same line and press `Enter`, and you should hear a different quote each time.

## What Is a Library?

A library is a container of functions and other objects that can be easily pulled into your own Python programs. Libraries are typically created for a specific purpose: there are libraries for downloading websites, working with math, working with specific file types, and almost anything else you can think of. Library is a general term for code designed to be imported, the Python-specific term is a module.

Python comes with a standard library that includes modules for a wide variety of common tasks. In addition, the Anaconda distribution we're using includes a wide variety of libraries for tasks related to data science.

Functions such as `help` and `dir` work on imported libraries, though you may wish to look up the library's own documentation or some other tutorial to learn how to use a specific library.

[<<< Previous](objects.md) | [Next >>>](magic.md)
