[<<< Previous](creating_dataframe.md) | [Next >>>](synthesis.md)

# Dataframe Fundamentals

The dataframe contains two-dimensional data. Typically, this comes in the form of columns and rows. 

- Columns move from left to right (exist on the X axis) and typically represent some aspect of the data, such as name, date, or dollars spent on cookies. A column tends to collect data in the same data type.
- Rows move from top to bottom (exist on the Y axis) and typically represent an entity, such as a specific person, a specific month, a specific book, and so on. A row holds different kinds of data, all about the same entity.

## Dataframe Size

When dealing with new data, one of the first things we want to find out are the number of rows and columns. To find the number of rows, we can use our familiar `len` function on the data frame:

```python
len(df)
```

When we run the above on our cookie budget dataset, the output should be five. That means we have five rows. Each row represents a specific month of spending.

To get both the number of rows and the number of columns, we can use the `shape` attribute on our dataframe. (This is an attribute and not a method, so we don't use parentheses.)

```python
df.shape
```

This returns a list-like object that tells us the number of rows and the number of columns, respectively. The output should be `(5, 3)`., meaning we have five rows and 3 columns.

## Finding Column and Row Names

To return just the column names from our dataset, we can use the following:

```python
df.columns
```

This returns an index (another list-like object) with our column names. This also provides us with a way to find the number of columns in one step:

```python
len(df.columns)
```

The above uses the `len` function on our index (list-like object) of columns. (You'll find that we'll start combining more and more of what we learn together as we go on, so it's important to keep track of what each function, method, and attribute do as we go on.)

Rows also have names, and we learned about this when we worked with the Pandas series. We store row names or identifiers in the index of the dataframe or series. Let's pull out the index now:

```python
df.index
```
You should get the following as output:

```python
RangeIndex(start=0, stop=5, step=1)
```

That's pretty weird output, but this is Python's way of describing that the index is a count that starts at 0, stops at 5, and goes up by one each time. Basically, our index is a list-like object that counts up from 0, which is not really that useful to us.

What does a good and useful index look like? Typically, we like to use something unique to each row, preferably that is identifying. In our case, we know our data represents our monthly budget. Each row represents a month. Since the dataset is small, the months are also unique. For now, months would make for the best index. Let's replace our non-useful index with a better one:

```python
df.index = df.month
```

In the above, we assign the index just like we assign a variable. If you try using `df` by itself to find the representation of the dataframe, you'll find that the first item on each line (the left column) has been replaced by the month. Replacing the index with something more useful has a number of advantages and makes the data easier to interpret.

## Working with Columns

Probably one of the most frequent operations we'll make on a dataframe is to pull out a specific column as a series. Let's pull out our `cookie_budget` column:

```python
df.cookie_budget
```

That's our `df` variable, a dot, then cookie_budget, with an underscore between cookie and budget.

In the above, we simply use the dot syntax as if the column were an attribute of the dataframe. You should get back your budget column as a Pandas series. You'll find you can perform operations on the column just like it were any series. Try the following:

```python
df.cookie_budget.mean()
```

Performing the above, we find that the average cookie budget over the course of these five months is 2.8. Try taking a few minutes now to test out our other series methods on different columns. (For example, `min`, `max`, `median`, and so on.) This technique (pulling out a column and doing something with it) is extremely common in Pandas.

## Doubling Our Budget

Hey, I like cookies. You like cookies. So why don't we throw caution to the wind and double our monthly budget for cookies?

Try the following:

```python
df.cookie_budget * 2
```

In the above, we pull out the `cookie_budget` column and multiply it by `2`, just like we would do any math in Python. The result should be the representation of our `cookie_budget` column as before, but now with each value doubled. (If you hadn't noticed before, you'll also find that the series now uses the month as the index. When we pull out a column, the index of the dataframe is used.)

That's fine, but we have a problem. If we try using `df` by itself, we'll find that the `cookie_budget` column hasn't changed. That's not good, because we really want more money to spend on cookies.

To overwrite the previous column, try the following:

```python
df.cookie_budget = df.cookie_budget * 2
```

That's our `df` variable, a dot, our `cookie_budget` column name, a space, an equals sign, a space, our `df` variable, a dot, a space, an asterisk for multiplication, a space, and the number `2.

In the above, we multiply our `cookie_budget` column by 2 as before, but now we reassign the column to the new values. This uses the same syntax as assigning a variable. 

Now that we've made the wisedecision to double our cookie budget, let's see what percentage of our monthly budget should be spent on cookies. Try the following:

```python
df.cookie_budget / df.budget
```
The resulting series tells us the percentage of each month's total budget we'll be spending on cookies.

## Extracing Rows

It's not an operation we use as frequently as pulling out columns, but we can also pull out specific rows. We'll learn two methods for extracting a specific row from a dataset.

First, let's pull out a row using a unique value from the index:

```python
df.loc["June"]
```
That's our `df` variable, a dot, an opening square bracket, double quotes, the word `June`, double quotes, and a closing square bracket.

The loc attribute combined with the slicing syntax (square brackets) lets us look up a row by the item in the index for that row. This outputs a series where the values are the values from that row and the index is the column name of each value.

If we know the numerical location of a row, we can use the following:

```python
df.iloc[0]
```

That's our `df` variable, a dot, the `iloc` attribute, an opening square bracket, the number `0`, and a closing square bracket. This outputs the first (or 0th) row in the dataframe.

## Other Useful Methods

You may wish to experiment with the following method:

```python
df.info()
```

The `info()` method prints out a summary of the dataframe that will let you know the length of each column, it's name, and its data type. If you're using a screen reader, this is probably too much information to want to parse, but it's a commonly used method to get an overview of a dataset.

[<<< Previous](creating_dataframe.md) | [Next >>>](synthesis.md)
