# Regression models

## Decision Tree Regression
Este modelo é uma árvore de decisão, na qual parte de um nó e este é ramificado em diversos galhos, cada um indicando uma característica observada dos dados. Pode ser exemplificada por várias condições if-else.

## Random Forest Regression
Random Forest é um "ensemble" de árvores de decisão. De acordo com a característica do dado, este modelo escolhe uma árvore de decisão para aplicar à instância analisada, dessa forma, a acurácia aumenta e o overfitting diminui em comparação ao modelo Decision Tree. 

### Quando utilizar?
Quando a tendência dos dados forem não lineares e o problema de não poder extrapolar os dados de treinamento não for relevante. Não é recomendado o seu uso quando os dados possuem formato de série temporal, porque a tendência de crescimento e decrescimento é importante nesse caso e o Random Forest não será capaz de obter bem essas tendências.

### Problema de extrapolação
Os valores preditos nunca ultrapassam os valores de treinamento. Dessa forma, uma tendência de crescimento nos dados não vai ser mantida, pois o valor predito não pode ser maior que os valores de treinamento.

- https://www.geeksforgeeks.org/random-forest-regression-in-python/
- Comparação entre Decision Tree e Random Forest + Problema de extrapolação: https://neptune.ai/blog/random-forest-regression-when-does-it-fail-and-why
- 
