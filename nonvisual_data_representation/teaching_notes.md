# Nonvisual Data Exploration and Representation Teaching Notes

## Types of Data


## Categorical Data

Read in Airbnb Data  
df.neighbourhood_group.head()  
Show neighbourhood_group has repeated values
Explain categorical data
Use set function
Count occurrences using value_counts
Replacement for bar chart?
Sighted advantage in seeing relations?

Refining count data
Save counts to varaible neighbourhood_counts
Divide to get proportions
neighbourhood_counts / len(df)
Also use percent change:
neighbourhood_counts.pct_change()

faq:
creating bar chart visualizations
skipping the divide step
creating tidy percentages

## Indexing

Counts as intermediate step
Binary as another intermediate step
Describe binary data
Create a boolean series of items over $1000
Create price_bools
Do value_counts and mean on price_bools
Create expensive_df using indexing
Show the neighbourhoods with the most listings over 1000
expensive_df.neighbourhood.value_counts().head()


Categorical subset
Create woodside_bools
Create woodside_df
Get mean and median price
possibly show funny cheap room names

## COrrelation

Explain correlation is relationship between two variables
Explain postive, negative, no association
Explain strength of association
Explain the -1 to 1 scale
Perform correlation on number_of_reviews and reviews_per_month
Run correlation on price and number of reviews

## Time

Look at last_review
Convert last_review to datetime
dates = pandas.to_datetime(df.last_review)
Extract only the years to a variable
years = dates.dt.year
Get value counts of years
Using pct_change to approximate a line chart

## Conclusion

What is easy to replace?
What hard to replace?
Advantages of interactive approach: you can always build on answers. Model can always be extended. Very flexible.
Disadvantage: Not as immediate. Not as good for collaboration with sighted or persuasion. Some types of insights are harder to access or take longer
You might need to actually know what you're doing, but that's mostly a good thing
