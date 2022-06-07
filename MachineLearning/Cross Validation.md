# Cross Validation (Validação Cruzada)

Um bom modelo precisa ter bons resultados de acurácia quando aplicado a novos dados, não sendo afetado por overfitting ou underfitting. Neste contexto, novos dados são considerados dados que não foram utilizados para o treinamento ou validação do modelo a ser avaliado.

A cada vez que adicionamos novos dados para realizar a predição e coletarmos a acurácia do modelo, temos resultados distintos para cada novo conjunto de dados. Com o objetivo de deixar a validação do modelo mais confiável, podemos fazer vários testes e obter um valor médio dos resultados de validação de cada uma das tentativas, esse método se chama Cross Validation ou Validação Cruzada.

Existem diversas técnicas de validação cruzada que podem ser utilizadas para avaliar um modelo, dentre elas: K-Fold Cross Validation, Stratified K-Fold Cross Validation, Leave One Out Cross Validation; que serão abordadas a seguir:

## K-Fold Cross Validation

Este método cria uma validação cruzada a partir de um número específico k de partições, ou seja, o conjunto todo será dividido entre k partes, sendo uma delas de teste e as outras de treinamento. A cada iteração, uma das partes será a de teste, até que todas as possibilidades se esgotem. A acurácia será calculada em todos os casos.

## Stratified K-Fold Cross Validation

De forma semelhante ao K-Fold Cross Validation, este método também faz k partições do dataset em treinamento e teste, porém leva em consideração a proporção das categorias. Dessa forma, todas partições devem conter a mesma proporção de categorias de treinamento e teste. Esse método evita problemas relacionados ao desbalanceamento dos dados que existem no K-Fold Cross Validation.

## Dúvidas recorrentes

- Como utilizar o K-Fold Cross Validation em dados que precisem ser divididos entre treinamento, validação e teste?

Por padrão, o K-Fold é implementado na biblioteca Scikit Learn levando em consideração apenas a divisão entre treinamento e teste, mas podemos utilizar o método duas vezes e obter a divisão entre treinamento, validação e teste. Por exemplo, podemos aplicar o K-Fold para obter dados de treinamento e teste, depois disso, podemos aplicá-lo novamente nos dados de treinamento para dividir este conjunto de dados e obter uma parte dele para a validação.

Passo a passo:
1º K-Fold no conjunto todo -> Gera treinamento e teste
2º K-Fold no conjunto de treinamento -> Gera treinamento' e validação

Assim, o conjunto final de cada iteração será composto por: Treinamento' + validação + teste

## Referências

- Biblioteca Scikit Learn: https://scikit-learn.org/stable/modules/cross_validation.html
- Explicação mais detalhada de Cross Validation: https://towardsdatascience.com/cross-validation-explained-evaluating-estimator-performance-e51e5430ff85
- Exemplo (código) de Stratified K-Fold Cross Validation: https://github.com/viniciusrpb/cloud_image_classification/blob/main/selenastraceae_greenalga_classification.ipynb
