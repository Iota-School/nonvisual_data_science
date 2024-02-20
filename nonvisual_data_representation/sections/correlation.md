[<<< Previous](indexing.md) | [Next >>>](line.md)

# Correlation

A common technique in data science is to determine the correlation between two numeric variables. Given two sets of numbers, how much does one set predict the value of another?

## Correlating Numeric Columns

A Pearson correlation describes the direction and strength of a relationship between two variables. 

In terms of direction, a correlation can be:

- Positive: An increase in one variable correlates with an increase in the other variable.
- Negative: A increase in one varaible correlates with a decrease in the other variable.
- No Correlation: One variable is not associated with an increase or decrease in the second variable.

A Pearson correlation is expressed in a decimal number from -1.0 to 1.0. If the number is negative, the correlation is negative. If the number is positive, the correlation is positive. A 1.0 indicates that the two variables are perfectly correlated, and a zero indicates that the two variables are not at all correlated.

## Finding the Correlation

Using Pandas, we can calculate the Pearson correlation between two columns containing numeric data. Let's try that now on two columns that seem like they might be related, 

```python
df.number_of_reviews.corr(df.reviews_per_month)
```

In the above, we use the `corr()` method on one of our columns, then pass in a second column.

The output, `0.5498675063773879`, suggests a moderate to strong correlation between these two variables. This makes intuitive sense—many reviews per month would seem to result in more total reviews. The variables are likely not fully correlated due to other relevant factors, such as the length of time the listing has been active.

Let's try a correlation on two more variables: the price and the number of reviews.

```python
df.price.corr(df.number_of_reviews)
```

The result, `-0.04795422658266219`, suggests that the two variables are uncorrelated or very weakly negatively correlated.

Scatterplots are often used to visualize correlative relationships between two variables. However, a correlation calculation between two variables as above can also give you significant information on the relationship. A visual scatterplot may sometimes indicate other patterns, such as the presence of outliers. Calculating measures of variability such as standard deviation, variance, and interquartile range (IQR) can also be helpful when exploring numeric data. 

[<<< Previous](indexing.md) | [Next >>>](line.md)
