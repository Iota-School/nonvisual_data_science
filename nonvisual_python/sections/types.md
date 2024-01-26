[<<< Previous]math.md) | [Next >>>](variables.md)

# Types

Types are classifications that let the computer know how a programmer intends to use a piece of data. You can just think of them as, well, types of data.

We've already seen one type in the last section: the integer. In this section, we'll learn four more: the floating point number, the string, the boolean, and the list.

Type each of the following lines, press `Enter`, and listen for the output:

```python
type(1)
```

(That's the word "type," an opening parenthesis, the number 1, and a closing parenthesis.)

```python
type(1.0)
```

(That's the word "type," an opening parenthesis, the number 1, a decimal point, a zero, then a closing parenthesis.)

```python
type("hello!")
```

(That's the word `type`, an opening parenthesis, a double quotation mark, the word `hello`, another quotation mark, then a closing parenthesis.)

```python
type(True)
```

(That's the word `type`, an opening parenthesis , the word `True` with a capital T, and a closing parenthesis.)

```python
type([1, 2, 3])
```
```

(That's the word `type`, an opening parenthesis , an opening square bracket, the number 1, a comma, the number 2, a comma, the number 3, a closing square bracket, and a closing parenthesis.


## Type Descriptions

Each of these lines represents a different type:

integer: `1`

Integers are numbers without decimal places, such as 4 or 5.

Float: `1.0`

Floats are numbers with decimals, and are treated a little differently than integers.

String: `"hello!"`

Strings are arbitrary sets of characters, such as letters, numbers, and symbols. You can think of them as a way to store text.

Boolean: `True` and `False`

Boolean is a fancy term for values representing "true" or "false," or "truthiness" and "falsiness."

List: `[1, 2, 3]`

A list is an ordered collection of values. You can put any type in a list: `["rose", "daisy", "buttercup"]` is also a valid list. (That's a list containing three strings.)

Don't worry about trying to actively remember these types. We'll be working with each in turn in the following sections.

## What's the deal with type()?

The `type()` text with parentheses we used above is a function. You can think of functions in Python in a few different ways:

1. A way of doing something in Python.
2. A way of saving some code for reuse.
3. A way of taking an input, transforming that input, and returning an output. The input goes in the parentheses `()`.

These are all valid ways of thinking about functions. For now, you might just want to think of a function as a way to perform an action in Python.

[<<< Previous]math.md) | [Next >>>](variables.md)
