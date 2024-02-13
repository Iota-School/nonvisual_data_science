[<<< Previous](../README.md) | [Next >>>](series.md)

# Dimensions in Data

Imagine we have a list:

```python
[10, 5, 8]
```

That's a list with three items (10, 5, and 8). In your mind, you can imagine these as points on a line going from left to right. The number 10 can be on the left, the number 5 in the middle, and the number 8 on the right.

This is what we call one-dimensional data. One-dimensional data is a sequence or list that does not contain other sequences or lists. The location in the sequence can be expressed with a single number.

 In Python, 0 would describe the location of 10, 1 would describe the location of 5, and 2 would describe the location of 8, since we start counting from 0. When we use number to describe locations like this, we call these numbers an "index." 

## Two-Dimensional Data

Imagine we have a new list:

```python
[
    ['January', 'February', 'March'],
    [10, 5, 8]
]
```

In the above, we create a list that itself contains two lists. The two lists each have three items.

This is two-dimensional data. To describe the location of an item in one of these two lists, we now need two numbers. The first will tell us which list the item is in. The second will tell us the location of the item within that list. 

If we think about these two lists spatially, we can place each list on a line from left to right and the items on each list on a line from top to bottom. If the data were a plane, each list could be placed on the X axis, and each item within the lists could be placed on the Y axis. 

If you've used spreadsheet software before, you can imagine each list as a column in a spreadsheet. That means if we turned the above data into a spreadsheet, it would have two columns and three rows. Columns go left to right (X axis), and rows go top to bottom (Y axis).
## Other Dimensions

We can create data that exists in more than two dimensions. If we replaced each of the items in the above list (i.e., 10, 5, and 8 and January, February, March) with further lists, we'd have created three-dimensional data. In that case the locations of items within those lists would need to be described using three numbers (X, Y, and Z). You can keep going with this principle and create data in any number of dimensions. We won't be working with that kind of data in this tutorial, but we call this N-dimensional data (data in any number of dimensions), and this kind of data has many applications.

Technically, any piece of data that is not a list or sequence is an example of zero-dimensional data. That means that no numbers are needed to describe its location in space. While we use zero-dimensional data all the time, there isn't much need to describe it this way.

[<<< Previous](../README.md) | [Next >>>](series.md)
