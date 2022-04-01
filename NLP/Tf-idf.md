### Tf-idf

#### O que é?

Tf-idf ("requency–inverse document frequency" ou frequência do termo–inverso da frequência nos documentos) é uma medida estatística que indica a importância de uma palavra de acordo com o contexto, baseada na frequência em que ela é utilizada em um conjunto de documentos de texto.

#### Para que pode ser utilizado?

- Criação de vetores de características para textos
- Recuperação de informações
- Mineração de dados

#### Como funciona?

O valor tf-idf de uma palavra aumenta conforme a frequência dela no texto aumenta, mas diminui conforme a frequência dela no dataset com todos os textos aumenta. Dessa forma, o tf-idf consegue encontrar as palavras mais importantes de cada um dos textos.

#### Vantagens

- É mais rápido que vários modelos de NLP como BERT, LSTM, Doc2vec e Word2vec.
- Por utilizar uma medida de frequência, o tf-idf pode ser uma boa abordagem para detectar o assunto principal de um texto.

#### Desvantagens

- Não pega tão bem o contexto das palavras (BERT pode ser melhor para isso).

## Referências

- https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfTransformer.html#:~:text=The%20formula%20that%20is%20used,document%20frequency%20of%20t%3B%20the
