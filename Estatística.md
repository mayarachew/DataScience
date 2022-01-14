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

Ao coletar uma amostra randômica simples, conforme aumentamos o tamanho da amostra percebemos que os valores da amostra variam menos em relação à média da população. Também devemos tomar o cuidado de coletar a maior amostra possível para diminuir as chances de pegarmos amostras não representativas.

### Atividade 3

**Task:** Perform stratified sampling: stratify the dataset by player position, and then do simple random sampling on every stratum. At the end, use the sample to determine which position scores the highest number of points per game.

```
print(wnba['Pos'].unique())

wnba['Points per game'] = wnba['PTS'] / wnba['Games Played']

F = wnba[wnba.Pos == 'F']
G = wnba[wnba.Pos == 'G']
C = wnba[wnba.Pos == 'C']
GF = wnba[wnba.Pos == 'G/F']
FC = wnba[wnba.Pos == 'F/C']

points_per_position = {}

for stratum, position in [(G, 'G'), (F, 'F'), (C, 'C'), (GF, 'G/F'), (FC, 'F/C')]:
    sample = stratum['Points per game'].sample(10, random_state=0)
    points_per_position[position]=sample.mean()
    
position_most_points = max(points_per_position, key=points_per_position.get)
    
```
