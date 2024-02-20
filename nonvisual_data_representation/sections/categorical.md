[<<< Previous](representing_data.md) | [Next >>>](indexing.md)
# Exploring Categorical Data

Categorical data is often represented visually using a bar or pie chart. However, it is also easily summarized in Pandas. In this section, we'll learn about approaches in Pandas that let us explore categorical data.

For the rest of this workshop, we'll be using our Airbnb dataset. You can read the dataset into Pandas with the following command:

```python
df = pandas.read_csv('https://bit.ly/nycbnb')
```
After running the above command, our Airbnb dataset will be assigned to the `df` variable.

## What is Categorical Data?

Let's attempt to explain categorical data in a less abstract way by working with our dataset. First, let's pull out the first five items from our `neighbourhood_group` column in the dataframe containing our Airbnb data:

```python
df.neighbourhood_group.head()
```

Remember that `head`()` shows us the first items from a dataframe or series, five by default.

The first five items are as follows:

```
0         Brooklyn
1        Manhattan
2        Manhattan
3         Brooklyn
4        Manhattan
```

Notice that both Brooklyn and Manhattan are repeated. This is the distinctive characteristic of categorical data. Each entity (a row in the dataframe) falls into one of a limited set of categories.

Let's use a new function to see how many unique categories there are in `neighbourhood_group`:

```python
set(df.neighbourhood_group)
```

This returns a list-like object (a set) with five items: `{'Bronx', 'Brooklyn', 'Manhattan', 'Queens', 'Staten Island'}`. The set function shows the unique values in a list, sequence, orother list-like object. In this case, we have five unique values each representing the borough where that specific Airbnb listing is located.

## Counts

A useful operation to perform on categorical data is to count the occurrences of each unique value. For example, we can count how often each borough appears in our `neighbourhood_group` column using the `value_counts()` method:

```python
df.neighbourhood_group.value_counts()
```

The output is as follows:

```
Manhattan        21661
Brooklyn         20104
Queens            5666
Bronx             1091
Staten Island      373
Name: count, dtype: int64
```

Our output is a new series. The index of the series are labels based on the unique values in the column. The series values are integers enumerating how many times each category appears in the column. This series tells us that there are more Airbnb listings in Manhattan than in Brooklyn, more listings in Brooklyn than in Queens, and so on.

## Replacing the Bar Chart

From a nonvisual perspective, this output is a decent replacement for a bar chart. Each line consists of a category and the number of occurrences of that category in the original series. If we were to create a textual representation of a bar chart produced by a sighted data scientist, we might consider using a format similar to this one.

One possible advantage a sighted person looking at a bar or pie chart might have would be quickly comprehending the proportions of each count in relation to one another. For example, the bar chart or pie chart would quickly show that the values for Manhattan and Brooklyn are fairly comparable (21661 versus 20104), and that there's a big drop between Brooklyn and Queens (20104 versus 5666). While this is actually relatively clear from the counts series we created above, we can improve on our analysis to get an even more immediate representation of the different proportions.

## Refining Our Counts Data

Let's create some more immediately comprehensible output of our `neighbourhood_group` counts. First, let's assign our previous counts series to a variable:

```python
neighbourhood_counts = df.neighbourhood_group.value_counts()
```

Now let's use the counts series to get the proportion of each value as a decimal:

```python
neighbourhood_counts / len(df)
```

In the above, `len(df)` is the total number of listings in our original dataset (`48895`). We divide each value in the series by this number. For example, for Manhattan, we divide `21661` by `48895`. This gives us `0.443011`, telling us that about 44% of the listings are in Manhattan. 

Reviewing our new output, the relations between the counts are even clearer. For example, `0.411167` or about 41% of listings are in Brooklyn, but only `0.115881` or about 12% of listings are in Queens.

This might be the most comprehensible output for understanding these proportions. However, Pandas provides other methods that give even more precise information. For example, we can use the `pct_change()` method on our `neighbourhood_counts` series to receive each value expressed as a change in percentage from the previous:

```python
neighbourhood_counts.pct_change()
```

In this output, the first value (Manhattan) is labeled `NaN`, or no data. The second value, for Brooklyn, is `-0.071880`. That tells us that the counts for Brooklyn are about 7% lower than the counts for Manhattan. The next value, for Queens, is `-0.807448`, showing a major drop of 80% between Brooklyn and Queens.

## Summing Up

In the above, we used a small number of Pandas methods to quickly figure out the proportions in a count of categorical data. This serves as a relatively strong replacement for bar and pie charts when working with data nonvisually. In visualization, bar and pie charts are at their best when showing a limited number of items, so parsing our outputs by reviewing line by line is not significantly slower than a visual scan, especially when we make sure of derived data such as decimal proportions and the percent change.

## FAQ

### How do I make a bar chart for my sighted colleagues?

```python
import matplotlib.pyplot as plt
plt.savefig('output.png')
```


### Is there a faster way to get proportions?

use normaliz=True

### Is there a way to see actual percentages rather than decimal proportions?

```
df.neighbourhood_group.value_counts(normalize=True).mul(100).round(1).astype('str') + '%'
```

[<<< Previous](representing_data.md) | [Next >>>](indexing.md)
