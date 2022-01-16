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

"Variables that describe qualities are called qualitative variables or categorical variables. Generally, qualitative variables describe what or how something is. Quantitative variables describe a quantity using real numbers, but there are also cases when words are used instead."


# Variables in Statistics

### Atividade

Variáveis ordinais podem ser tanto números quanto palavras.

Quantitative variables can be measured on ordinal, interval, or ratio scales.

Neste dataset, temos variáveis medidas em escala de intervalo e de razão:
- Intervalo: ['Birthdate', 'Weight_deviation']
- Razão: ['Height', 'Weight', 'BMI', 'Age', 'Experience', 'Games Played', 'MIN', 'FGM', 'FGA', 'FG%', '15:00','3PA', '3P%', 'FTM', 'FTA', 'FT%', 'OREB', 'DREB', 'REB', 'AST', 'STL', 'BLK', 'TO', 'PTS', 'DD2', 'TD3']

#### Tipos de variáveis:

- **Discretas:** quando não existem valores possíveis intermediários entre dois valores adjacentes. Exemplo: quantidade de pessoas em uma sala.

Neste dataset, temos as seguintes variáveis discretas: Games Played, FGM, FGA, 3PA, FTM, FTA, OREB,...

- **Contínuas:** quando existe uma infinidade de valores possíveis intermediários entre dois valores adjacentes. Exemplo: altura de uma pessoa.
     
Neste dataset, temos as seguintes variáveis discretas: Height, Weight, Age, FT%, Weight_deviation,...

## Distribuições de frequência

**Series.value_counts()** mostra uma tabela de distribuição dos valores.

**Series.sort_index()** pode ser utilizado para ordenar uma tabela de acordo com o índice dela.

Para criar uma nova coluna baseada em colunas já existentes, pode ser feito o seguinte:

```
def make_pts_ordinal(row):
    if row['PTS'] <= 20:
        return 'poucos pontos'
    else:
        return 'muitos pontos'
    
wnba['PTS_ordinal'] = wnba.apply(make_pts_ordinal, axis = 1)
```

**.iloc[]** pode ser utilizado para reordenar as linhas da tabela gerada pelo .value_counts(). Cada número equivale a uma linha, ou seja, a primeira equivale a 0. 

```
pts_ordinal_desc = wnba['PTS_ordinal_scale'].value_counts().iloc[[4, 3, 0, 2, 1, 5]]
```

Para descobrir a porcentagem de cada valor em relação ao todo, podemos aplicar o Series.value_counts(normalize = True) * 100.

**Frequência absoluta:** quantidade total de vezes que obtivemos um valor como resposta.
**Frequência relativa:** a relação da frequência absoluta com o valor total de respostas.

### Atividade

**Task:** Descobrir qual a porcentagem de jogadores que possuem 24 anos.

```
percentage_24 = wnba['Age'].value_counts(normalize = True)[24] * 100
```

**Task:** Descobrir qual a porcentagem de jogadores que possuem 24 anos ou mais.

```
percentage_over_24 = wnba['Age'].value_counts(normalize = True).sort_index().loc[24:].sum()* 100
```

**Percentile:** Se o valor x for o vigésimo percentil, significa que 20% de todos os valores da distribuição são iguais ou menores que x.

**Task:** Descobrir qual a porcentagem de jogadores que possuem 24 anos ou menos.

```
percentage_over_24 = wnba['Age'].value_counts(normalize = True).sort_index().loc[:24].sum()* 100
```
ou
```
from scipy.stats import percentileofscore

# kind = 'weak': indica que queremos os valores iguais ou menores.
percentage_over_24 = percentileofscore(a = wnba['Age'], score = 24, kind = 'weak')
```

**Task:** Descobrir qual a porcentagem de jogadores que possuem mais que 24 anos.

```
from scipy.stats import percentileofscore

percentage_over_24 = (100 - percentileofscore(a = wnba['Age'], score = 24, kind = 'weak'))
```

Podemos descobrir informações (contagem, média, std, valor mínimo, 25%, 50%, 75%, valor máximo, nome da variaável, tipo da variável) de uma coluna do nosso dataset pelo comando "Series.describe()":

```
wnba['Age'].describe()
```

O primeiro quartil é chamado de 25% (lower quartil), o segundo de 50% (middle quartil) e o terceiro de 75% (upper quartil).

**Task:** Obter o "lower quartil" e o "10th percentil".

```
age_lower_quartile = wnba['Age'].describe()['25%']

age_10th_percentile = wnba['Age'].describe([.10])['10%']
```

