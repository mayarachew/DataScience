# DataScience
Anotações de estudo sobre Data Science.

## Sumário
0) Aprendizado supervisionado x não supervisionado
0) Matriz de confusão
1) Autoencoders
2) Multinomial Naive Bayes Classifier

## Notebook

### Aprendizado supervisionado x não supervisionado

#### Aprendizado supervisionado
**Dados:** Dados de treinamento rotulados;x: dados; y: rótulo.

**Objetivo:** Aprender uma função que gere algo a partir dos dados de treinamento (entrada); x -> y.

**Exemplos:**
- Classificação
- Detecção de objetos
- Semantic segmentation (segmenta uma imagem de acordo com características dos pixels)
- Captação de imagem (transforma uma imagem em frases)

#### Aprendizado não supervisionado
**Dados:** Dados de treinamento não rotulados.

**Objetivo:** Aprender propriedades/estruturas "escondidas" a partir dos dados informados.

**Exemplos:**
- Clustering
- Redução de dimensionalidade
- Feature learning (aprende propriedades específicas)
- Density estimation (estima a distribuição/densidade dos dados)


### Matriz de confusão
- TP: "true positive", classificado certo como positivo
- FP "false positive", classificado errado como positivo
- TN: "true negative", classificado certo como negativo
- FN: "false negative", classificado falso como negativo

|                                     | Label real positiva | Label real negativa  | 
| ----------------------------------- | ------------------- | -------------------- |
| Label definida pelo modelo positiva | `true positive`     | `false positive`     |
| Label definida pelo modelo negativa | `false negative`    | `true negative`      |



- **"Accuracy"**: Porcentagem de amostras rotuladas corretamente, de acordo com a predição do modelo. Esta métrica não funciona bem com dados cujas classes são desbalanceadas, dessa forma não é comumente utilizada para classificação de textos.
```
accuracy = (TP + TN)/(TP + FP + TN +FN)
```
- **"Precision"**: Porcentagem de amostras rotuladas corretamente como uma classe x, em relação todas as amostras rotuladas como uma classe x.
```
precision = TP/(TP + FP)
```

- **"Recall"**: Porcentagem de amostras rotuladas corretamente como uma classe x, em relação às amostras reais pertencentes a essa classe x.
```
recall = TP/(TP + FN)
```

- **"F-measure"**: (f1_score) Média harmônica ponderada das medidas de "precisão" e "recall".
```
F = [(B^2 + 1)PR]/(B^2P +R)
```

### Multinomial Naive Bayes Classifier
#### O que é?

Características:
- High bias
- Low variance

#### Para que pode ser utilizado?
Análise de sentimentos, detecção de spam em emails.
#### Como funciona?
#### Vantagens

#### Desvantagens
Este classificador é "naive" (ingênuo) por não considerar a ordem das palavras, o que pode ser uma super desvantagem!

Veja só, a palavra "não" e a palavra "quero" possuem significados próprios e, quando elas são conectadas "não quero", elas possuem um significado conjunto. O Naive Bayes considera as palavras como se fossem isoladas, não considerando regras gramaticais e o contexto na qual elas estão inseridas. Então, em um texto com "não quero", ele processaria o "não" separado de "quero".

Por ignorar a relação entre as palavras, pode-se dizer que Naive Bayes possui "high bias".

#### Materiais de referência
- Aplicação em SPAM de emails: https://www.youtube.com/watch?v=O2L2Uv9pdDA

Pode ser utilizado para 


