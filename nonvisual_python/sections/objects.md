[<<< Previous](conditionals.md) | [Next >>>](objects.md)

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


[<<< Previous](conditionals.md) | [Next >>>](objects.md)
