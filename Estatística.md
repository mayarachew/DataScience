**Dataset:** https://www.kaggle.com/jinxbe/wnba-player-stats-2017/version/1.

### Atividade sampling_error

**Task:** Take one measure of the sampling error.

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
# random_state = 1: para obter sempre a mesma amostra ao rodar este comando
sample = wnba['Games Played'].sample(30, random_state = 1)

# maximum number of games played by a player in the 2016-2017 season using the sample
statistic = sample.max()

sampling_error = parameter - statistic
```

Quanto mais mais representativa uma amostra é, menor o erro de amostra.

- Simple Random Sampling (SRS): Series.sample()

### Atividade comparação entre estatística e parâmetro

**Task:** visualize the discrepancy between a parameter and its corresponding statistics in the case of simple random sampling.

```
import pandas as pd
import matplotlib.pyplot as plt

wnba = pd.read_csv('wnba.csv')
population_mean = wnba['PTS'].mean()
mean_list = []

for idx in range(100):
    sample = wnba['PTS'].sample(10, random_state = idx)
    PTS_mean = sample.mean()
    mean_list.append(PTS_mean)
        
plt.scatter(x=range(1,101), y=mean_list)
plt.axhline(y=population_mean)
```
