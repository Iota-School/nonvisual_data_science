[<<< Previous](line.md) | [Next >>>](../README.md)

# Changes Over Time

We've covered a great deal in this workshop. Let's conclude by bringing together a number of the techniques we've learned to accomplish something relatively challenging: tracking a change in a variable over time nonvisually.

## Creating a Time Column

One of the columns in our dataset, `last_review', indicates when the most recent review on a listing was posted. Let's track the number of listings last reviewed in each year, starting in 2011.

First, let's take a look at our `last_review'` column:

```python
df.last_review.head()
```

Notice that the dtype (Pandas data type) of the column is `object`. This means that Pandas couldn't automatically detect the type of data in the column. Let's create a new series where our data are recognized as dates:

```python
dates = pandas.to_datetime(df.last_review)
```

We now have a series assigned to the `dates` variable that is correctly recognized as time data. We can use a special attribute inside this series, `dt`, that allows us to access other methods and attributes related to date and time. Let's use this functionality now to extract the year for each listing:

```python
years = dates.dt.year
```

Let's count how many listings were last reviewed in each year:

```python
years.value_counts()
```

The resulting series tells us how many listings were last reviewed in a given year. Since later reviews supersede older reviews in this column, we can assume there is a large bias in the direction of recent years. However, the data suggest that Airbnb has grown in popularity in the period from 2011 to 2019.

## Replacing Line Charts

Line charts are commonly used to visualize a change over some ordered numeric data. The most frequent kinds of ordered numeric data used in line charts are times and frequencies. The above approach can be used to create output representing a change over time, and thus can replace a line chart in some circumstances. As we did when examining categorical data, we can also use the `pct_change()` method to get a better sense of ups and downs in the data:

```python
 years.value_counts().sort_index().pct_change()
 ```

The output here gives a sense of how the listing counts for each year changed over time. In 2012, the `last_review` count grew by 250% compared to the previous year. In 2018, the count grew by 88% compared to the previous year.

[<<< Previous](line.md) | [Next >>>](../README.md)
