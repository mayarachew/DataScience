# ULMFiT

Universal Learning Fine-tuning for Text Classification (ULMFiT) é um modelo de NLP criado em 2018 composto por 3 etapas:
- Pré-treinamento do modelo de linguagem com um dataset amplo para adquirir conhecimento da linguagem a ser utilizada
- Treinamento com o dataset de treinamento de uma tarefa específica
- Classificação do dataset de teste

Este modelo utiliza o princípio da transferência de aprendizado ("transfer learning"), por ter uma etapa de pré-treinamento inicial com um dataset maior, o que possibilita a utilização de um dataset menor para o treinamento da tarefa específica.

## Arquitetura
3 camadas AWD-LSTM (LSTM simples com otimização de hyperparâmetros de saída).

## Aplicações
- Classificação de textos (ele foi proposto inicialmente para esta tarefa).

## Referências
- https://www.analyticsvidhya.com/blog/2018/11/tutorial-text-classification-ulmfit-fastai-library/
