# Redes neurais

## O que são?

De acordo com Hecht Nielsen, um pesquisador de redes neurais em U.S., uma rede neural é um sistema de computador composto por simples elementos interconectados, que processam informação por meio de uma resposta dinâmica a entradas externas.

As redes neurais simplificam o microestruturas e funções do cérebro humano com o objetivo de simular inteligência humana.

Uma rede neural é formada por 1 camada de entrada, n camadas intermediárias, 1 camada de saída e conexões que interligam todas as camadas. Essa topologia pode variar de acordo com a complexidade do problema, com a dimensionalidade dos dados de entrada e com a existência de recursos dinâmicos ou estáticos. Vale ressaltar que esta topologia quem define é o próprio desenvolvedor.

## Como funciona?

1. Recebe uma entrada ("input") de um objeto com atributos.

2. Um vetor é criado com pesos\* para serem aplicados ao objeto de entrada. Os pesos são ajustados nessa etapa.

\* Estes pesos podem ser > 0 ("excitatory") ou < 0 ("inhibitory").

3. Por meio de uma função de ativação, é realizada uma soma ponderada de acordo com o vetor no objeto de entrada, gerando a saída ("output").

## Tipos de redes neurais

- FeedForward Neural Networks
- Redes recorrentes
- Redes Conectadas Simetricamente

## Funções de ativação

### Linear
Deve-se tomar cuidado com funções lineares, pois costumam limitar o desempenho da rede por não conseguirem aprender bem com os dados.

### Threashold

### Sigmoid
Range: (0,1). Função monotônica*, contínua, não passa pela origem e não é simétrica. Derivada não monotônica, o que é um ponto negativo porque, para resultados da função de ativação pequenos ou altos possuem, a derivada possui valores semelhantes, o que pode atrapalhar a rede. Recomendada para redes menos profundas.

* Função sempre crescente ou sempre descrescente.

### "Hyperbolic Tangent" ou Tangente Hiperbólica
Range: (-1,1). Função monotônica, contínua, simétrica. Derivada não monotônica, contínua. Ao utilizá-la, é importante saber que os valores de saída podem ser negativos, por conta do range (-1, 1). Recomendada para redes menos profundas.

### Rectified Linear Unit (ReLU)
Se o valor for igual ou maior a um limiar, retorna um resultado x e se ficar abaixo deste limiar, retorna 0. Range: (0, infinito). Função monotônica, não contínua, não simétrica. Derivada com comportamento de degrau, não monotônica, não contínua, não tem derivada no 0. É muito utilizada por conta de sua simplicidade. Recomendada para redes mais profundas.

### Softplus
Se assemelha bastante com a ReLU. Possui derivada no 0, mas é um pouco mais custosa que a ReLU. Recomendada para redes mais profundas.

### Softmax
Em tarefas de classificação, geralmente é necessário utilizar a softmax na última camada, pelo fato de ela fazer uma cálculo ponderado com as probabilidades de ser determinada classe na camada de saída (tipo uma normalização).

Para Multilayer Perceptron recomenda-se a utilização de tangente hiperbólica ou sigmoid.

## Referências

- https://www.deeplearningbook.com.br/funcao-de-ativacao/
