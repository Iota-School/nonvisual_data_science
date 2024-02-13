[<<< Previous](keysvalues.md) | [Next >>>](dataframe_fundamentals.md)

# Creating a DataFrame

If the series is how we handle one-dimensional data in Pandas, the dataframe is how we handle two-dimensional data. Like the series, the dataframe provides a variety of methods for working with data contained in it.

To create a series, we first created a list and passed it to a Pandas Series object. To create a dataframe, we'll first have to create a dictionary.

## Creating the Dictionary

First, let's create three lists. If you've been following along from the beginning, you should already have the first list assigned as a variable.)

```python
budget = [10, 10, 5, 15, 15]
month = ["June", "July", "September", "October", "November"]
cookie_budget = [3, 2, 0, 4, 5]
```

You may wish to run `len()` on each of these lists to check that they have five items. If one has too many or too few items, you'll get an error in the next step.

Now that we have these lists, let's create a dictionary. 

```python
monthly_budget = {
    "month": month, 
    "budget": budget, 
    "cookie_budget": cookie_budget
}
```

In the above, we create a dictionary with three key-value pairs. The key is a string describing the data and the value is a list. 

## Creating the Dataframe

Finally, let's use the dictionary to create a dataframe:

```python
df = pandas.DataFrame(monthly_budget)
```

Let's check out the newly created `df` variable by entering it into a line by itself:

```python
df
```

The result will be a significant amount of output. The output should be similar to the table below, though note that the output will be unstructured text rather than a table:

      month       budget   cookie\_budget
  --- ----------- -------- ----------------
  0   June        10       3
  1   July        10       2
  2   September   5        0
  3   October     15       4
  4   November    15       5

This dataframe representation takes the form of a table. The first line consists of column headers. These headers are the keys in the dictionary we provided when creating the dataframe. Each subsequent line represents a row. The first column (the first number you hear in each row) is the index, which consists of integers 0, 1, 2, 3, and 4.

Because the dataframe representation isn't structured as a table, it's of limited use to screen reader users. While you can parse out the data by reviewing each line carefully, we will learn better ways to explore the data in the dataframe in the coming sections. With that said, it's good to be generally familiar with the structure of this representation.

While sighted data scientists do use these representations, they're not as useful as you might think. This is because, when dealing with large datasets, much of the information gets cut off anyway because it is impractical to display it all. You're not missing out on that much by not using the representation above—sighted data scientists also need to use the techniques to limit output we'll learn when dealing with datasets that have many columns and/or rows.

[<<< Previous](keysvalues.md) | [Next >>>](dataframe_fundamentals.md)
