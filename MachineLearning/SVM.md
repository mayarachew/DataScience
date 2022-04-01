### SVM

#### O que é?

SVM ("Support Vector Machine") é um algoritmo de aprendizado supervisionado.

*** Hyper-parâmetros ***

- kernel: uma função utilizada pelo algoritmo que define a complexidade dos dados.
  - linear: esta é a função linear, a menos complexa dentre estas opções.
  - poly: função polinomial.
  - rbf: "radial basis function", uma função de base radial, esta busca curvas ao redor dos pontos. Um dos kernels mais complexos.
  - sigmoid: função de tangente hiperbólica.

#### Para que pode ser utilizado?

- Tarefas de classificação.
- Tarefas de regressão.

#### Como funciona?

1) Cada amostra no conjunto de dados é plotado no espaço n-dimensional de acordo com a sua respectiva coordenada.
2) É escolhido um hyperplano com base na função utilizada como hyperparâmetro. 
3) Este hyperplano é ajustado no espaço n-dimensional de forma que exista a maior distância possível (margem) entre o hyperplano e as amostras. 
4) Após tendo encontrado a melhor posição do hyperplano, os dados são classificados de acordo com essa divisão.

#### Vantagens

- Robusto para outliers.
- Eficaz em situações que o número de dimensões é maior que o número de amostras.
- Eficiente em termos de memória, por utilizar um subconjunto de dados de treinamento na função de decisão.

#### Desvantagens

- O tempo de treinamento é longo, por isso não possui um bom desempenho em um conjunto de dados grande.
- Não funciona bem em dados com ruído/classes sobrepostas.

## Referências

- Implementação scikit-learn: https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html
- Explicação sobre hyperparâmetros do SVM: https://ichi.pro/pt/hiperparametros-svm-explicados-com-visualizacoes-22257741819931
- Equação de cada um dos kernels: https://data-flair.training/blogs/svm-kernel-functions/
- Funcionamento e exemplos: https://www.inf.ufpr.br/dagoncalves/IA07.pdf

