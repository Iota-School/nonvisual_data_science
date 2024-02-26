[<<< Previous](intro_to_sonification.md) | [Next >>>](introduction_to_astronify.md)

# Preparing Data for Sonification

In this section, we will make synthetic data to sonify, or represent as sound, using Astronify in the next section. In doing so, we will practice performing math upon arrays and will introduce Astropy Tables. You will frequently hear me refer to "synthetic" or "simulated" data in this section; by these terms, I simply mean that we created the data ourselves and that it is not "real" data that comes from measurements and observations.

Let's start by importing our favorite packages: Pandas and Numpy.

```python
import pandas
import numpy
```

Now, let's make some data to put in a DataFrame that we will call **df**. We're going to multitask and actually make this DataFrame hold the simulated data that we will use to test out Astronify. In particular, we're going to make one column called "x" that will be an evenly spaced array of 100 numbers between 0 and 10; these will be our independent or "x-axis" values. Then we will take advantage of the fact that we can do math with arrays to make a variety dependent columns that are functions of x. For our purposes here, we will make functions of x that include two types of linear function (one with a positive slope and one with a negative), a quadratic function or parabola, an absolute value function, and a sine of x. By sonifying each of these different functions, we will begin to get an intuition for how each of them sound when sonified.

The idea of sonifying simple algebraic functions is inspired by Scott Fleming's talk "Hearing the Light with Astronomy Data Sonification" at [the Space Telescope Science Institute's Day of Accessibility](https://iota-school.github.io/day_accessibility/), which I highly recommend checking out. (Patrick also gave a talk there!)

## Numpy's linspace Function

How are we going to get that nice array of 100 evenly-spaced x values? Typing out 100 values sounds terribly tedious, not to mention that it would be very easy to make a mistake. Fortunately, Numpy has a function called linspace that will do the work for us! As inputs, we give linspace three parameters: the start value for our array, the stop value for our array, and the number of evenly-spaced values that we want.

Let's give it a try!
```python 
numpy.linspace(0,1,5)
```

Your IPython console should have just returned an array with five evenly-spaced numbers from 0 to 1. Let's try another:

```python 
numpy.linspace(0,10,10)
```

Now we get 10 evenly-spaced values from 0 to 10! Cool! Now, I said we wanted our independent variable values to range from 0 to 10 but to include 100 numbers. That just requires a small change to the third parameter in the linspace function from the line of code we just ran. Let's also save the output as a variable, x, so that we can continue to use it.

Note that I have included some comments marked by the pound symbol in my code as commentary, but you do not need to include these comments when you reproduce the code in your own IPython terminal! Commenting your code is good practice for readability, but the comments themselves do not affect how your code runs--they are just comments!

```python 
# First we want to make an array of 100 evenly spaced values from 0 to 10 using numpy's linspace function.
# This will be our x array (x-axis values).
x = numpy.linspace(0, 10, 100)

# and let's just print it out to check
x
```

## Making Simulated Data to Sonify

Now that we have our independent variable x, we're going to make a linear function of x with a positive slope and one with a negative slope, a quadratic function of x, an absolute value function, and a sinusoidal (sine) function.

I go pretty rapid fire through the math here, but the comments do explain each step.

```python 
# Now we will make functions from this x array.
y_linear = x # linear, y = x
y_neg_linear = -x # linear with negative slope, y = -x
y_parabola = -(x-5)**2 + 1 # parabola or quadratic, note that ** denotes an exponent in Python
y_abs = -abs(x-5) + 1 # absolute value using the abs() function
y_sine = numpy.sin(2*x) # sine function using Numpy sin()
```

Each of these new variables contains an array of dependent values that follow a function of x. They each contain 100 values, just like x. Let's take a look at just a few.

```python 
y_neg_linear
```

Note that your IPython console just returned 100 values that are the negatives of each x value. Let's try another.

```python 
y_sine
```

This one might be a bit harder to interpret, but those of you who recall some of your algebra classes might recognize these values as following a sinusoidal pattern.

## Putting the Data in a DataFrame

Now let's make each of these arrays, including x, a column of a new Pandas DataFrame called df. Note that I add each column individually because I find it less confusing than adding them all at once when the DataFrame is created.

```python 
# Now let's construct a pandas DataFrame with each of these arrays as a row.
df = pandas.DataFrame()
df['x'] = x
df['linear'] = y_linear
df['neg_linear'] = y_neg_linear
df['parabola'] = y_parabola
df['abs'] = y_abs
df['sine'] = y_sine
```

## Astropy Tables
Before we actually get to work testing the Astronify sonification package, we will need to briefly introduce a new type of object: Astropy Tables. Why? Well, the sonification package we're using, Astronify, is made by astronomers, for astronomers, to be used on astronomy data. Thus, it takes Astropy Tables--a typical object used to store data by astronomers--as the input for the data which it sonifies.

Astropy is a Python package widely used by astronomers with many functionalities ranging from unit conversions to coordinate system transforms to data management. Tables are an object type in Astropy that, for our purposes here, are exceptionally similar to Pandas DataFrames. (Hurray! That will make things easier.) There are some differences between the two--for instance, we can use units in Astropy Tables--but right now we just want to be able to convert DataFrames to Tables. The good news is that Astropy has a built in function to do just this! It's called (creatively) **from_pandas**.

## Bringing it all together: making an Astropy Table from the Pandas DataFrame

Finally we have come full circle and are ready to make that Astropy Table. Fortunately, with the from_pandas() method this is just one line of code (after the import statement):

```python
# first import Table from Astropy
from astropy.table import Table

tbl = Table.from_pandas(df)
```

*Note that Table begins with a capital "T"; if you use a lowercase it will no longer work.*

Congratulations, you now have a Table ready to sonify with Astronify! Let's explore it a little bit. First, we can print out the column names in the Table:

```python
tbl.colnames
```

And they're the same as those from the DataFrame!

Let's try checking on the data inside one of those columns.

```python
tbl['x']
```

As you can tell, the "x" column contains the data from that original x array that we made and that we had added to the DataFrame df. Success! So, in summary, Astropy Tables are similar to Pandas DataFrames in the sense that they have named columns which each contain rows of data.

Now we're all ready to start with the sonification itself.

## Just in case...

If you did not quite catch all of the data preparation here or had some trouble with all of the code flying around, not to worry! You can just download a .csv file with all of the data that we just made by following the code below.

~~~python
url = 'https://github.com/sgkane/sonification_tutorial_one/blob/main/prepared_data.csv?raw=true'
df = pd.read_csv(url,index_col=0)
tbl = Table.from_pandas(df)
~~~

[<<< Previous](intro_to_sonification.md) | [Next >>>](introduction_to_astronify.md)
