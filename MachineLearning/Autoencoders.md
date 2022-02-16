Autoencoders são "generative models", tendo em vista que são não supervisionados e têm o objetivo de descobrir/detectar padrões nos dados de entrada de forma a criar novos dados semelhantes aos da entrada.

### Autoencoders simples

#### O que é?
Os autoencoders são uma técnica de aprendizado não supervisionado que utiliza redes neurais para codificar uma entrada (por meio de neurônios) e depois decodificá-la para gerar uma nova representação como saída. Ou seja, é uma técnica que aprende a partir de exemplos e gera saídas com dimensões (geralmente) menores e propriedades úteis extraídas dos exemplos originais.

PS: A dimensão da saída costuma ser menor, pois a saída deve conter apenas as propriedades principais da entrada. Essas propriedades são ditas úteis/principais porque a partir delas deve ser possível reconstruir a entrada.

**Características:**
- Não supervisionado (Alguns dizem que é auto supervisionado) 

#### Para que pode ser utilizado?
- Remoção de ruídos
- Redução de dimensionalidade para visualização de dados

#### Como funciona?
Ele codifica os nós de entrada em nós ocultos (neurônios) e os decodifica em nós de saída.

A codificação é feita por sinapses positivas e negativas.

#### Vantagens

#### Desvantagens

### Autoencoders Variacionais (VAEs – Variational Autoencoders)

#### O que é?
Autoencoders Variacionais são uma variação dos Autoencoders Simples que permitem a utilização das propriedades extraídas dos dados de entrada para a geração de novos dados. 

#### Como funciona?
A geração de novos dados é possível porque os dados de treinamento são regularizados de forma que evite o sobreajuste e garanta que o espaço latente tenha propriedades mais assertivas na hora de gerar os novos dados. Por exemplo, os dados de entrada podem ser imagens manuscritas da letra "A", então o espaço latente pode ser gerado ressaltando importantes propriedades da letra "A" e deixando-a em alta definição e, a partir deste espaço latente, os dados podem ser gerados com leves modificações.

**Características:**
- Não supervisionado (Alguns dizem que é auto supervisionado) 

#### Para que pode ser utilizado?
- Geração imagens

#### Vantagens

#### Desvantagens
