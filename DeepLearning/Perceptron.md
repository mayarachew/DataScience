# Perceptron

## O que é?
Perceptron é um modelo, um neurônio, desenvolvido por Rossemblat em 1958. Este pode receber várias entradas e produz uma saída binária.

**Características:**
- Possui apenas uma camada ("single layer") com função de threashold, com pesos [-1, 0, 1].
- Estratégia de aprendizado: correção de erros ("error correction"). É criada uma curva/superfície/hyper-superfície que define o erro gerado pelos parâmetros livres, nesse caso o peso, e um valor mínimo global é encontrado para realizar o ajuste dos pesos.
- Função de ativação: produto interno da entrada pelo respectivo peso.
- Possui um parâmetro livre da rede neural chamado "bias" com peso associado e entrada sempre 1, que faz um ajuste do hyperplano.

## Para que pode ser utilizado?
- Cálculo de funções lógicas AND, OR e NAND.
- Problemas linearmente separáveis.

## Como funciona?

1) O modelo recebe um vetor de entradas [x1, x2, x3, ...].

2) O vetor de pesos [w1, w2, w3, ...] é multiplicado pelo vetor de entradas para expressar a importância de cada uma delas para a saída. Nessa etapa também são testados vários valores pesos e de "bias", os que gerarem os melhores resultados são escolhidos. O número de interações é finito, mas pode demorar consideravelmente dependendo desse ajuste.

3) É realizada uma soma ponderada com os valores resultantes e, se este valor for maior que o limiar ("threashold"), a saída é 1, mas se este valor for menor ou igual ao limiar, a saída é 0.

## Vantagens
- Um dos modelos mais simples, servindo de base teórica para outros.

## Desvantagens
- Resolve apenas problemas linarmente separáveis, cujos dados podem ser separados por uma reta/plano/hyper-plano em um espaço bidimensional. Porém, com mais de um Perceptron organizado em redes neurais de propagação direta ("feed-forward"), esse problema pode ser resolvido.

## Referências
- Diagrama explicativo de diferentes redes neurais e explicação do Perceptron: https://www.deeplearningbook.com.br/o-perceptron-parte-1/
- https://www.deeplearningbook.com.br/o-perceptron-parte-2/


