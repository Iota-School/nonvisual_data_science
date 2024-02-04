[<<< Previous](variables.md) | [Next >>>](conditionals.md)

# Lists

## Lists

Remember lists? They look like this:

```python
flowers = ['rose', 'violet', 'buttercup']
```

Go ahead and type in the above line to assign a list with three strings in it to the `flowers` variable. Remember to put quotes around each of the three strings and to separate items in the list with a comma.

Check your list by typing the variable name `flowers`. You should hear the output `['rose', 'violet', 'buttercup']`.

## Getting the Length

So far in this workshop, we've only used one function, the `type()` function. Let's try another. Enter the following line:

```python
len(flowers)
```

That's the word `len` (short for length), an opening parenthesis, our flowers variable, and a closing parenthesis.

When we run the above, we should hear the integer `3` as output. That means our list has three items in it. 

## List Slicing

One useful feature of lists in Python is list slicing, which allows you to pull out specific items at a certain location within the list. Try the following:

```python
flowers[0]
```

That's the variable name `flowers`, an opening square bracket, the integer `0`, and a closing square bracket. You should get `rose` as output, since that's the first (or zeroth) item in the list. (Confusingly, in Python and in most other programming languages, counting starts from zero.)

Try accessing the other list items (`violet` and `buttercup`).

You can count backward from the end of a list using negative numbers. For example, the last item in the list would be `-`.

```python
flowers[-1]
```

## What About Loops?

A common way to do things in Python is to write what is called a loop, essentially some code that runs for each item in a list or list-like object. In future workshops we'll be using Pandas, a library (tool) for data science. While Pandas has some support for using loops, it has its own approaches to working with lists and list-like objects, so we're not going to cover for loops in this introduction to Python. 

While we won't be working with loops in this workshop series, they're an essential part of Python. If you'd like to learn more about for loops, here are some links to additional materials:

[Loops on the DHRI Curriculum](https://github.com/DHRI-Curriculum/python/blob/v2.0/sections/08-loops.md)  
[Iteration on Python for Everybody](https://www.py4e.com/html3/05-iterations)  


[<<< Previous](variables.md) | [Next >>>](conditionals.md)
