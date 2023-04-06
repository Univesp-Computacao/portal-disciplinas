# NOSQL - Not Only SQL

## Conceitos
Por muito tempo banco de dados Relacionais tem sido o principal meio de armazenamento de dados cuja ideia principal era representar
**entidade** e **relacionamento** de maneira **uniforme**.

Porém, o esquema rígida que o Modelo Relacional propõe não atende à algumas complexidades contemporâneas, principamente quando falamos de escalabilidade .


Hoje há novos desafios e o modelo NoSQL foi criado com o
objetivo de manipular volumes maiores de dados. Esse modelo não é orientado à tabelas, embora possa ter relacionamentos. 


As vantages do uso de NoSQL são sua **flexibilidade** e a sua **modelagem** que é mais rápida e exige menos código, além de lidar facilmente com grande volume de dados.

## Escalonamento
Quando falamos de escalonamento devemos considerar dois tipos: 

- **Escalonamento horizontal** (Scaling out) é a capacidade de
aumentar a quantidade de computadores. (mais complexo)
- **Escalonamento vertical** (Scaling up) é a capacidade de alocar
mais recursos ao computador (memória e processamento).


## Tipos de Banco de Dados NOSQL

- **Banco de dados chave-valor:** os registros
pertencem a mesma coleção de elementos, e
todos possuem uma chave única. (Ex.: Redis).

- **Família de colunas (colunares):** todos os
registros fazem parte da mesma tabela, mas
podem conter diferentes colunas. (Ex.:Cassandra).

- **Documento:** registros em coleções
específicas, mas não há esquema fixo de
registros. Pense num arquivo JSON. (Ex.: MongoDB).

- **Grafo:** registros são nós de um grafo e são
interligados por relacionamentos.(Ex.: Neo4j).


## Explorando o MongoDB

Em um documento podem existir um valor simples, como um número,
uma palavra ou uma data, e também uma lista de valores.
Os documentos são agrupados em collections.
Um conjunto de collections forma um database (banco de dados).
Se for necessário, esse database pode ser duplicado em outros servidores,
e cada cópia é chamada de replica set (conjunto de réplica).