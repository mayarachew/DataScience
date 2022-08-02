# Conceitos Básicos

## Níveis de linguagem

- **Fonética/Fonologia:** estuda os sons de uma língua específica, incluindo fonemas e pronúncia.
- **Morfologia:** estuda a construção e formação de palavras.
- **Sintaxe:** estuda a integração entre as palavras.
- **Semântica:** estuda a o significado da palavra dentro de determinado contexto.
- **Pragmática/Discurso:** estuda a conexão entre palavras para tornar a frase compreensível por meio de conectores e outros elementos.

## Modelo de linguagem

A partir de um modelo de linguagem é possível completar diversas tarefas.

### Tipos

- Modelos de linguagem probabilísticos: N-grams, Hidden Markov Models, Regras Linguísticas.

Regra da cadeia
P("oi tudo bem") = P(oi,tudo,bem) = P(OI) \* T(tudo|oi) \* P(bem|tudo,oi)

Regra da cadeia menor (menor custo computacional e menor processamento computacional)
P("oi tudo bem") = P(oi,tudo,bem)
= P(OI) \* T(tudo|oi) \* P(bem|tudo,oi)

Andrei Markov
P("oi tudo bem") ~= P(oi| bem)

Teorema de Bayes
P(A,B) = P(B,A)
P(A,B) = P(A)P(B|A)
P(B)P(A|B) = P(A)P(B|A)
P(A|B) = P(A)P(B|A)/P(B)

- Modelos de linguagem baseados em redes neurais

## Referências

Cuidado com stemmização:
Fernanda -> Fer (nome próprio não deve ser stematizado)
Ferver -> Fer (stematização errada) -> Ferv (stematização correta)

- Tarefas de NLP: http://nlpprogress.com/
