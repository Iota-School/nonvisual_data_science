[<<< Previous](introduction_to_astronify.md)

# Testing Astronify

We've finally reached the moment you've been waiting for—we're going to make our own sonifications! In particular, we are going to sonify the functions that we made in the previous module to get a sense of what each of them sounds like sonified.

## Step one: Import Astronify

Good news: if you have already installed Astronify, this is a one-line process! If you have not already installed Astronify, please revisit that module. In Anaconda Prompt, start IPython by typing IPython. We want to import the SoniSeries class which is what we use to actually make the sonification. *Note that this is all one word and that the S beginning both Soni and Series are capitalized.*

```python 
from astronify.series import SoniSeries
```

## Step two: Sonify the representations of the functions we made in the previous module

And now we can sonify the data using Astronify's SoniSeries! We will create a new instance of the SoniSeries class--a new object--for each function we wish to sonify, starting with the linear function with a positive slope.

Because Astronify is made for light curves, by default it expects the dependent variable or x column to be called 'time' and the independent variable or y column to be called 'flux'. We are just going to tell it to expect different names--in this case the names we have given our columns in the Table--using the time_col and val_col parameters, which correspond to x and y, respectively. We'll also adjust the note spacing just so it is a bit slower and easier to listen to than the default.

```python 
# create a sonification (SoniSeries) object for the linear function
soni_linear = SoniSeries(tbl, time_col='x', val_col='linear') # create a SoniSeries object
soni_linear.note_spacing = 0.05 # adjust the note spacing
soni_linear.sonify() # make the sonification
soni_linear.play() # and play the sonification
```

Now we will repeat the process for each of the other functions we represented in our table. Note that I name the sonification for each function something different so that we do not overwrite any of our previous sonifications.

Next: the linear function with inverse slope:
```python 
soni_neg_linear = SoniSeries(tbl, time_col='x', val_col='neg_linear')
soni_neg_linear.note_spacing = 0.05
soni_neg_linear.sonify()
soni_neg_linear.play()
```

Sonifying the quadratic function / parabola:
```python 
soni_parabola = SoniSeries(tbl, time_col='x', val_col='parabola')
soni_parabola.note_spacing = 0.05
soni_parabola.sonify()
soni_parabola.play()
```

Sonifying the absolute value function:
```python 
soni_abs = SoniSeries(tbl, time_col='x', val_col='abs')
soni_abs.note_spacing = 0.05
soni_abs.sonify()
soni_abs.play()
```

Make note of the difference between the sonifications of the quadratic and absolute value functions. Can you tell them apart? (Hint: the absolute value function has a much sharper turnaround halfway through than the quadratic function, which changes more gradually.)

And finally, the sine function:
```python 
soni_sine = SoniSeries(tbl, time_col='x', val_col='sine')
soni_sine.note_spacing = 0.05
soni_sine.sonify()
soni_sine.play()
```

Now we have successfully sonified each of the functions we represented! Can you tell them apart? Try playing them side by side to test yourself and develop an intuition for how each function sounds. Now that you have created each sonification, you just need to use the final "play" method to play them again. For instance:

```python 
soni_parabola.play()
```

## Step three: Making more "realistic" data

The sonifications we made so far are very helpful for understanding how Astronify represents data as sound, and they give us an intuition for the behavior of each of the functions. If we were teaching an algebra class, this would be plenty; sighted students spend a great deal of time learning an intuition for visualizations of these same functions (i.e. learning to read graphs). However, this is a data science tutorial series, and the reality is that real data will rarely, if ever, be as "clean" as the functions we just sonified. Real data tends to be what I call "noisy" (a fitting description given that we are sonifying it!) Rather than following a perfectly clear pattern, data tends to vary up and down for a variety of reasons.

For instance, suppose we have data for the measured rainfall per day in inches over the course of a year. There will probably be some overall pattern to the data because rainfall varies by season and thus is not completely random, but each day will not follow that trend perfectly. Even in the rainy season, some days will be sunny, and even in the driest time of the year, some days might still see rain. Moreover, there might be some error in how we measure the rainfall that could add to the "noise" of the data because each day's measurements are not perfectly accurate. The data is not going to follow our perfect annual rainfall pattern to a "T".

To emulate the noisiness of real data, we are going to add noise (aka a random increase or decrease of each value) to our representation of the parabola. To do this, we will use Numpy's random.normal() function, which has three parameters that we will use:
* loc: defines the center or mean of the distribution from which random numbers will be drawn
* scale: defines the standard deviation of the distribution of random numbers (ex. how far away we tend to get from the center of the distribution of random numbers)
* size: how many random numbers we want

So, the random.normal() method will return an array of *size* random (or pseudo-random, but don't worry about that for now!) numbers centered on *loc* and with a standard deviation of *scale*. Let's try it out: 

```python 
numpy.random.normal(loc=0, scale=1, size=100)
```

We get out an array of numbers that are all roughly close to zero, maybe ranging as far as 2 or 3 from 0 in either direction. To us, the human user, they seem pretty random!

Now we will add these random numbers to our parabola array, make that array with noise a new column in the Astropy Table, and sonify the new column with Astronify:

```python 
noise = numpy.random.normal(loc=0, scale=1, size=100)
y_parabola_noise = y_parabola + noise
# add this as a new column to the Table
# This works just like a DatFrame!
tbl['parabola_noise'] = y_parabola_noise
# and sonify!
soni_parabola_noise = SoniSeries(tbl, time_col='x', val_col='parabola_noise')
soni_parabola_noise.note_spacing = 0.05
soni_parabola_noise.sonify()
soni_parabola_noise.play()
```

Can you still hear the parabola shape in the sonification? Try increasing or decreasing the *scale* parameter in random.normal to change the noisiness of the data and explore how the sonification changes. Is there a point at which the data is too noisy for you to hear the parabola in the sonification?

[<<< Previous](introduction_to_astronify.md)
