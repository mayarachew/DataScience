# Tipos de Arquivos

## Parquet (.parquet)
Arquivo com armazenamento em formato de coluna para facilitar buscas, diminuindo assim o tempo da busca e o custo de armazenamento.

- Suporta armazenamento de dados estruturados (com tipos);
- Utilizado em analytics use cases (OLAP);
- Utilizado para big data;
- Menos custos;
- Buscas rápidas.

## JSON 

### JSON Multiline (.json)
- Utiliza UTF-8 Encoding;
- O JSON de um registro pode ocupar mais de uma linha.

### JSON Line (.jsonl)
JSON Line ou newline-delimited JSON.

- Utiliza UTF-8 Encoding;
- Cada linha é um valor JSON válido;
- Para separar uma linha da outra, é utilizado '\n'.

## Referências
- O que é Parquet: https://databricks.com/glossary/what-is-parquet
- Documentação do Parquet: https://parquet.apache.org/
- Documentação do JSON lines: https://jsonlines.org/
