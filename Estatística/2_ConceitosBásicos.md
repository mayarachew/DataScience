# Conceitos Básicos

## População x Amostra

- **População**: todo o conjunto existente.

- **Amostra**: subconjunto de uma população.

## Dados quantitativos x Dados qualitativos

- **Dados quantitativos**: representam valores ou medidas numéricas.

- **Dados qualitativos**: podem ser definidos por categorias não numéricas.

## Dados discretos x Dados contínuos

- **Dados discretos**: dados pertencentes a um conjunto finito de valores possíveis, ou seja, é contável.
  Ex: número de maçãs em uma árvore. Podem existir 1, 2, 3, {...}, n maçãs em uma árvore, mas não podem existir 2,5 maçãs.

- **Dados contínuos**: dados pertencentes a um conjunto infinito de valores possíveis, ou seja, o dado pertence a um valor dentro de um intervalo.
  Ex: ao extrair sucos de maçã, podemos colocar em garrafas. Podem existir {...}, 1, {...}, 2, {...}, 2,5, {...}, 3, {...} garrafas de suco de maçã.

## Tradeoff: Viés x Variância

Em Aprendizado de Máquina ("Machine Learning"), utilizamos o viés e a variância para calcular o erro geral das previsões.

- **Viés ("Bias")**: a diferença média entre o rótulo ("label") definido pelo modelo e o rótulo real.

- **Variância ("Variance")**: É o quanto a quantidade de acertos do modelo varia de acordo com diferentes predições, com diferentes valores de teste.

Idealmente, o melhor seria obter baixo viés e baixa variância. Na prática, ao tentarmos abaixar o viés, a variância irá aumentar e vice-versa. Com o objetivo de diminuir o erro geral da previsão, deve haver um equilíbrio entre os valores de viés e variância.

## Correlação

A correlação mede as relações entre duas variáveis.

### Valores de coeficiente de correlação:

- **+1**: significa que existe uma correlação positiva entre as variáveis, ou seja, quando uma variável aumenta, a outra também aumenta.
- **0**: significa que não existe correlação.
- **-1**: significa que existe uma correlação negativa entre as variáveis, ou seja, quando uma variável diminui, a outra também diminui.

### Correlação x Causalidade

Correlação não implica causalidade, então duas variáveis podem ter correlação e o valor de uma não causar o valor da outra, vice-versa.

## Referências:

- https://www.cienciaedados.com/8-conceitos-estatisticos-fundamentais-para-data-science/#:~:text=Estat%C3%ADstica%20%C3%A9%20%E2%80%9Cum%20ramo%20da,principais%20habilidades%20em%20Data%20Science.
- https://medium.com/data-hackers/o-que-é-bias-variance-tradeoff-a5bc19866e4b
