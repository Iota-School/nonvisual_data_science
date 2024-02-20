
# Indexing and Boolean Data

In the previous section, we learned about creating counts data as a useful intermediate step in an analysis. You may sometimes encounter counts data in a dataset you're analyzing. For example, our Airbnb dataset has a column, `calculated_host_listings_count`, that shows how many other rentals were posted by the host of each listing. However, you'll most often work with counts data derived from other fields in your dataset as we did with counts of the `neighbourhood_group` column.

Another type of data frequently used as an intermediate step in an analysis is binary data. This data represents whether something is true or false, with no other possible options. In Pandas, this type of data takes the form of a series containing boolean values (`True` and `False`).

## Creating a Boolean Series

Let's say we want to analyze ultra-pricey Airbnb listings, those that are over $1000 per night. We'll start by creating a boolean series. To create this series, Pandas will look at our `price` column, and if the price is above `1000`, it will set the value in the new series to `True`. If the price is below `1000`, it will set the value to `False`. 

Try the following:

```python
price_bools = df.price > 1000
```

The result, now assigned to `price_bools`, will be a series containing only `True` and `False` values. Each `True` will correspond to a location in the `price` column where the price is greater than `1000`.

The boolean series is only somewhat useful on its own. We can try using our `value_counts()` method to find out how many `True` and `False` values we have in the series:

```python
price_bools.value_counts()
```

The result shows that only 239 listings are over $1000 per night.

One trick useful with a boolean series is to ask for the mean using the `mean()` method. This will tell us the proportion of items in the series that are `True`.

```python
price_bools.mean()
```

In this case, the proportion is `0.0048`, indicating that only about half a percent of the listings are over $1000 per night.

## Creating a Data Subset

The true power of the boolean series is that it can be used to create a subset of your dataframe for only those values for which your proposition is true. In our case, we can create a new dataset that contains only those listing for which the price per night is greater than $1000.

Run the following:

```python
expensive_df = df[price_bools]
```

We've now created a new dataframe assigned to `expensive_df`. Let's check how many rows are in this new dataframe:

```python
len(expensive_df)
```

This new dataset contains only 239 rows. The listings in this new dataset all have a nightly price of over $1000.

We can now use this derived dataset to answer new questions. For example, what neighborhood has the most Airbnb listings that are over $1000 per night?

```python
expensive_df.neighbourhood.value_counts().head()
```

This shows that the three neighborhoods with the largest number of rooms above $1000 are the Upper West Side, Midtown, and the West Village.

## Categorical Subset

The subset of our data we created above made a distinction based on numeric data (the price). Let's try creating a new subset based on a column with categorical data.

I live in New York City, and my neighborhood is Woodside. Let's learn what the mean and median Airbnb prices are in my neighborhood.

First, let's create a boolean series. An item will be `True` if it corresponds to an item in the `neighbourhood_group` column that has the value `Woodside`.

```python
woodside_bools = df.neighbourhood == 'Woodside'
```

Once we have the boolean series, let's immediately use it to create a subset of the original dataframe:

```python
woodside_df = df[woodside_bools]
```

Now we can use the new Woodside dataset to check the mean and median price of an Airbnb room in Woodside:

```python
woodside_df.price.mean()
```

```python
woodside_df.price.median()
```

The median price of a night in Woodside is (or was)$60. Seems like a pretty good deal.




