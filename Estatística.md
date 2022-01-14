Task: Take one measure of the sampling error.

Dataset https://www.kaggle.com/jinxbe/wnba-player-stats-2017/version/1.

```
import pandas as pd
wnba = pd.read_csv('wnba.csv')

# print the first five rows
wnba.head()

# print the last five rows
wnba.tail()

wnba.shape

# maximum number of games played by a player in the 2016-2017 season using the population
parameter = wnba['Games Played'].max()

# randomly sample 30 players from the population
sample = wnba['Games Played'].sample(30, random_state = 1)

# maximum number of games played by a player in the 2016-2017 season using the sample
statistic = sample.max()

sampling_error = parameter - statistic
```
