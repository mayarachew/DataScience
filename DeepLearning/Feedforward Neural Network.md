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

## Tipos de feedforward neural networks

### Convolutional Neural Network (CNN)
Redes neurais convolucionais incluem camadas convolucionais e de "pooling" para compartilhar informações locais e uma camada "fully connected" para tarefas de classificação. Geralmente, a função de ativação Softmax é utilizada nessa última camada. 

- **Convolução** consiste em aplicar um filtro em uma imagem e obter o resultado, uma matriz convolucionada.
- **"Pooling"** consiste em reduzir a dimensionalidade da imagem por meio de convolução. "Max pooling" utiliza o maior valor para representar determinada área nessa redução de dimensionalidade, enquanto o "average pooling" utiliza o valor médio da área. Esse processo é feito repetitidamente, com diferentes áreas da matriz presente na camada para obter uma matriz menor.

Sua aplicação é muito utilizada em processamento de imagens/visão computacional, por dois princípios:

- **Local receptive field**: neurônios analisando parte das imagens ("local image") ao invés de analisar a imagem inteira ("global image"). As camadas de convolução permitem a detecção de objetos sem *decorar* o local que eles devem aparecer, como é comum acontecer em redes neurais.
- **Parameter sharing**: um ou mais filtros/kernels com pesos podem ser utilizados para escanear as imagens. Nesse caso, cada filtro escaneia uma imagem inteira, com parâmetros fixos.

Processo completo de aplicação de CNN em uma imagem:
1) Leitura da imagem
2) Vetorização da imagem ou aplicação de uma camada de convolução e pooling
3) Aplicação de uma rede neural total mente conectada "fully connected" para classificação

## Funções de erro/perda

A função de erro/perda ("Error/Loss function") calcula o erro da predição, mostrando o quão próximo do ideal a rede neural está. Geralmente são utilizadas funções não lineares, porque a derivada de funções lineares é constante, o que é ruim para o treinamento. Essas funções de erro/perda são utilizadas para encontrar o mínimo global.

**Como saber se encontramos um mínimo global e não apenas um mínimo local da função de erro/perda?** Não há garantias!

### Tipos de funções de erro/perda

#### Função de custo quadrático

A Função de custo quadrático ou ("Quadratic Cost Function") costuma ser a mais comum.

#### Função de entropia cruzada

A Função de entropia cruzada ou ("Cross Entropy Error") é mais complexa que a função de custo quadrático.

## Otimizadores: formas de ajuste de pesos

Serão citadas abaixo técnicas para ajustar os pesos das camadas intermediárias de forma que minimize o erro final.

### Gradient descendent

Em um gráfico gerado pela função de erro escolhida por parâmetros livres, o gradiente descendente é representado por vetores que indicam o mínimo global do gráfico, que minimiza o valor do erro.

### Batch gradient descendent algorithm (BGD)
É a aplicação do gradiente descendente em forma de lote, calculando o erro associado a cada uma das amostras do dataset. Esse algoritmo aprende bem, mas é bastante custoso pela fórmula que requer vários parâmetros devido à aplicação em cada uma das amostras.

### Stochastic gradient descendent algorithm (SGD)
Muito semelhante ao BGD, porém mais otimizado, porque, ao invés de aplicar em todas as amostras, é escolhida aleatoriamente uma das amostras para calcular o erro associado. Em relação ao BGD, tende a errar mais justamente por essa aleatoriedade.

### Mini-batch gradient descendent algorithm (MBGD)
Criado com base no BGD e no SGD, o MBGD escolhe um subconjunto de amostras para calcular o erro associado. A % que o subconjunto representa em relação ao dataset total deve ser escolhida pelo programador. Esse algoritmo gera resultados e custos computacionais intermediários entre BGD e SGD, por isso costuma ser o mais utilizado.

### Algoritmo de Backpropagation

Este algoritmo utiliza o gradiente descendente e estima o efeito dos erros das camadas intermediárias no erro da camada de saída, utilizando a função de erro escolhida.

- Utiliza a regra Delta generalizada.
- Requer funções de ativação contínuas e diferenciáveis, para evitar situações com derivada indefinida.
- A derivada parcial é utilizada para medir a contribuição de cada peso para o erro final. Caso a derivada seja positiva, significa que existe um aumento do erro. Caso a derivada seja negativa, signitica que existe uma diminuição do erro.

PS: Existem outros algoritmos baseados em gradiente descendente que são mais utilizados atualmente, como: AdaGrad, RMSProp, Adam, AdaMax, Nadam.

## Funções de ativação

Na camada de saída, as funções de ativação podem ser:

- Para tarefas de classificação, Sigmoid ou de Tangente Hiperbólica.
- Para tarefas de regressão, Linear.

<!-- ## Normalização

## Otimizadores -->

## Referências

- https://www.deeplearningbook.com.br/a-arquitetura-das-redes-neurais/
