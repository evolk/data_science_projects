# Fitbit data analysis readme

I wanted to analyse my fitbit data for a couple of years now, I was especially curious to see if my activity levels impact my resting heart beat rate (as is claimed, e.g, here: https://www.polar.com/blog/resting-heart-rate/). I've had a Fitbit with HR function since it came out, although I wasn't always wearing it (and I wan't always doing sports!). So, I was ready to see next to know effects, my primary goal was to have fun with time series analysis.
The analysis aims to investigate the following alternative hypothesis: the more active I am, the lower my resting heart rate should become. I also look at the following complications in the analysis:
How quickly does the effect of higher activity take place?

Is there monthly seasonality to my resting heart rate, due to hormonal fluctuations, as is indicated here and in other studies: https://www.nature.com/articles/s41598-017-01433-9
I took several months of my resting heart rate, steps and activity-related data because during that time I had a relatively stable, though rather unplasand lifestype. During the week I was commuting from Oxford to London, during the weekend recoving from the work week. Monday-Friday I walked a total of 2 hours or more (home to train station A, train station B to work, and back) so I had a decent step count.
Extracting data from Fitbit at this level of detail and scope is not trivial. There used to be nice R packages for that but at the time of writing (Easter breka 2018) they don't work anymore I used Fitbit developer API to do that, to do that there is a detailed tutorial here: https://annofoneblog.wordpress.com/2017/10/19/your-heart-your-calories-your-sleep-your-data-how-to-extract-your-fitbit-data-and-make-graphs-using-r/
This notebook goes through the following stages:

1. Import and format the data

2. Explore and plot the raw data

3. Investigae wholes and anomalies

4. Investigate seasonality and trends

5. Investigate correlations

6. Performs multivariate analysis

As I only extracted 9 months worth of data, with one point per day per variable, there is no way I would have enough for a proper LSTM analysis, perhaps in a few years :) In any case, there is no shame in doing solid statistics in cases where fancy neural nets are like using a bazooka to shoot a sparrow.
Another thing to keep in mind is the accuracy of the sensors - Fitbit is not a medical grade device, so I cannot be sure the resting heart rate is 100% accurate. Even the step count can be questioned - if you take a ride in a car on a bumpy road, be sure it will add a few hundred steps to you count. Same happens if you knit or crochet.
I did my best to add comments the cells to explain what is going on.

Useful (and used) Resources:

1. https://machinelearningmastery.com/multivariate-time-series-forecasting-lstms-keras/

2. http://barnesanalytics.com/analyzing-multivariate-time-series-using-arimax-in-python-with-statsmodels

3. https://github.com/nlittlepoole/thermometr

4. https://blog.statsbot.co/time-series-anomaly-detection-algorithms-1cef5519aef2
