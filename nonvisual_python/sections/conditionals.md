[<<< Previous](lists.md) | [Next >>>](objects.md)

# Conditionals

A conditional is a statement that evaluates to either True or False. For example, enter the following into our REPL:

```python
10 > 5
```
That's the number 10, then a greater sign, then a five. As output, you should get back `True`. Python looks at the statement, evaluates it (simplifies it), determines that ten is greater than five, and lets us know it's true by returning `True` as a value.

## Boolean's

In Python, a boolean is a type that represents either true or false. They're represented with capital letters: `True` and `False`. 

## Comparison

One of the most common uses of conditional statements is to compare two objects. We already saw one way to compare using `>`, or the greater than symbol. For example:

```python
10 > 50
```
Since 10 is less than 50, the above will return `False`. If we instead use the `<` sign, as below, the result would be `True`.

```python
10 < 50
```

You can also check for equality between two objects using the `==` operator. (That's two equals signs.)

```python
5 == 5
```

That's five, a space, a double equals sign, a space, and a five. The result should be `True`.

Now try the following:

```python
7 == 4
```

That's seven, a space, a double equals sign, a space, and a four. The result should be `False`.

You can also compare strings in this way:

```python
"hello" == "goodbye"
```

```python
"hello" == "hello"
```

Remember that, to create strings, we surround some text with quotes, in this case double quotes. When using our double equals operator (`==`) to compare `"hello"` and `"goodbye"`, we get `False`, whereas comparing `"hello"` with `"hello"` returns `True`.

## Why Two Equals Signs?

Why do we use two equals signs to check for equality? Remember that, when we assign variables, we use one equals sign (`=`). In Python, one equals sign (`=`) is used for assigning variables and two equals signs (`==`) is used for checking equality.

[<<< Previous](lists.md) | [Next >>>](objects.md)
