[Next >>>](representing_data.md)

# Types of Data

In the last session, we learned about how Pandas handles one- and two-dimensional data, and we used statistical methods such as the mean, median, and standard deviation to gain an insight into one-dimensional data such as the price column in our Airbnb dataset. Up to this point, we've mostly worked with numerical data, such as prices or budget items. It's time to look at some other types of data and how to work with them in Pandas.

## Types of Data

Here are a few types of data we'll encounter in this session. 

- `Categorical` — Categorical data takes the form of textual or numeric data that is frequently repeated. Categorical data is used to indicate that the entity belongs to a specific category. In our Airbnb dataset, the `neighbourhood_group` column provides a good example of categorical data. The column consists of a set of five values (the five boroughs in New York City) and indicates the boroughs that a specific listing belongs to.
- `Time` — This form of data represents points in time. This can take the form of a date, a time, or a date and time, and can come in a variety of formats.
- `Numeric` — This is data for which statistical methods such as mean or standard deviation are meaningful.
- `Descriptive` or `Nominal` — This form of data does not have meaningful  (as with numeric or time) and does not represent a meaningful set of categories. It is often unique or nearly unique. This form of data are often used to identify a row. Email addresses, ID numbers, or our Airbnb listing names fall into this category.

In addition to the above, there are types of data that you may encounter in a dataset, but that you are even more likely to create for yourself in the process of analyzing other forms of data.

- `Count` — Counts are created by enumerating how many of each value occurs. For example, if we have categorical data indicating whether a set of animals is a cat, dog, or bird, count data would let us know how many of each occur in the dataset.
- `Binary` or `Boolean` — This form of data lets us know whether or not something is true for each entity. For example, in our Airbnb dataset, we might create an `is_brooklyn` column that would tell us whether a listing is in Brooklyn, or an `is_expensive` column that tells us that the price is above $500 per night. Most other forms of data can be transformed into binary or boolean data if we choose.

Types of data are not formalized in data science, and you'll hear different names and organizational systems for categorizing types of data. For example, some data scientists consider data to be either numeric or categorical. 

## Types of Data Versus Python's Data Types

In the first session of this workshop series, we learned about Python's data types such as strings, lists, and Boolean's. The types of data described above are broad concepts, while Python data types are specific to Python. For example, categorical data can take the form of a string or an integer, as can time data.

[Next >>>](representing_data.md)
