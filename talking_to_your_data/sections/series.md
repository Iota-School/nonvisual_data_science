
# The Series

Now that we know about dimensions b in data, let's try working with one-dimensional data. In regular Python, the default data type we use for one-dimensional data is the list. Go ahead and create the list below:

```python
budget = [10, 10, 5, 15, 15]
```

In the above, we create a list with five items (10, 10, 5, 15, and 15), and assign it to the variable 'budget'.

We [learned a few ways to do things with Python lists in the previous tutorial](../..//home/patrick/projects/nonvisual_data_science/nonvisual_python/sections/lists.md) (slicing to pull out specific items, the `len` method to learn the legth of the list, and the `append` method to add items to the end of the list). But there's a lot more we can potentially do with the data in this list.

## Pandas Series

Let's import the Pandas library:

```python
import pandas
```

There should be no output after entering the above line in IPython.

Now let's create a Pandas series from our listand assign it to a new variable, which will simply be the letter `'s`.

```python
s = pandas.Series(budget)
```

In the above, we access the `Series` type object (note the upper case in `Series) inside the Pandas library. Then we pass in our `budget` list.

This transforms our `budget` list into a new data type, the Pandas series, and assigns the series to the variable `s.

## Reading a Series

Now that we have our series assigned to the variable `s`, type `s` on its own line and press `Enter` to receive a representation of the series:

```python
s
```
The representation of our series will be as follows:


```
0    10
1    10
2     5
3    15
4    15
dtype: int64
```

The output is six lines total. The first five lines each have two numbers, one on the left and one on the right. 

- The number on the right is our budget data. We call this the `value`.
- The number on the left is the index. By default, it tells us the location of the data, just like when we do list slicing. The index has other uses that we will learn about later.

The line at the end tells us the data type of the items in the list. In this case, it is `int64`, meaning an integer.

## Series Methods

The main reason we choose to use a Pandas series over a regular Python list is the wide variety of methods provided by the Pandas series. Let's try out a few of these now.

First, let's get the average of the numbers in the list. (Remember that the average or mean is the result of adding up all the numbers, then dividing by how many numbers there are.)

```python
s.mean()
```

In the above, we access the `mean` method inside our series assigned to the variable `s`. The method takes no arguments, so we don't place anything inside the parentheses.

Our output from the above should be `11`. That's the average of 10, 10, 5, 15, and 15

Let's get the median of the five numbers in our series. (Remember that the median is the middlemost number, or the average of the two middlemost numbers.)

```python
s.median()
```

This result might be more intuitive if the series were sorted. Let's try the `sort_values` method:

```python
s.sort_values()
```

This outputs our series with the values sorted from least to greatest. If you review the output, you'll find that the middlemost number of the five values is indeed `10`.

A few other methods to try:

```python
s.min()
s.max()
s.count()
s.sum()
s.std()
```

## Describe

A commonly-used Pandas series method is `describe`. Try it out:

```python
s.describe()
```

Go ahead and review the output. Here are some highlights:

- The `count` is the number of items in the series.
- The `min` and `max` are the minimum and maximum values, respectively.
- The `mean` is the average.
- The `50%` is the same as the median, meaning the middlemost number. The `25%` and `75%` (twenty-fifth and seventy-fifth quartiles) are the numbers closest to the 25% and 75% mark in the dataset, or the median of the lower half and upper half of the data set, respectively.
- The `std` is the standard deviation. The standard deviation is a measure of how much variability is in the data set. If the number is low, most values in the data set are close to the average. If the value is high, values in the data are more dispersed.

## What's the Deal with the Describe Method?

We'll be moving on from thinking about series, though we'll be using them constantly from now on. But let's think about the describe method and its output.

First, here's a quick question. What data type is the output of `describe()`?

If you answered a Pandas `series`, you'd be correct. Some clues are that the last line of the output included a data type, `float64`. The last line of a Pandas series representation includes the data type. Each line of the output has two items: on the left, the index, and on the Right, the value. In this case, the index is a useful label, rather than a number.

## Is Describe Useful?

My sighted students often ask me why we would use methods such as `mean` and `max` if the `describe` method prints out that information and more. For them, my answer is that you will often want to do work with specific numbers.

For screen reader users, the question is reversed. `Describe` offers us a little too much output. It's rare that we want to know the mean, median, count, max, etc. all at once. We might sometimes want all this information, but usually it's more straightforward to get back information one piece at a time. This requires less reviewing on our part.

Is describe useless, then? Sometimes you will want to get a lot of data at once because you don't yet know what you're looking for. And sometimes you'll be working with a sighted colleague and you know that `describe` would be the best way to give a high-level overview. 

Mostly, though, as a screen reader user, you will want to limit the amount of output you get back. Luckily, Pandas gives us many tools for controlling the amount of information that gets returned to us, meaning less time reviewing output and more time doing data science.

## FAQ

Why is `Series` capitalized when we create a series object? In Python, there are certain kinds of data that are capitalized. The `Series` we access in Pandas is a `class`, a kind of template for making new objects, and the convention is to capitalize a class in Python. (In fact, the convention is to use word case, or camel case, meaning we capitalize the beginning of each word in the name.)

Why do we use such a short variable name (`s`) for our series? Generally speaking, in Python, you are encouraged to use descriptive variable names, and `s` is not very descriptive. The short answer here is that there are some informal conventions in the Python data science community. If there will only be one series, we will often call it `s`. We will learn one or two more of these informal short variable conventions in these tutorials. However, if you're tempted to start naming varaibles `s1`, `s2`, etc., it's probably time to give your variables longer names.

