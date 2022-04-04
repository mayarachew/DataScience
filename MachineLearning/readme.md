## Machine Learning

### O que é?

### Tipos de aprendizado

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

### Underfitting e Overfitting

**Underfitting**: quando o modelo não aprendeu o suficiente com os dados de treinamento para ter um bom desempenho nos dados de teste. O underfitting pode ser percebido quando o modelo tem resultados ruins quando aplicado em dados de treinamento e de teste.

**Overfitting**: quando o modelo aprendeu demais com os dados de treinamento e perdeu a capacidade de generalizar o modelo para novos dados. O Overfitting pode ser percebido quando o modelo tem ótimos resultados quando aplicado em dados de treinamento, mas resultados ruins com dados de teste.
