# Teste A/B

<!-- Print the late_shipments dataset
print(late_shipments)

Calculate the proportion of late shipments
late_prop_samp = (late_shipments['late'] == "Yes").mean() -->

## Z-score
Esta métrica é utilizada para mensurar o quão longe da média o valor está. 
z = (x – μ) / σ

x = valor a ser comparado
μ = valor médio da população
σ = desvio padrão médio do valor da população

Exemplo: Vamos supor que você quer descobrir se é alto, médio ou baixo, por isso dediciu medir a sua altura. Após a medição, descobriu que possui 1,69m de altura, mas ainda não consegue tirar conclusões apenas com este número. 
_Será que sou baixo? Mas baixo em relação ao que?_ Bom, podemos comparar a sua altura com a altura média dos brasileiros! Supondo que você se identifica com o sexo feminino e que a altura média das mulheres brasileiras é 1,61 com variância de 0,20 em uma distribuição normal, podemos utilizar o z-score para realizar a comparação entre as suas medidas e a das brasileiras e finalmente descobrir se você tem uma estatura alta, média ou baixa.

z = (1,69 – 1,61) / 0,20
z = 0,4

A partir deste valor, concluímos que você está na média, pois ele está dentro do intervalo [-1, 1], que simboliza os 64% da população que possui entre 1,41m (1,61-0,2) e 1,81m (1,61+0,2) de altura. 
Quanto mais perto do 0 for o z-score, mais perto do valor médio o valor analisado está, e, quanto maior for o z-score em módulo, mais afastado do valor médio o seu valor está.
