# Feedforward Neural Network

## O que é?

Também pode ser chamada de "Artificial Neural Network" ou "Multilayer Perceptron", este nome foi dado por conta de ser uma rede com mais de uma camada "Perceptron". Ela é um tipo de rede neural com camadas de neurônios encadeadas umas com as outras, ou seja, a saída de uma camada é a entrada de outra por meio de uma função de ativação\*. Existem uma ou mais camadas de neurônios escondidas ("hidden layers").

\* Para conectar as camadas e fazer transformações nos dados, são utilizadas funções de ativação não lineares. Geralmente são não lineares, pois são utilizadas para resolver problemas complexos.

## Estrutura

- Camada de entrada ("input layer"): não contém neurônios, apenas o vetor de entrada.

- Camadas intermediárias/escondidas ("hidden layers"): contém neurônios referentes às retas/planos/hyperplanos utilizados no espaço bidimensional para separar os dados.

- Camada de saída ("output layer"): contém neurônios referentes às saídas possíveis, aos rótulos ("labels").

### Valores da camada de saída

- Se os valores de probabilidade de ser determinado rótulo forem baixas, pode-se chegar à conclusão de que não foi possível realizar a predição ou escolher o rótulo da maior probabilidade.
- Os valores de probabilidade da camada de saída somados podem dar um valor > 1.

**Observações**

- No caso de ter uma camada escondida, a rede neural aproxima matematicamente uma função contínua.
- No caso de ter uma ou mais camadas escondidas, a rede neural aproxima matematicamente qualquer tipo de função. A qualidade da aproximação depende da complexidade da rede neural, incluindo outros parâmetros além da quantidade de camadas intermediárias.
- Cada "Feedforward Neural Network" possui pelo menos uma camada intermediária.
- Arquitetura mais comum: totalmente conectada ("fully connected").
- No caso de existirem 3 camadas, a primeira é responsável por criar um hyper-plano no espaço de entrada, a segunda camada por criar regiões convexas e a terceira por criar combinações de figuras convexas.

<!-- ## Regras de treinamento -->

## Funções de erro/perda

A função de erro/perda ("Error/Loss function") calcula o erro da predição, mostrando o quão próximo do ideal a rede neural está. Geralmente são utilizadas funções não lineares, porque a derivada de funções lineares é constante, o que é ruim para o treinamento. Essas funções de erro/perda são utilizadas para encontrar o mínimo global.

**Como saber se encontramos um mínimo global e não apenas um mínimo local da função de erro/perda?** Não há garantias!

### Tipos de funções de erro/perda

#### Função de custo quadrático

A Função de custo quadrático ou ("Quadratic Cost Function") costuma ser a mais comum.

#### Função de entropia cruzada

A Função de entropia cruzada ou ("Cross Entropy Error") é mais complexa que a função de custo quadrático.

## Formas de ajuste de pesos

Serão citadas abaixo técnicas para ajustar os pesos das camadas intermediárias de forma que minimize o erro final.

### Gradiente descendente

Em um gráfico gerado pela função de erro escolhida por parâmetros livres, o gradiente descendente é representado por vetores que indicam o mínimo global do gráfico, que minimiza o valor do erro.

### Algoritmo de Backpropagation

Este algoritmo estima o efeito dos erros das camadas intermediárias no erro da camada de saída, utilizando a função de erro escolhida.

- Utiliza a regra Delta generalizada.
- Requer funções de ativação contínuas e diferenciáveis, para evitar situações com derivada indefinida.
- A derivada parcial é utilizada para medir a contribuição de cada peso para o erro final. Caso a derivada seja positiva, significa que existe um aumento do erro. Caso a derivada seja negativa, signitica que existe uma diminuição do erro.

## Funções de ativação

Na camada de saída, as funções de ativação podem ser:

- Para tarefas de classificação, Sigmoid ou de Tangente Hiperbólica.
- Para tarefas de regressão, Linear.

<!-- ## Normalização

## Otimizadores -->

## Referências

- https://www.deeplearningbook.com.br/a-arquitetura-das-redes-neurais/