Em casos de alta granularidade nos dados da tabela, pode ser interessante agrupar os valores por meio do parâmetro "bins" do "Series.value_counts()".

**Task:** Gerar uma distribuição de frequência agrupada para a variável "PTS" do dataset com: 10 intervalos, respectivas porcentagens e em ordem decrescente.

```
grouped_freq_table = wnba['PTS'].value_counts(normalize = True, bins = 10).sort_index(ascending=False) * 100
```

Dessa forma, não temos controle sob os intervalos definidos. Caso seja do nosso interesse definí-los manualmente, podemos por meio da função "pd.interval_range()".

**Task:** Gerar uma distribuição de frequência agrupada para a variável "PTS" do dataset com: frequência de 60, começando no 0, finalizando no 600.

```
intervals = pd.interval_range(start = 0, end = 600, freq = 60)

gr_freq_table_10 = wnba["PTS"].value_counts(bins = intervals).sort_index()
```

# Bar plots

## Gráfico de barras
Podem ser utilizadas variáveis nominais e ordinais.

### Vertical
```
wnba['Age'].value_counts().plot.bar()
```

### Horizontal
```
# grafico de barras horizontal
wnba['Age'].value_counts().plot.barh()
```

Parâmetro "rot" para rotacionar as labels em 45 graus:
```
wnba['Age'].value_counts().plot.bar(rot=45)
```

Parâmetro "title" para adicionar título ao gráfico:
```
wnba['Age'].value_counts().plot.bar(title='Idade dos jogadores de WNBA')
```

## Gráfico de pizza
Podem ser utilizadas variáveis nominais e ordinais. PS: melhor evitar, pois é difícil para o ser humano identificar proporções maiores ou menores por meio de ângulos.
```
# autopct = '%.2f%%': mostra porcentagens
import matplotlib.pyplot as plt
wnba['Exp_ordinal'].value_counts().plot.pie(figsize = (6,6), autopct = '%.2f%%', title="Percentage of players in WNBA by level of experience")
plt.ylabel('')
```

## Histograma
Histograma é um gráfico de barras que representa a distribuição de frequências de uma variável. Podem ser utilizadas variáveis de intervalo e de razão. Ele complementa a interpretação da função "db.describe()".
```
from numpy import arange

# grid = True: adiciona linhas verticais/horizontais no gráfico
# xticks = arange(2,585,58.2): define os valores do mínimos e máximos de x
wnba['Games Played'].plot.hist(grid = True, xticks = arange(2,585,58.2), rot = 30)

print(wnba['Games Played'].describe())
```

```
import matplotlib.pyplot as plt

# bins = 8: número de barras
wnba['Games Played'].plot.hist(range = (1,32), bins = 8, title="The distribution of players by games played")

plt.xlabel('Games played')
```

**Fato curioso:** em histogramas, as barras são juntas umas às outras, sem intervalo entre elas, devido ao fato de que sabemos que não existem valores intermediários entre as barras. Em gráficos de barras existem intervalos porque nós não sabemos como as variáveis ordinais foram definidas, logo, não temos certeza de que os valores são adjacentes.

### Formatos

Distribuições assimétricas ou "Skewed distributions é uma medida de falta de simetria na distribuição de frequência. 

- **"Left skewed" ou "negatively skewed":** quando a calda do gráfico aponta para a esquerda.
- **"Right skewed" ou "positively skewed":** quando a calda do gráfico aponta para a direita. 

PS: a calda do gráfico é a parte onde tem as menores barras e elas se encontram decrescendo de tamanho.

```
# right skewed
wnba['AST'].plot.hist()

# left skewed
wnba['FT%'].plot.hist()
```
- **"Normal distribution":** quando a distribuição é simétrica e se parece com uma gaussiana.

```
# normal distribution
wnba['Weight'].plot.hist()
```

- **"Uniform distribution":** quando a distribuição é simétrica e os valores são distribuidos uniformemente, gerando barras da mesma altura.

# Comparação entre distribuições de frequência

**Task:** Estamos interessados em analisar como posição do jogador varia de acordo como nível de experiência dele.

Opção 1: podemos analisar os valores puros em forma de tabela.
```
rookies = wnba[wnba['Exp_ordinal'] == 'Rookie']
little_xp = wnba[wnba['Exp_ordinal'] == 'Little experience']
experienced = wnba[wnba['Exp_ordinal'] == 'Experienced']
very_xp = wnba[wnba['Exp_ordinal'] == 'Very experienced']
veterans =  wnba[wnba['Exp_ordinal'] == 'Veteran']

rookie_distro = rookies['Pos'].value_counts()
little_xp_distro = little_xp['Pos'].value_counts()
experienced_distro = experienced['Pos'].value_counts()
very_xp_distro = very_xp['Pos'].value_counts()
veteran_distro = veterans['Pos'].value_counts()

print(rookie_distro, little_xp_distro, experienced_distro, very_xp_distro, veteran_distro)
```

