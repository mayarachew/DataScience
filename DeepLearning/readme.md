### Deep Learning

#### O que é?

"Deep Learning" ou Aprendizado Profundo é um modelo baseado em aprendizado não supervisionado e aprendizado de recursos hierárquicos. O "deep" de seu nome pode ser traduzido para profundo, que faz uma referência às camadas de uma rede neural (LINK).

#### Machine Learning x Deep Learning

Machine Learning:

- Não é necessário investir em um computador potente para rodar algoritmos de Machine Learning.
- Não são necessários tantos dados para obter o melhor desempenho do modelo (essa perfomance pode não aumentar com a inserção de mais dados).
- Dependem de seleção e pré-processamento manual de dados.
- Mais simples de ser explicado.

Deep Learning:

- É necessário um computador mais potente para executar operações de matrizes em grandes conjuntos de dados (operações de álgebra linear). Pode ser necessário uma GPU para melhorar a rapidez do modelo em comparação com CPUs.
- Quanto mais dados, melhor os resultados do modelo. Costuma ser mais escalável que o Machine Learning.
- Extração automática de dados,ou seja, geralmente o pré-processamento não é necessário pois está inserido nos modelos ("E2E Learning").
- Mais complexo de ser explicado.

#### Modelos de redes neurais

- Multilayer Perceptron (LINK)
- Autoencoder (LINK)

#### 5 tipos de algoritmos de redes neurais

- Error-correction learning: pode ser utilizado para classificação.
- Memory-based learning: possui como base a memória; para tarefas de classificação, se um dado a ser classificado ainda não foi analisado anteriormente, o processo consiste em analizar os dados de treinamento que pertencem à vizinhança local do dado. Para isso, é necessário ter um critério para definir a vizinhança local do vetor de teste e uma regra de aprendizado para ser aplicada aos dados de treinamento pertencentes a essa vizinhança.
- Hebbian learning: é uma das mais conhecidas, ela é dependente do tempo e do local em que a sinapse ocorre, além de ser interativa e correlacional. Nesse algoritmo vários neurônios são ativados simultaneamente.
- Competitive learning: a saída de neurônios de uma rede neural com esse algoritmo é resultado de uma competição entre eles. Apenas um neurônio pode ser ativado por vez.
- Boltzmann learning: um algoritmo de aprendizado estocástico*, baseado na estatística.

\* Estocástico ("stochastic"): conceito utilizado na estatística para definir eventos aleatórios.
