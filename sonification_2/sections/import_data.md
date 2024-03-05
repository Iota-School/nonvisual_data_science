# Importing and Exploring our Data

Welcome to the fifth and final tutorial of the Nonvisual Data Science workshop series! This will be the second tutorial covering data sonification, or the representation of data as sound. If you missed our last tutorial, which covered the fundamentals of sonification, I highly reccommend that you check that out first. Today we will be working with some real data!

## Importing the Data

I have prepared a csv that compiles data from [the daily temperatures in global cities](https://www.kaggle.com/datasets/subhamjain/temperature-of-all-countries-19952020?resource=download) and [the daily weather in Indian cities](https://www.kaggle.com/datasets/vanvalkenberg/historicalweatherdataforindiancities), both of which are linked here. Some significant modifcations were made to combine the tables and to put them into a format that is convenient for our purposes in this tutorial, although the data itself was not changed. If you are curious about the preprocessing that I performed on these datasets, please do feel free to reach out to me (Sarah Kane at sgk27@cam.ac.uk), and I can send you the Python script that I used.

As always, please begin by opening Anaconda Prompt, and begin IPython by typing "ipython" in all lowercase letters and hitting enter. Our first step will be to import the dataset that I have prepared. Let's start by importing our standby packages: Numpy and Pandas:

~~~python
import numpy
import pandas
~~~

Next we can import the data from the url at which I have it saved using the pandas.read_csv function, just as we have in previous weeks. Please feel free to copy and paste these lines of code, as the URL is rather long! As before, we save the DataFrame returned from read_csv as df.

~~~python
url = 'https://github.com/sgkane/sonification_tutorial_two/blob/main/weather_data.csv?raw=true'
df = pandas.read_csv(url,index_col=0)
~~~

And just like that, we have our data!

## Exploring the Data

I am very strongly of the opinion that data representations--whether visual or audio--are far, far more useful when you actually have some understanding of the data beforehand. As of right now, you have very little idea what is actually in that DataFrame that you just created, beyond perhaps a general sense that it has to do with the weather. Thus, we're going to take some of the steps that Patrick taught us in the introduction to Pandas tutorial to explore our dataset.

First, it would probably be nice to know what columns are in our data:

~~~python
df.columns
~~~

You should get a rather long list of the columns as output:
['year', 'month', 'day', 'new_york_city_temp', 'philadelphia_temp', 'pittsburgh_temp', 'orlando_temp', 'austin_temp', 'seattle_temp', 'delhi_temp', 'delhi_rain_inches', 'delhi_temp_model_one', 'delhi_temp_model_two']

In summary, we have a column each for the day, month, and year of each data measurement. We then have columns for the daily recorded temperature in cities including New York City, Philadelphia, Pittsburgh, Orlando, Austin, Seattle, and Delhi, India. There is a column recording the daily rain in Delhi in inches, and there are two columns containing model predictions for the daily temperature in Delhi. I made those last two columns myself, and we'll talk more about them later.

What is the shape of our data?

~~~python
df.shape
~~~

As an output, you should get (9265, 13), which you might recall means that the data has 9265 rows and 13 columns.

I don't know about you, but the next question I have is what the date range of our dataset is. I'm going to operate on the assumption that our data is in chronological order (which I know it is since I preprocessed it!), so the first row corresponds to the first day of data. We can see what's in the date columns for the first row by running the following line of code (remembering that numbering in Python begins from 0!):

~~~python
df.iloc[0]
~~~

If I read the output for the year, month, and day columns, I can tell that this data begins on January 1, 1995.

We can conveniently check on the last row of the DataFrame by indexing -1 (and indexing -2 would give us the second to last row of the DataFrame, and so on):

~~~python
df.iloc[-1]
~~~

Again reading the first three columns which correspond to year, month, and day, I can tell that this dataset ends on May 13, 2020.

Let's also check on a temperature column. I'm going to look at the tempatures in Philadelphia because I did my undergrad there, so I roughly know what reasonable temperatures should be. First, what is the highest daily temperature recorded in Philadelphia in our dataset?

~~~python
df.philadelphia_temp.max()
~~~

I get an output of 92.9. This is interesting for two reasons: first, even though my DataFrame includes no units, I can now guess that the temperatures are in degrees Fahrenheit because that would be an absurdly hot temperature in Celsius! Second, I am a bit surprised that this is the maximum daily temperature recorded in Philadelphia in our data, as it definitely got hotter than 92.9 degrees in the summer. Perhaps this is an average of the temperature over the entire day, which will naturally be lower than the highest temperature of each day; otherwise, I would worry that there was something wrong with the data! I believe the former scenario is the truth (though admittedly, I will not vouch for the accuracy of any of these measurements!).

Let's similarly look at the minimum temperature:

~~~python
df.philadelphia_temp.min()
~~~

I get 9.4 as an output, which seems roughly reasonable to me.

Finally, for the sake of thoroughness, let's look at the average temperature in the Philadelphia column:

~~~python
df.philadelphia_temp.mean()
~~~

And I get an output of approximately 56 degrees, which roughly makes sense to me from my experience. I encourage you to repeat these steps for each column you are interested in and plan to sonify to get a sense of what the data is doing!
