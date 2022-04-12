# Recurrent Neural Network

Utilizam valores de um período de tempo anterior para predizer algum aspecto do tempo futuro, por isso é chamada de recorrente.

A saída da rede em um tempo t-1 é utilizada como entrada da próxima rede para predizer valores no tempo t.

LSTM
são podem ser utilizadas pra reter valores temporais.

Generative Adversarial Network
Construir duas redes: uma para gerar informação e outra para detectar se essa informação é real ou foi criada artificialmente.
Pode ser utilizada para criar uma imagem 
Treinamento não supervisionado (sem rótulo), mas sabemos se a imagem é real ou artificial
Rede generativa: gera entrada fake
Rede descriminadora: detecta imagens reais
Pode ser utilizado para criar pinturas no estilo de algum artista, um texto, uma imagem.
Treinamento precisa ocorrer de forma gradual nas duas

Data imbalance desbalanceamento
afeta algoritmos de machine learning
Soluções: undersampling (remover amostras da classe majoritária), oversampling (duplicar amostras da classe minoritária), synthetic minority
undersampling é recomendada
synthetic minority oversampling technique (SMOTE) utilizado em dados tabulares BOM, pega duas amostras da classe minoritária e faz uma interpolação para a criação de uma nova

vanishing gradient/: diminuição/decrescimo do gradiente ao longo das camadas ocultas, vai ficando mais difícil fazer o ajuste das redes ocultas em uma rede muito profunda. quanto mais profunda a camada, mais lento é o ajuste (e pior).l independe da técnica utilizada

