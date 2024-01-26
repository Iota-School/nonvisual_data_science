[<<< Previous](types.md) | [Next >>>](lists.md)

# Variables

A variable is a symbol that refers to an object, such as a string, integer, or list. Fundamentally, it is a way of giving a name to data. Once the data is named, Python keeps track of it moving forward.

Let's try entering this line:

```python
x = 5
```

That's an x, a space, an equals sign, a space, and a 5.

You shouldn't hear any output from this line. (That is, you'll just hear the word `In` and a number as Python waits for new input from you.)

Now let's just type the letter `x` and press `Enter`. You should hear `5`, which is the data we saved to the variable `x`.

Try these lines:

```python
x + 10
```

You should hear `15` as output.

Let's save a string as the variable `y`:

```python
y = "hello"
```

Now try accessing the data by typing `y` and pressing `Enter`. You should hear `"hello"` as output.

Try entering the following line:

```python
y + " and goodbye"
```

That's a `y`, a space, a plus, a space, a quotation mark, the words `"and goodbye"`, and another quotation mark. You should hear `"hello and goodbye"` as output.


## Explanation

The `=` sign lets you assign symbols like `x` and `y` to data.

Variables can be longer words as well:

```
breakfast = ['ham', 'eggs', 'toast']
```

If you run the above line, a list with three strings is assigned as the variable `breakfast`.

Variables can have letters, numbers, and underscores, but should start with a letter. 

## Question: Where Do Variables Live?

When you assign a variable, Python starts keeping track of it. The variable name and associated data is stored in your computer's memory. If you close the IPython process, all variables and other assignments are cleared and you start a fresh session. There are ways to save your session to resume later, but we'll talk about those later.

## Question: What's the Deal with Spaces?

In the above variable assignment lines, I added in a space before and after the equals sign. These lines will totally work without the spaces. However, sighted people find the spaces make lines easier to read, and it's considered good style to add in these spaces. It can be good to get into a habit of adding these spaces, since it makes your code easier to read and more professional-looking. However, if you're writing code for yourself or you intend to use a tool (called a linter) to tidy up your code after writing, you might choose to leave off spaces, and I've noticed many blind coders leave off these spaces.

[<<< Previous](types.md) | [Next >>>](lists.md)
