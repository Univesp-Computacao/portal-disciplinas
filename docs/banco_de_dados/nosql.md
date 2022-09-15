# NOSQL - Not Only SQL

NoSQL fornece um modelo de dados que se adapta
melhor às necessidades da aplicação (modelagem mais
rápida e menos código).

Grande quantidade de dados: Necessita de
processamento em cluster (armazenamento dividido
entre vários servidores).

Favorece replicação de dados e escalabilidade.

## Replicação 

Master-Slave

O slave terá a cópia dos dados do master.
Escrita ocorre apenas no master e leitura em ambos.

é importante avaliar a questão sobre
consistência e performance quando não há falhas na
comunicação.

Masterless

muitos bancos NoSQL são baseados na ideia de que
qualquer servidor pode receber requisições de leitura e escrita.

Assim, mesmo com falha em um dos servidores do cluster, o
serviço se mantem disponível.

Teorema CAP (CAP Theorem):
* Consistência (C - Consistency); 
* Alta disponibilidade (A - Availability); 
* Tolerância a particionamento dos dados na rede (P - Partition-tolerance)

## Tipos de Banco de Dados NOSQL

**Banco de dados chave-valor:** os registros
pertencem a mesma coleção de elementos, e
todos possuem uma chave única. (Redis)

**Família de colunas (colunares):** todos os
registros fazem parte da mesma tabela, mas
podem conter diferentes colunas. (cassandra)

**Documento:** registros em coleções
específicas, mas não há esquema fixo de
registros (MongoDB)

**Grafo:** registros são nós de um grafo e são
interligados por relacionamentos.(Neo4j)