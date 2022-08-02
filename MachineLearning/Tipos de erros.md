# Tipos de erros

## Erros de treinamento
## Erros de teste
PS: É importante manter a distrinuição natural dos dados. Manipulações nessa distribuição podem alterar bastante os resultados e não são bem vistas. 

É importante manter a mesma distribuição nos dados de treinamento, validação e teste, ou seja, fazer uma amostragem aleatória respeitando a representatividade de classes.

Amostragem estratificada: amostragem aleatória mantendo a representatividade de classes entre os dados de treinamento/validação/teste.

Holdout: divisão dos dados entre treinamento (2/3) e teste (1/3).

Hiperparametro: não depende do aprendizado do modelo. precisa colocar manualmente;

Qual a diferença entre dados de validação e dados de teste?
os dados de validação utilizados para tunning de hyper parâmetros enquanto que os dados de teste servem para fazer a avaliação final do modelo.

Holdout com dados de validação:
70% para treinamento, 10% para validação e 20% para teste.
80% para treinamento, 10% para validação e 10% para teste.

De fato, isso diminui os dados de treinamento, mas pode ser necessário para tunning de hyper parâmetros, então o trade off vale a pena.

Validação cruzada:


## Stratified K-fold
Com muitos dados, stratified k-fold ajuda a medir a capacidade de escalonamento do modelo; É bom evitar modelos que possuem o desvio padrão alto avaliando diferentes trials no stratified k-fold, pois indica uma variação muito alta nos resultados, podendo gerar acurácias muito boas ou muito ruins dependendo dos dados de entrada. Vale mais a pena manter um modelo com desvio padrão baixo, que significa um modelo que obtém acurácias um tanto semelhantes para diferentes dados de entrada.
Com poucos dados, ele pode causar overfitting.

## Stratified K-fold com validação
Bom evitar caso tenha poucos dados, pois sobrarão poucas instâncias de cada uma das classes, o que pode dificultar o treinamento do modelo (leave one out pode ser uma saída nesse caso).
