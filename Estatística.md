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

### Atividade 4

**Task:** Perform stratified sampling on the data set 100 times, and sample strata proportionally.

```
stratum_1 = wnba[wnba['Games Played'] <= 12]
stratum_2 = wnba[(wnba['Games Played'] > 12) & (wnba['Games Played'] <= 22)]
stratum_3 = wnba[wnba['Games Played'] > 22]

sample = []
mean_points = []
population_mean = wnba['PTS'].mean()

# Sample each stratum proportionally
for i in range(100):
    sample_1 = stratum_1.sample(1, random_state = i)
    sample_2 = stratum_2.sample(2, random_state = i)
    sample_3 = stratum_3.sample(7, random_state = i)
    
    sample = pd.concat([sample_1, sample_2, sample_3])
    
    mean_points.append(sample['PTS'].mean())

plt.scatter(x=range(1,101), y=mean_points)
plt.axhline(y=population_mean)   
```

Notou-se que o resultado não foi muito melhor que o anterior, mesmo amostrando por stratum. Isso se deve ao fato do parâmetro Games Played não ter sido a melhor opção, pois um jogador poderia entrar para jogar por 5 minutos enquanto outro poderia jogar por 40 minutos e os dois teriam participado de um jogo. Assim, escolher o parâmetro minutos de jogo pode ser mais correto que quantidade de jogos.

Dicas para amostragem:
- Diminuir a variedade em cada 'stratum'.
"For instance, avoid having in the same stratum a player that has scored 10 points and a player that has scored 500. If the variability is high, it might be a sign that you either need more granular stratification (you need more strata), or you need to change the criterion of stratification (an example of criterion is minutes played)."
- Maximizar a variedade entre 'stratum's diferentes.
"Good strata are different from one another. If you have strata that are similar to one another with respect to what you want to measure, you might need a more granular stratification, or you might need to change the stratification criterion. On the previous screen, stratifying the data by games played resulted in strata that were similar to each other regarding the distribution of the total points. We managed to increase the variability between strata by changing the criterion of stratification to minutes played."
- O critério de estratificação deve estar fortemente relacionado à propriedade que você está querendo medir
"For instance, the column describing minutes played (the criterion) should be correlate strongly with the number of total points (property we want to measure)."

## Cluster sampling
Ocorre quando uma população é dividida em grupos menores, que podem ser chamados de clusters.

### Atividade Cluster Sampling

**Task:** Let's simulate a cluster sampling on our data set.

```
all_data = wnba
sample = pd.DataFrame()

# Seleciona 4 cluster randômicos
selected_clusters = pd.Series(wnba['Team'].unique()).sample(4, random_state = 0)

# Pega todos os dados de cada cluster selecionado
for cluster in selected_clusters:
    data = wnba[wnba['Team'] == cluster]
    sample = sample.append(data)

sampling_error_height = all_data['Height'].mean() - sample['Height'].mean()

sampling_error_age = all_data['Age'].mean() - sample['Age'].mean()

sampling_error_BMI = all_data['BMI'].mean() - sample['BMI'].mean()

sampling_error_points = all_data['PTS'].mean() - sample['PTS'].mean()
```

- "Descriptive statistics": Descrição da amostra ou população (proporções, métricas, propriedades).
- "Inferential statistics": Quando utilizamos uma amostra para inferir conclusões a respeito de uma população.

