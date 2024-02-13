[<<< Previous](dataframe_fundamentals.md) | [Next >>>](challenges.md)

# Pulling It Together

So far, we've used our various series and dataframe methods on a toy dataset we created ourselves. Let's try using them on a real world dataset.

## Reading In Our Dataset

For this section, and for the next workshop, we'll be using a large dataset of Airbnb rentals in New York City. The data is sourced from [this repository](https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data) on Kaggle, a website for sharing datasets for analysis. The data is from 2019, so predates both the pandemic and the 2023 Airbnb legislation in New York City.

## Reading Our Data

Our first step is to have Pandas pull in our Airbnb data. Copy the following line and run it in IPython:

```python
df = pandas.read_csv('https://bit.ly/nycbnb')
```

<!-- If you're having trouble running this command, try these steps. -->

## Initial Analysis

Let's run through the procedures we've learned to get a feel for our dataset.. First, let's get the size of the dataset in rows and column:

```python
df.shape
```

The output of this command should be `((48895, 16)`. That means we have 48,895 rows and 16 columns. Another way to think about that is that we have 48,895 advertised Airbnb rentals and each of those entities has 16 items of information about it.

Before we can proceed, we should learn what kinds of data we have to draw on. Let's get the names of the various columns in the dataset:

```python
df.columns
```
Earlier I said the output of this command is a list-like object Unfortunately, this data type (the Pandas index) is somewhat annoying to review as a screen reader user. If you'd like to review the output one line at a time, you can convert the index to a normal Python list with the `list()` function:

```python
list(df.columns)
```

Since a normal list with many items will be printed out one item per line in IPython, you may find the output easier to review.

There are many interesting columns in this dataset, but a few stand out:

- price
- name
- neighbourhood

Check out each of these columns by pulling them out of the dataset as a series. You'll find that:

- The `price` columns consists of integers (int64), presumably representing dollars.
- The `name` columns appears as strings or string-like objects. (Pandas guesses as `object`.)
- The `neighbourhood` column are also string-like objects, but with many repeated values.

These are very different types of data. In the next workshop, we'll learn how to deal with data like `name` (textual) and `neighbourhood` (categorical). Let's wrap up this workshop by working a little with our `price` column.

## Limiting Our Data

You might have noticed that when we pull out columns from a large data set like this one, Pandas does not print out the entire 48,895 items. Instead, Pandas outputs the first five items, prints an ellipsis, then outputs the last five items. As screen reader users, we may wish to limit this output further. One approach might be to use `iloc[0]` to return only the first item in the data set. Alternatively, we can use one of two methods that work on both dataframes and series to limit the amount of output:

- The `head()` method pulls out the first items from a dataframe or series (five by default).
- The `tail()` method pulls out the last items from a dataframe or series (five by default).

## How Expensive Are new York City Airbnbs?

Let's end our workshop by taking a look at prices in New York City airbnbs. We'll use only methods we've learned so far in this workshop. 

First, let's figure out what the mean (average) price of an airbnb is in New York City in 2019:

```python
df.price.mean()
```

That's df, a dot, our `price` column, a dot, then our `mean` method with opening and closing parentheses.

Our output should be `152.7206871868289`. That seems pretty high for a single night's sleep. Maybe NYC is as expensive as you've heard?

Notice that we are using multiple dots to combine attributes and methods in a sequence. We start with our dataframe variable (`df`), then pull out the column, then use the `mean()` method. We call this technique "chaining."

Let's now try our `median()` method:

```python
df.price.median()
```

Our median is `106.0`. That's pretty different from our average. What do you think that means?

Remember that the average is the sum of all the items divided by the number of items. If we have the following numbers:

5, 10, 10, 10, 10, 10, 99999

Then the average is 14293.42857142857. However, the median would be 10. Averages are very sensitive to a small number of extremely high numbers. The median, however, is not sensitive to a small number of outliers in this way.

To put this another way, imagine that we have a data set of the net worth of everyone in the last class you took. Now imagine we add multibillionaire Jeff Bezos to this dataset. Once Jeff Bezos is added, the average net worth of the group will increase by a large amount, probably by at least a billion (unless you were in a very large class or the people in your class were extraordinarily wealthy). However, the median would change only slightly.

Because the median price of an Airbnb rental is significantly lower than the average, we can assume that there are a number of extremely expensive rentals in New York City that are driving up the average. We can check this by chaining together a few more methods:

```python
df.price.sort_values().tail()
```

This sorts all the prices, then returns the last five. (By default, `sort_values` sorts in ascending order, or from least to greatest.) The output shows that there are some very expensive rentals that are driving up the average. We call this situation, where the mean is greater than the median, a right-skewed distribution.

If we were to use a visual technique such as a bar graph to represent the data, we might also see that the data has a smaller number of very large values. However, we can also make similar insights about the shape of the data through techniques such as looking at the mean and median. In the next session, we will consider more sophisticated ways to generate insights about large data sets nonvisually.

[<<< Previous](dataframe_fundamentals.md) | [Next >>>](challenges.md)
