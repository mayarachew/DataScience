# Ensemble Learning

**Problema:** Algumas técnicas funcionam bem com alguns tipos de dados, devido a suas particularidades, mas não funcionam bem com outros dados pelo mesmo motivo. 

Ensemble Learning surgiu para combinar modelos simples mas que funcionam bem com alguns tipos de dados e produzir um resultado final mais assertivo. Por utilizar a melhor combinação entre modelo e dados, a performance das predições realizadas com Ensemble Learning são melhores do que as realizadas pelos modelos aplicados individualmente.

#### Tipos
- **Sequenciais:** quando os modelos são aplicados de forma sequencial. Neste caso a performance pode ser impulsionada por acumular conhecimento entre os classificadores.
- **Paralelos:** quando os modelos são aplicados em paralelo, sem que haja dependência de aprendizado.

## Categorias

### Métodos Bagging
Bagging aggregation realiza uma divisão do dataset em amostras menores, aplica modelos simples e independentes em cada uma delas e cria uma combinação com os modelos que obtiveram os melhores resultados. Os modelos são aplicados de forma paralela e o resultado é uma média dos resultados obtidos a partir dos modelos.

#### Passo-a-passo:
1) Dividir o dataset de treinamento em pequenas amostras;
2) Criar e aplicar diversos classificadores para cada uma das amostras;
3) Realizar a média de todas as predições para admití-la como a predição final.

### Métodos Boosting
Boosting é realizado com a aplicação sequencial de modelos preditivos a fim de produzir um modelo final mais robusto. O Boosting treina iterativamente os modelos a partir das dificuldades apresentadas pelos modelos anteriores, para tornar a predição mais assertiva e menos tendenciosa (menor bias).

#### Passo-a-passo:
1) Aplicar um modelo preditivo no dataset;
2) Observar as dificuldades do modelo anterior e aplicar outro modelo preditivo no dataset;
3) Observar se as dificuldades diminuíram;
4) Repetir os passos anterioes até que acabem os modelos preditivos a serem analisados;
5) Realizar a predição final.
