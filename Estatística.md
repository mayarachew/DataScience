Explore the dataset https://www.kaggle.com/jinxbe/wnba-player-stats-2017/version/1.

Print the first five rows using DataFrame.head() and the last five rows with DataFrame.tail().
Find the number of rows and columns using DataFrame.shape.
Learn about each column from the documentation. You can also find useful documentation in this glossary and on WNBA's official page.
Take one measure of the sampling error.

Use the Games Played column to find the maximum number of games played by a player in the 2016-2017 season. The dataset contains all the players who played at least one game, so it's a population relative to our question. Find this parameter, and assign the result to a variable named parameter.
Using the DataFrame.sample() method, randomly sample 30 players from the population, and assign the result to a variable named sample.
When calling Series.sample(), use the argument random_state = 1. This makes your results reproducible, and it helps us with the answer-checking (we'll discuss this on the next screen).
Find the maximum number of games using the sample, and assign the result to a variable named statistic.
Measure the sampling error, and assign the result to a variable named sampling_error.

```
import pandas as pd
wnba = pd.read_csv('wnba.csv')

wnba.head()

wnba.tail()

wnba.shape

parameter = wnba['Games Played'].max()

sample = wnba['Games Played'].sample(30, random_state = 1)

statistic = sample.max()

sampling_error = parameter - statistic
```
