# Checking Models of Our Data with Sonification

One really frequent thing you'll see people do with data is to model it. What I mean by this is that they will try to find some mathematical equation that more or less follows the same pattern as the data. The correlations that Patrick showed you how to find in the Nonvisual Data Representation tutorial could be considered a part of linear modeling, or finding a linear equation that follows the trend in the data. We won't dig too deeply into that here; we are just interested in using sonifications to judge whetehr a model is roughly a good fit to the data or not.

You might recall that there are two columns in our DataFrame called "delhi_temp_model_one" and "delhi_temp_model_two." When I made this csv file for us to use, I made two different models for the data, and these columns contain the predictions of each of those models at each of the timesteps in our data. I will tell you three things about these models: first, one of them is a rather good fit to the data, and the other is deliberately bad. Our goal here is two distinguish between the two with the sonification. Second, both models use a sine equation, which you might recall from last week means that they both follow a wave pattern. I chose to use a sine function for the model because the data itself is like a wave, with the temperatures increasing and decreasing regularly with time as the seasons pass. Finally, for those of you who are statistics savvy, I will tell you that neither of these curves is actually a best-fit model to the data; I made the "good" model by manipulating the sine function to match how I know the data is behaving, and then the "bad" sine model has just some more or less random coefficients. If you're not interested in math and statistics, feel free to ignore that last bit, but I just wanted to include it for completeness.

Again, if you are interested in how I made the csv, including the models, please do feel free to reach out to me and I can send you the Python script that I used.

Now, there are some rigorous mathematical ways to test whether one model is a better fit to the data than another, and frankly, I reccommend looking into those if you are interested in doing serious modeling. However, in practice, many people using visualizations will simply evaluate models by visualizing the model and the real data together and seeing if they look similar. We will do something similar here by sonifying both the data from the Delhi daily temperatures and the two models' predictions of Delhi's daily temperatures to decide which representation sounds more similar to the true data.

## Sonifying our Models

To begin with, let's listen to the sonification of the Delhi daily temperature data once more just so the reference for comparison is fresh in our minds. Fortunately, we've already made this sonification, so we just need to play it:

~~~python
soni_delhi.play()
~~~

We can then sonify and play the predictions from Models One and Two using the steps with which we are very familiar by now. Recall that we have set the zero point of our Delhi sonification, or the value that is mapped to a pitch of 440 Hertz, to 60 for comparison with the Philadelphia sonification. We'll set the zero point of both of our model sonifications to 60 as well, for consistency.

Let's sonify the first model:

~~~python
soni_model1 = SoniSeries(tbl, time_col='timestep', val_col='delhi_temp_model_one')
soni_model1.pitch_mapper.pitch_map_args["zero_point"] = 60
soni_model1.sonify()
soni_model1.play()
~~~

And we can sonify the second model with the exact same steps: 

~~~python
soni_model2 = SoniSeries(tbl, time_col='timestep', val_col='delhi_temp_model_two')
soni_model2.pitch_mapper.pitch_map_args["zero_point"] = 60
soni_model2.sonify()
soni_model2.play()
~~~

Which model sonification sounds more similar to the original Delhi temeprature data, and thus which model do you think is a better fit for the data?

The answer is below this line:

Model One is meant to be a better fit to the data--and in fact, it is meant to be a much better fit to the data than Model two!
