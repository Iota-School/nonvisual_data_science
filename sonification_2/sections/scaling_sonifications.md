[<<< Previous](sonify_temperature.md) | [Next >>>](missing_values.md)

# Scaling a Sonification

## Sonifying Delhi's Daily Temperatures

Next, let's sonify another column of our data, this time Delhi's daily temperatures. We can follow the same steps to make a new instance of the SoniSeries:

~~~python
soni_delhi = SoniSeries(tbl, time_col='timestep', val_col='delhi_temp')
~~~

And finally, sonify and play the sonification!

~~~python
soni_delhi.sonify()
soni_delhi.play()
~~~

Once again, I very clearly hear the cycles in temperature marking the changes in seasons. Let's play the Philadelphia temperature sonification to compare them side-by-side.

~~~python
soni_philadelphia.play()
~~~

They sound pretty similar to me! Now, I am no weather or climate expert, but I would certainly expect Delhi, India to be hotter than Philadelphia, Pennsylvania, but that isn't clear from the sonifications, which represent higher temperatures as higher pitches. I suggest that we go and check the data for the Delhi daily temperatures to confirm that they are generally hotter than those for Philadelphia.

When we go back and check the data, I'm going to use our DataFrame df rather than the Astropy Table tbl that we have been using for our sonifications because the syntax for Tables is slightly different than that for DataFrames, and there's really no need to learn the syntax for Astropy Tables unless you plan to be an astronomer! Both the DataFrame and Table contain the same data, anyway, so we should be able to use either.

Alright, just as we did for the Philadelphia daily temperatures, let's check the average Delhi temperature:

~~~python
df.delhi_temp.mean()
~~~

I get an average daily temperature in Delhi of 76.965 degrees--about 20 degrees hotter than Philadelphia's average temperature!
We should also probably look at the maximum value:

~~~python
df.delhi_temp.max()
~~~

For which I get an output of 103.7--definitely higher than Philadelphia's maximum temperature of 92.9 degrees.
And the minimum value:

~~~python
df.delhi_temp.min()
~~~

And here I get an output of 43.9.
That for sure seems hotter than Philadelphia overall! So why don't we hear that in the sonification?

## Pitch Scaling in Astronify Sonifications

The reason we can't hear Delhi's temperatures represented at a higher pitch than Philadelphia's is because each sonification object Astronify makes is scaled independently of each other such that all data values are represented by pitches within the audible hearing range. By default, Astronify represents the median of the data as 440 Hertz and maps the rest of the values such that they are represented by pitches between 100 to 10000 Hertz. Now again, because each sonification is treated independently, this means that the two very different medians of the Philadelphia and Delhi daily temperatures are both being mapped to 440 Hertz, thus why our sonifications sound so similar.

Fortunately, Astronify allows us to change the value of what they call the "zero point", or the value that is represented by that "central pitch" of 440 Hertz, so that it is a set value rather than the median of the data. We can do this for the Delhi temeprature data. What I want to do is set the zero point of the Delhi temperature sonification to be the same as the zero point of the Philadelphia temperature sonification. That means that we need to know the median of the Philadelphia temperature data, as that will be the default zero point of the Philadelphia temperature sonification. Let's check what it is:

~~~python
df.philadelphia_temp.median()
~~~

I get an output of 57.0, so we want to set the zero point of our Delhi temperature sonification to be 57 to be consistent with the Philadelphia temperature sonification. We can do this by changing the "zero_point" argument in the pitch mapping arguments via the (rather long) line of code below:

~~~python
soni_delhi.pitch_mapper.pitch_map_args["zero_point"] = 57
~~~

Here, I've set the zero point to be represented by the 440 Hertz pitch to be 57 degrees. If you're feeling technical, you can skip a line of code here by directly setting the zero point of the Delhi temperature sonification to be equal to the median of the Philadelphia temperature data:

~~~python
soni_delhi.pitch_mapper.pitch_map_args["zero_point"] = df.philadelphia_temp.median()
~~~

Regardless of the way you re-set the zero point, we'll need to re-sonify and play our data to hear the change:

~~~python
soni_delhi.sonify()
soni_delhi.play()
~~~

You can play the Philadelphia temperature sonification again for comparison:

~~~python
soni_philadelphia.play()
~~~

Can you hear the difference? I certainly can--the Delhi temperature sonification is much higher pitched!

Note here that due to how the Astronify sonification algorithm works, we can't easily make the value-to-pitch mapping identical for the Delhi and Philadelphia temperature data. This is why it's so crucial that we check the minimum and maximum values of our data to get a sense for how the scaling works. This issue of scaling is not totally unique to sonification, as similar visualizations of difference datasets often have different axis scalings that can be confusing to sighted users of those visualizations. However, unlike visualizations, our sonification does not include automatic labels for the minimum and maximum values and how they are mapped to the pitches. The issue of "axis labels" in sonification is a very interesting one to me, so please do feel free to reach out or to attend office hours if you are interested in chatting more!

Frankly, I find this modified Delhi temperature sonification to be rather unpleasant on the ears and less informative than the original. You don't need to rescale sonifications, so long as you are aware that two different sonifications might be on different scales! This is another reason to take a look at your data before you sonify it.

We won't cover them all in detail here, but you can read more about Astronify's sonification parameters in the section with that name.

[<<< Previous](sonify_temperature.md) | [Next >>>](missing_values.md)
