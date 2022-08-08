# Regressão Linear

## Regressão Linear Simples
A regressão linear simples é utilizada em análises preditivas para:
- encontrar variáveis preditoras, que auxiliam a prever uma variável dependente;
- medir por magnitude e sinal o quanto as variáveis preditoras impactam a variável dependente.

Prevê a criação de uma equação linear para descrever o comportamento dos dados. Ela possui o seguinte formato:
Y_pred = a * X_real + b

X_real = variável independente (eixo x).
Y_pred = valor predito de um dado, de acordo com a variável X (eixo y).
a = variação de y por unidade de X (inclinação da reta).
b = valor de Y_pred quando X_real é zero (valor em que a reta corta o eixo y).

Para medir a eficácia deste modelo, é utilizado o Coeficiente de correlação:

### Coeficiente de correlação (R)
Este coeficiente mede a relação linear entre as duas variáveis analisadas. Valores variam de -1 a 1, sendo que valores próximos de 1 indicam uma maior correlação e valores próximos de -1 indicam uma menor correlação.

## Regressão Linear Múltipla
Esta variação da Regressão Linear pode ser utilizada quando existem mais de um atributos a serem utilizados na análise.
Y_pred = a0 * X0_real + a1 * X1_real + ... + an * Xn_real + b

Para medir a eficácia deste modelo, é utilizado o Coeficiente de determinação:

### Coeficiente de determinação (R²)
Mede o quanto o modelo representa e explica os dados apresentados. Valores variam de 0 a 1, sendo que valores próximos de 1 indicam que o modelo se ajusta bem aos dados e valores próximos de 0 indicam que o modelo não se ajusta bem aos dados.

## Referências
- Vídeo com exemplos explicativos: https://www.youtube.com/watch?v=ZqlgLMMOiRU
- Texto com a teoria: https://proeducacional.com/ead/curso-cga-modulo-i/capitulos/capitulo-4/aulas/analise-de-regressao-linear/
