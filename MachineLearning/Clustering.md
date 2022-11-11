# Clustering

Clustering pode ser visto como uma tarefa não supervisada.

## Aplicações
- Tarefa de preprocessamento antes de aplicar outra técnica de descobrimento
- Descobrimento de conhecimento para obter informações sobre a distribuição dos dados
- Tarefa não supervisada:
  -  Marketing: mapeamento de segmentos de clientes para direcionar políticas, ofertas,..
  -  Imóveis: mapeamento de imóveis de acordo com preço, tipo e endereço
  -  Documentos: classificação de documentos de acordo com padrões similares, assuntos,..

## Pontos de atenção antes de aplicar clustering
- **Cuidado com outliers!!** Eles podem aparecer na visualização como clusters solitários ou podem ser forçados a agregar um cluster, implicando na diminuição da qualidade dos clusters.
- O significado de cada cluster pode não ser óbvio, é necessária uma análise exploratória
- O número de clusters também pode não ser óbvio no início, para isso apresentaremos mais a frente algumas técnicas que podem ajudar na definição deste número

## Métricas de validação

Pode ser dizer que um clustering é bem feito quando a similaridade inter-cluster é máxima e a similaridade intra-cluster é mínima. Isso quer dizer que as instâncias pertencentes ao mesmo cluster devem estar unidas ao máximo na visualização e estas devem estar distantes das instâncias de outros clusters.

Também pode ser desejável que um método de cluster:
- Seja escalável
- Possa tratar distintos tipos de variáveis
- Consiga tratar dados com ruído e outliers
- Seja insensível à ordem dos dados de entrada
- Seja aplicável a datasets com altas dimensões
- Tenha resultados interpretáveis

## Medidas de distância e similaridade

### Atributos numéricos
- Distância euclideana
- Distância de Minkowski

Vale ressaltar a necessidade de normalizar os dados antes de aplicar os cálculos de distância nos casos em que essa medida seja sensível à faixa de valores da variável.

### Atributos nominais
Caso os valores sejam iguais, a distância será 0, caso os valores sejam diferentes, a distância será 1.


## Tipos de clustering
### Particional
Quando os dados são divididos em partições de acordo com um critério.

#### Métodos heurísticos
#### 

### Hierárquico
Quando os dados são divididos em partições hierárquicas de acordo com algum critério. Dessa forma, primeiro os dados são particionados grupos e depois estes grupos podem ser particionados outras vezes e outras vezes para gerar clusters diferentes.
 
#### Métodos aglomerativos
Começam com pequenos clusters e se calcula iterativamente a distância entre os clusters para que os clusters mais próximos se tornem um só.

#### Métodos divisivos
Começam com um cluster por dataset e a cada interação este cluster se divide em clusters menores até que chegue a uma condição de parada pré-determinada.
<!-- ### Baseados em densidade
### Baseados em grades
### Baseados em modelos -->