Opção 2: podemos analisar os valores por meio de um gráfico chamado "grouped bar plot".
```
import seaborn as sns

# hue = 'Pos': indica a variavel a ser comparada (subdivisão no eixo x)
sns.countplot(x = 'Exp_ordinal', hue = 'Pos', data = wnba, order = ['Rookie', 'Little experience', 'Experienced', 'Very experienced', 'Veteran'], hue_order = ['C', 'F', 'F/C', 'G', 'G/F'])
```

**Task:** Vamos supor que temos a seguinte hipótese a ser verificada no dataset: quanto mais velhos os jogadores, a média de tempo de jogo diminui. Nessa task vamos considerar que a idade que divide um jogador novo de um velho é 27 anos.

```
import seaborn as sns

wnba['age_mean_relative'] = wnba['Age'].apply(lambda x: 'old' if x >= 27 else 'young')

wnba['min_mean_relative'] = wnba['MIN'].apply(lambda x: 'average or above' if x >= 497 else 'below average')

sns.countplot(x = 'age_mean_relative', hue = 'min_mean_relative', data = wnba)
```
 Com base nesse resultado, vemos que os jogadores mais velhos possuem mais tempo de jogo. Logo, rejeitamos a nossa hipótese inicial.
 
Para melhorar a nossa análise, podemos criar um histograma sobreposto com a quantidade de tempo de jogo de acordo com a idade do jogador e marcar com uma linha o tempo médio de jogo.
```
import matplotlib.pyplot as plt

wnba[wnba.Age >= 27]['MIN'].plot.hist(histtype = 'step', label = 'Old', legend = True)
wnba[wnba.Age < 27]['MIN'].plot.hist(histtype = 'step', label = 'Young', legend = True)

plt.axvline(497, label = 'Average')
plt.legend()
plt.show()
```

## Gráficos de densidade de kernel ou "kernel density estimate plots"
Podem ser utilizadas variáveis de intervalo e de razão.

Esse último gráfico ficou um tanto lotado de informações, então ainda podemos melhorar mais! Para isso, podemos utilizar gráficos de densidade de kernel.
```
import matplotlib.pyplot as plt

wnba[wnba.Age >= 27]['MIN'].plot.kde(label = 'Old', legend = True)
wnba[wnba.Age < 27]['MIN'].plot.kde(label = 'Young', legend = True)

plt.axvline(497, label = 'Average')
plt.legend()
plt.show()
```

## "Strip plot"
Podem ser utilizadas variáveis de intervalo e de razão.

**Task:** verificar a relação entre o peso dos jogadores e a posição deles no jogo.
```
import matplotlib.pyplot as plt
import seaborn as sns

sns.stripplot(x = 'Pos', y = 'Weight', data = wnba, jitter = True)

plt.show()
```
Podemos notar que os jogadores da posição "G" são os mais leves e os da posição "C" são os mais pesados.

## Diagrama de caixa ou "Box plot"
Podem ser utilizadas variáveis de intervalo e de razão.

Além do gráfico de pontos mostrado acima, também podemos utilizar o diagrama de caixa:
```
import matplotlib.pyplot as plt
import seaborn as sns

sns.boxplot(x = 'Pos', y = 'Weight', data = wnba)

plt.show()
```

## Outlier
Um valor pode ser considerado um outlier se for maior que o "upper quartile" em 1.5 vezes o intervalo interquartil ("interquartile range") e for menor que o "lower_quartile" em 1.5 vezes o intervalo interquartil.

```
import matplotlib.pyplot as plt
import seaborn as sns

# obter os valores dos quartiles
upper_quartile = wnba['Games Played'].describe()['75%']
lower_quartile = wnba['Games Played'].describe()['25%']

# definir o intervalo interquartil
iqr = upper_quartile - lower_quartile

# multiplicar o intervalo por 1.5 e definir os limites superior e inferior
upper_bound = upper_quartile + (iqr * 1.5)
lower_bound = lower_quartile - (iqr * 1.5)

# verificar quantos valores não estão dentro dos limites definidos (outliers)
outliers_high = sum(wnba['Games Played'] > upper_bound)
outliers_low = sum(wnba['Games Played'] < lower_bound)

# plotar o gráfico
sns.boxplot(wnba['Games Played'])
plt.show()
```
