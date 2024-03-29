[<<< Previous](scaling_sonifications.md) | [Next >>>](temperature_models.md)

# Dealing with Missing Values

Real data is often messy. It can have errors and strange formatting and a myriad of other issues that can be difficult to even predict before you explore the data yourself. One of the most frequent issues you will encounter is missing values in your dataset, which we will discuss how to handle now.

First, let's try sonifying the temperature data from New York City. Hopefully these lines of code are quite familiar right now, so I'll include all of the steps of making the sonification together:

~~~python
soni_nyc = SoniSeries(tbl, time_col='timestep', val_col='new_york_city_temp')
soni_nyc.sonify()
soni_nyc.play()
~~~

Woah! That sonification does not sound like the others! I hear these irregular really low notes in the sonification. Those repeated outlier notes are even more obvious if you invert the pitch mapping of the sonification such that low values are represented by high pitches, and vice versa. The code to invert the pitch for our sonification looks very similar to the code we used to change the zero point because we are just changing another pitch map argument:

~~~python
soni_nyc.pitch_mapper.pitch_map_args['invert'] = True
~~~

We've just set the invert pitch map argument to True (with a capital T!) as opposed to its default value of False. To hear the difference, we'll need to re-sonify and play the sonification:

~~~python
soni_nyc.sonify()
soni_nyc.play()
~~~

Listening to the sonification, note how those repeated low notes we heard before are now repeated very high notes; that's the pitch inversion. What's happening? Let's look at the data itself in our DataFrame df to see what's happening, starting by looking at the average:

~~~python
df.new_york_city_temp.mean()
~~~

...and the maximum recorded NYC temperature...

~~~python
df.new_york_city_temp.max()
~~~

...and finally the minimum:

~~~python
df.new_york_city_temp.min()
~~~

And therein seems to be the problem! I get an output of -99.0, and having spent some time in New York City, I can fairly confidently say I've never heard of it getting to -99 degrees there!

What seems to be happening is that there are several days where we are missing temperature data for New York City, and in this particular dataset, those missing measurements are filled with a value of -99.0 because they are obviously not true values for the temperature. However, *Astronify* does not know that -99.0 represents a missing value, so such a low number is wreaking havoc on our sonification!

In the spirit of transparency, I replaced the missing values in the temperature columns that we have already used with a method called linear interpolation for our convenience when I made the file for us to use. One other common way you'll see missing values is via something called a Numpy NaN, which stands for "not a number." Some functions, especially Numpy and Pandas functions, will handle NaN values well and ignore them, as we would hope would be the case for missing values. However, some other functions will throw an error if the input contains a NaN, so it's good to be aware of their existence.

We can check if our data contains a NaN with Numpy's handy isnan() function:

~~~python
numpy.isnan(df.new_york_city_temp)
~~~

You should get out an array of Booleans (True or False values) in the same shape as df.new_york_city_temp that are False at positions where df.new_york_city_temp does not contain a NaN and True at positions in the array where it does contain a NaN. In our case, you should get a bunch of False values as output. Personally, I don't want to read through that whole array to check for any single True value, but we can easily check if there are any True values in an array with the .any() function:

~~~python
numpy.isnan(df.new_york_city_temp).any()
~~~

The .any() function will return a True if any values in an array are True (even if it's just one True in a thousand False values!) and False if there are no True values. In our case, you should get a return of False, which means that there are no NaNs in our dataset. All of the missing values seem to have been replaced with -99.0 rather than a NaN.

## Dealing with Missing Values in the Sonification

Alright, so we know what missing values are and how to find them, but how do we stop them from making a mess of our sonification? Fortunately, Astronify has a parameter in its pitch mapping algorithm that we can set to do this for us. The minmax_percent argument allows us to enter a minimum and maximum percent of the values that will be mapped to a pitch. Thus, if I set the minimum percent to 5, then the lowest 5% of values in our data will be excluded from the sonification. In our case, this means that those really low -99.0 values representing missing data won't be sonified. We're not as concerned about really high values here, so I'll make the upper bound of the minmax_percent 100, thus including even the highest temperature value from our data in the sonification. Note here that we set minmax_percent to be equal to a list qith two numbers: the lower bound and upper bound we want included in our data.

~~~python
soni_nyc.pitch_mapper.pitch_map_args["minmax_percent"] = [5, 100]
~~~

Tthen we can follow our favorite steps of sonifying the data and playing the sonification:

~~~python
soni_nyc.sonify()
soni_nyc.play()
~~~

Success! I hear some high notes, but not that same identical really high note over and over. Recall that the pitches in our sonification are still inverted, so high pitches still represent low temperatures!

[<<< Previous](scaling_sonifications.md) | [Next >>>](temperature_models.md)
