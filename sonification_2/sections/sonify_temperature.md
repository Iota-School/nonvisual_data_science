# Sonifying Temperature Data

Alright, now that we have imported and explored our data a bit, we're ready to sonify it--after a few more quick steps!

## Preparing to Sonify

There are two things we'll need to do before we can sonify the data. First, our dates are spread across three different columns, which will be difficult for Astronify to parse if we want to sonify temeprature versus time. Thus, we'll add an extra column that numbers each row from 0 to 9265 in chronological order. Because Astronify doesn't care about the actual value of the time columns, only about the relative distance between each time--what I will call the timestep--we can just label the column with evenly spaced numbers and use that as the time for the sonification since each data point represents a day, thus making the original timesteps also evenly-spaced.

Fortunately, Patrick already showed us in a previous tutorial how to add an index from a range of evenly-spaced numbers:

~~~python
df['timestep'] = pandas.RangeIndex(start=0, stop=len(df), step=1)
~~~

What we've done here is added a column to the DataFrame df with the name "timestep" that is filled with evenly-spaced numbers from 0 to the length of the DataFrame in steps of 1. We are following the Python convention of numbering beginning from 0 rather than 1. Note that I've used brackets and quotation marks to create the column name amd assign values to it. This syntax works better for adding a new column to a DataFrame, whereas either this format or the more familiar df.timestep formatting works quite well for looking at what is inside a column. You can check that our timestep column looks correct by using the head() and tail() methods that we've used before:

~~~python
df.timestep.head()
~~~

You should get an output of the first five rows of the new timestep column, which should indeed contain the numbers 0 to 4. Next, let's check the end of the column:

~~~python
df.timestep.tail()
~~~

And here you should get the output of the last five rows of the column, containing the numbers 9260 to 9264. All looks good here!

Now, recall that Astronify wants Astropy Tables, not Pandas DataFrames, as its data input. As we did in the last tutorial, we can make a Table, which I will call tbl, from the DataFrame df using Astropy's from_pandas function. We will also need to first import the Table class from Astronify:

~~~python
from astropy.table import Table # import the Table class
tbl = Table.from_pandas(df) # create the Table tbl from the DataFrame df
~~~

Recall that the pound symbol marks a comment that has no effect on the code itself. It's probably good to check that all of our columns from the DataFrame made it over to the Table, as we did last week:

~~~python
tbl.colnames
~~~

And your output from the line above should confirm that the columns in tbl are the same as those in df!

## Sonifying the Philadelphia Temperature

Our data is ready for us to sonify using Astronify! We'll follow the same steps we took last week to sonify our synthetic data, starting with importing the needed SoniSeries class from Astronify:

~~~python
from astronify.series import SoniSeries
~~~

Next, we will make an instance of the SoniSeries class containing the data in tbl. Remember that we need to tell the SoniSeries class what the names of our time and value columns are (in this case, they will be our timestep and Philadelphia temperature columns).

~~~python
soni_philadelphia = SoniSeries(tbl, time_col='timestep', val_col='philadelphia_temp')
~~~

Unlike last week, I'll leave the note spacing at its default setting of 0.01 seconds between notes. This is rather a long sonification with a lot of data points, so I don't want to slow it down. I actually think the sonification sounds a bit better if you set the note spacing to 0.08, but that's a matter of personal preference, so feel free to test it.

Now we can make the sonification and play it!

~~~python
soni_philadelphia.sonify() # make the sonification
soni_philadelphia.play() # play the sonification
~~~

What do you hear? Remember that pitch is mapped to our value column such that higher pitches represent higher daily temperatures in Philadelphia, and lower pitches represent lower daily temperatures. Most clearly, I hear a repeating cycle of higher and lower pitches--this is the cycle of the seasons repeating over the years with colder temperatures in the winter and hotter temperatures in the summer! If you listen again and count the cycles, can you hear the 15 cycles in temperature representing the 15 years of data that we have here?

~~~python
soni_philadelphia.play()
~~~
