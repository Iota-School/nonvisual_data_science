[<<< Previous](conditionals.md) | [Next >>>](motivation.md)

# Looking Inside Objects

In this workshop, we've used five data types so far: integers, floats, strings, booleans, and lists. We've noticed that there are some things we can do with some objects, but not with others. For example, we used the `len` function to check the length of a list. It's also possible to use `len` on strings, which will tell us how many characters are in the string. However, when we use `len` on an integer, we get an error:

```python
len(5)
```

This returns the following error output:

```
TypeError: object of type 'int' has no len()
```

In Python, everything is an object. What you can do with any particular object is partly determined by that object's type. You can do certain things with lists that you can't do with integers, and you can do certain things with integers that you can't do with strings. Types allow us to place data in a specific category so we can work with it more intuitively, doing math with integers and floats, adding or removing items from lists, and so on.

One way to think about objects is that they are containers. Inside these containers, you find functions that can act on that object and variables that contain data about the object. Because we like to have special terms for things in programming, functions and variables found inside objects have their own names:

- **Methods** are functions contained inside objects.
- *Attributes* are other data contained inside objects.

## Using Object Methods

Remember our list of flowers we used before? If you've restarted yourIPython session, you can recreate it with the following:

```python
flowers = ['rose', 'violet', 'buttercup']
```

What if we want to add another item to our `flowers` list? Enter this line of code:

```python
flowers.append("daisy")
```

That's `flowers`, a period, `append`, an open parenthesis, a quotation mark, `daisy`, a quotation mark, and a closing parenthesis.

You can see if the `flowers` list has changed by typing `flowers` and hitting `Enter`. You should receive the following output:

```python
['rose', 'violet', 'buttercup', 'daisy']
```

Daisy has been added, or appended, to the end of the list.

What did we do here? We used the method `append` contained within our `flowers` list object. That method receives one piece of data, the object to be added to the list, which we place within parentheses. We call data passed to a function or method an "argument."

## Getting Information About Objects

We already know a few ways to get information about an object in Python.

1. We can enter a variable name into the REPL by itself to receive a representation of that object. For example, when we type `flowers` into our REPL, we learn what data is contained in the list.
2. We can use the `type` function to learn the data type of an object. That lets us know if it's an integer, list, boolean, string, or some other data type.
3. For certain objects, we can use the `len` function to see how much data it contains. For lists, this gives us the number of items in the list, and for strings, this gives us the number of characters in the string.

In addition, we can use these other useful functions:

To get general information on an object, we can use the `help` function. Try this:

```python
help(flowers)
```

This gives us some information on the data type, including what methods and attributes defined for the object. For now, you will want to mostly ignore the methods with underscores around them.

We can also use another function, `dir`, to get just a list of names of methods and attributes in an object. 

```python
dir(flowers)
```

The output from both of these functions can be pretty overwhelming. Often it makes more sense to search for a data type using a search engine and you'll find lists of the most commonly used methods and attributes, or you'll discover new methods and attributes while following tutorials or searching for how to perform a specific task.

## Frequently Asked Question: What Are the Methods with Underscores?

In this section, I told you that you might want to ignore methods that have underscores, since you're unlikely to use them directly. If we're not going to use them, why are they there?

These are special methods, often called "magic methods," that allow other features of the language to work. For example, magic methods are what allow you to add and subtract integers using plus and minus. While working with these methods directly is useful for creating your own interfaces in Python, you may wish to ignore these for now.

[<<< Previous](conditionals.md) | [Next >>>](motivation.md)
