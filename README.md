# Analyzing-Trending-Tweets-In-Different-Countries

In this project we will analyze the top trending tweets in different countries of the world and will visualize the results.

# Getting the Data

The file `trends_12-12-2018`used for the analysis has been created by using the tweepy. Briefly, I used the twitter trend
api call for collecting top 5 trends for all the available locations ( using the WOEID "WHERE ON EARTH ID") on twitter api.
The complete detail with the code can found on my other repository [here](https://github.com/aameerhamza1801/Analyzing-Top-Trends-on-Twitter-Using-Python).

# Analyzing The Data 

The data initially contains a list of locations (with cities, countries and ids) along with the top 5 trends for each location.

[]!(images/dataframe.jpg)

The country and the trends columns are then separated for further analysis. Since, there could be more than one locations in a
country so the trends of a single country are converted into one list so that we have a country, trends row. For analysis, 
the common trends in a single country are separated and their frequency is recorded. All this process can be seen in this
snippet:

[]!(images/freq_data.jpg)

where 

    **all_trends** is the top five trends list of all locations in a country and
    **freq_dict** is the `{trends:frequency}` data for unique trends in the all_trends column
    
For visualizing purpose, the trends with a frequency of less than 10 are removed from the `freq_dict` column and the countries 
where there is no trend frequency greater than 10 are removed. Obviously this would not create uniform result as some countries
have more locations than others but the twitter divides the locations according to the usage of the twitter so the countries
left out have lower twitter usage than the countries included for analysis.

Finally the frequencies, trends and countries are converted into lists and then plotted in the form of a bar char as below: 

[]!(images/top_country_trends.jpg)

As can be seen in the chart, United states has the top frequency as twitter usage is the most in US (hence more locations). Also 
we can see in most locations in US the top trend is `#RockHall2019` on 12 dec,2018. We can also see the most frequent trends in
other countries as well e.g. India has a trend **INDvsNED** which shows the hocky men's worldcup match. So we can see different 
events in different parts of the world.
The twitter trend api also provides the **trend Volume** attribute but it does not gives satisfatory results as most of the
locations have null value for volume (twitter needs to improve this) therefore I have not used the volume for analysis.

# What could be done in future

In the future, I plan to analyse the trends that are common in different countries. This will tell us about the similarities
in different countries. e.g. if the hashtag `#TaylorSwiftSong` is trending in three countries then this shows that 
those countries could have a similar music taste.
So analyzing the similar topics in different countries would be cool.
