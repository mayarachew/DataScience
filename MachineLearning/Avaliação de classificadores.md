# Avaliação de classificadores

## Critérios de avaliação
Para avaliar um classificador, alguns critérios devem ser levados em consideração:
- **Precisão:** o quão precisos são os resultados obtidos
- **Velocidade:** o quão rápido eu consigo obter os resultados
- **Robustez:** o quão bem o modelo consegue lidar com dados desconhecidos; a sua capacidade de generalização
- **Escalabilidade:** qual a relação entre o aumento de tempo de processamento e o aumento da quantidade de dados
- **Interpretabilidade:** o quão compreensível e fácil de explicar é o modelo criado
- **Complexidade:** (varia de acordo com o modelo) qual o tamanho da árvore de classificação, qual a quantidade de regras de associação necessárias

## Métricas de avaliação
Existem diversas métricas de avaliação de classificadores, as principais estão listadas a seguir. Após conhecer cada uma delas, cabe a você decidir qual deve ser a melhor para avaliar os seus resultados, tendo em vista que nem todas as métricas são aplicáveis em todos os casos e que, consequentemente, podem gerar uma avaliação incoerente com a realidade ou com o que se quer medir.

### Matriz de confusão

### Conceitos básicos
- Verdadeiros positivos (VP): quando a classe predita é 1 e a real é 1 também
- Verdadeiros negativos (VN): quando a classe predita é 0 e a real é 0 também
- Falsos positivos (FP): quando a classe predita é 1, mas a real é 0
- Falsos negativos (FN): quando a classe predita é 0, mas a real é 1

Aqui o nosso cenário ideal é ter nenhum falso positivo e nenhum falso negativo :)

### Acurácia

Acurácia = (VP + VN) / (VP + VN + FP + FN)

Acurácia é simples e muito utilizada para avaliar classificadores, mas vale uma ressalva: para dataset desbalanceados, ela pode não refletir bem o desempenho do modelo. Por exemplo, em um dataset de fraude, poucas instâncias são fraudulentas, geralmente menos de 10%, então se o classificador definir que todos os dados do conjunto de teste são não fraudulentos temos uma alta acurácia, ao mesmo tempo que não identifica nenhuma amostra fraudulenta e consequentemente não é de muita serventia na tarefa de identificação de fraudes. 

As alternativas a seguir podem ser utilizadas para complementar a interpretação da métrica acurácia.

PS: Caso em que o modelo classifica tudo como 1 -> alta acurácia.

Assume uma classe como sendo a classe de interesse e calcular PR = VP/(VP+ FP)

### Revocação (recall)

Revocação = VP / (VP + FN)

Como o meu modelo está classificando instâncias positivas (predita) dentre todas as que são de fato positivas (real).

Utilizada quando precisamos minimizar os FN, ou seja, as predições negativas incorretas, nesse exemplo o diagnóstico da estar saudável quando se tem a doença.

### Precisão

Precisão = VP / (VP + FP)

Como o meu modelo está classificando instâncias positivas (predita) dentre todas as que foram preditas como positivas (predita).

Utilizada quando precisamos minimizar os FP, ou seja, as predições positivas incorretas, nesse exemplo o diagnóstico de ter a doença quando se está saudável.

PS: Para o caso do diagnóstico de uma doença, o mais indicado é utilizar a revocação para diminuir o diagnóstico de estar saudável quando se tem a doença, tendo em vista que uma pessoa que recebeu um diagnóstico saudável não irá procurar o médico novamente e a doença pode evoluir. No caso contrário, se uma pessoa recebeu o diagnóstico de uma doença estando saudável, ela irá ao médico novamente e descobrirá que se tratava de um alarme falso.

### F1-score
Média harmônica entre precisão e revocação.

### Curva ROC

https://sitiobigdata.com/2019/01/19/machine-learning-metrica-clasificacion-parte-3/#
