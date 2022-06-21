# Ensemble Learning

**Problema:** Algumas técnicas funcionam bem com alguns tipos de dados, devido a suas particularidades, mas não funcionam bem com outros dados pelo mesmo motivo. 

Ensemble Learning surgiu para combinar modelos simples mas que funcionam bem com alguns tipos de dados e produzir um resultado final mais assertivo. Por utilizar a melhor combinação entre modelo e dados, a performance das predições realizadas com Ensemble Learning são melhores do que as realizadas pelos modelos aplicados individualmente.

PS: Vale ressaltar que nem sempre Ensemble Learning gera a melhor performance em comparação com os modelos individuais, mas é uma técnica que pode sim melhorar a performance, então pode fazer sentido aplicar e ver a performance aumenta.

#### Tipos
- **Sequenciais:** quando os modelos são aplicados de forma sequencial. Neste caso a performance pode ser impulsionada por acumular conhecimento entre os classificadores.
- **Paralelos:** quando os modelos são aplicados em paralelo, sem que haja dependência de aprendizado.

## Categorias

### Bagging
Bagging aggregation realiza uma divisão do dataset em amostras menores, aplica modelos simples e independentes em cada uma delas e cria uma combinação com os modelos que obtiveram os melhores resultados. Os modelos são aplicados de forma paralela e o resultado é uma média dos resultados obtidos a partir dos modelos.

#### Passo-a-passo:
1) Dividir o dataset de treinamento em pequenas amostras;
2) Criar e aplicar diversos classificadores para cada uma das amostras;
3) Realizar a média de todas as predições para admití-la como a predição final.

### Boosting
Boosting é realizado com a aplicação sequencial de modelos preditivos a fim de produzir um modelo final mais robusto. O Boosting treina iterativamente os modelos a partir das dificuldades apresentadas pelos modelos anteriores, para tornar a predição mais assertiva e menos tendenciosa (menor bias).

#### Passo-a-passo:
1) Aplicar um modelo preditivo no dataset;
2) Observar as dificuldades do modelo anterior e aplicar outro modelo preditivo no dataset;
3) Observar se as dificuldades diminuíram;
4) Repetir os passos anterioes até que acabem os modelos preditivos a serem analisados;
5) Realizar a predição final.

### Adaptative Boosting
Atua de forma semelhante ao Boosting, mas adiciona um peso padrão na inicialização de cada modelo, que define o peso da predição deste modelo no resultado final. Assim, os modelos com maior precisão terão mais peso na decisão do modelo final.

### Gradient Boosting
Atua de forma semelhante ao Boosting também, mas treina os modelos diretamente nas dificuldades observadas na predição de modelos anteriores, ou seja, no erro deles.

### Stacking
Neste método, as predições dos modelos são utilizadas como features, assim, o modelo final tem mais certeza de onde os modelos performaram melhor e coloca mais peso, enquanto coloca menos peso aonde os modelos performaram pior.

## Aplicações
- Conjunto de dados não balanceado

## Referências
- Conceito e exemplo prático: https://medium.com/turing-talks/turing-talks-24-modelos-de-predi%C3%A7%C3%A3o-ensemble-learning-aa02ce01afda
- Pacote para ensemble learning no Scikit Learn: https://scikit-learn.org/stable/modules/ensemble.html
- Aula sobre Ensemble Learning e exemplos: https://www.youtube.com/watch?v=WtWxOhhZWX0&ab_channel=Simplilearn
- Aula sobre Ensemble Learning para dados desbalanceados: https://www.youtube.com/watch?v=53uUM_5rRtA&ab_channel=Dr.DataScience
- Exemplo de stratified K-Fold com BaggingClassifier da Scikit Learn: https://machinelearningmastery.com/bagging-and-random-forest-for-imbalanced-classification/
