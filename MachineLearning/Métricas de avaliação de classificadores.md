# Métricas de avaliação de classificadores

Existem diversas métricas de avaliação de classificadores, as principais estão listadas a seguir. Após conhecer cada uma delas, cabe a você decidir qual deve ser a melhor para avaliar os seus resultados, tendo em vista que nem todas as métricas são aplicáveis em todos os casos e que, consequentemente, podem gerar uma avaliação incoerente com a realidade ou com o que se quer medir.

## Matriz de confusão

## Acurácia
Acurácia é simples e muito utilizada para avaliar classificadores, mas vale uma ressalva: para dataset desbalanceados, ela pode não refletir bem o desempenho do modelo. Por exemplo, em um dataset de fraude, poucas instâncias são fraudulentas, geralmente menos de 10%, então se o classificador definir que todos os dados do conjunto de teste são não fraudulentos temos uma alta acurácia, ao mesmo tempo que não identifica nenhuma amostra fraudulenta e consequentemente não é de muita serventia na tarefa de identificação de fraudes. 

As alternativas a seguir podem ser utilizadas para complementar a interpretação da métrica acurácia.

## Precisão
Assume uma classe como sendo a classe de interesse e calcular PR = VP/(VP+ FP)

## Revocação
Como o meu modelo está classificando instâncias positivas.

## F1-score
Média harmônica entre precisão e revocação.

## Taxa de verdadeiro positivos

## Taxa de falsos positivos

## Curva ROC
