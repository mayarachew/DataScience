## Rotulação semi-automática

Utiliza a rotulação manual em alguns dados e ou outros são rotulados com a ajuda do aprendizado de máquina.

### Aprendizado ativo

1) Especialista recebe dados não rotulados
2) Especialista rotula alguns casos
3) Modelo de machine learning

#### questões a serem levadas em consideração antes desse processo:
- **direitos autorais:** quem é o dono do dataset? eu posso compartilhar?
- **disponibilidade:** eu posso utilizar esse dataset? é público? 
- **gênero textual:** qual é o gênero? existem termos específicos desse gênero de texto? qual o tipo de linguagem?
- **domínio**
- **tempo**

#### instanciação da teoria
- **categoria/etiquetas:** é importante descrever de forma "clara" o que significa cada categoria
- **esquema de anotação:** como deve ser anotado?
- **diretrizes**
- **manual**
- **concordância:** tem que resover a discordância e chegar em um concenso.
- **neutralização da teoria**

#### seleção e treinamento de anotadores
- risco de supertreino
- pouco treino
- falta se consistência no critério de anotação
- expertise dos anotadores (especialistas, entendedores, "leigos")
- quantidade de anotadores
- tipos de anotadores (voluntários e remunerados)

#### Especificação do procedimento de anotação
- anotações preliminares
- discussão de discordâncias
- presença de juíz
- quantidade de "passadas de anotação" (panotação + revisão/resolução de discordâncias)
- planejamento, cronograma de execução
- questões humanas (cansaço, vontade, erro, inconsistência)

#### Projeto de interface de anotação
- **facilidade:** ferramentas que facilitam como o INCEPTION, bi TAGTOC, TEAMTAT,LABELSTUDIO, 
- **sem bias:** cuidado com recomendações automáticas que influenciam
...

Ferramentas para anotação: Inception, BI,Tagtoc, Teamtat, LabelStudio.

### Métricas para avaliação de rótulos
#### Coeficiente Alfa de Krippendorff
Vantagens:
- Permite a presença de múltiplos anotadores por documento
- Presença de vários rótulos ou entidades
- Existência de valores ausentes
