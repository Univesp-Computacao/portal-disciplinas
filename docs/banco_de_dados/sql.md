SGBD é um pacote de software que facilita a criação e manutenção de um banco de dados. A manipulação dos dados é feita através da realização de operações como consultas, alteração de dados, emissão de relatórios, etc.

Controle de acesso: o SGBD oferece um subsistema de autorização e segurança que previne que usuários acessem dados sem que estejam autorizados.

Os SGBDs permitem que operações sobre os dados sejam definidas de maneira independente da aplicação.

Vantages da Abordagem baseada em SGBD
Persistência para programas e estruturas de dados (objetos).
Eficiência no processamento de consultas.
Oferecimento de sistemas de backup e recuperação.
Garantia das restrições de integridade.
Garante padrões.
Reduz o tempo de desenvolvimento de aplicações
Fornece flexibilidade e disponibilidade.
Promove economia de escala.
Sistema de Banco de Dados
Sistemas de BD são sistemas desenvolvidos com funções específicas, que usam Banco de dados, desenvolvidos em SGBDs. Sozinho um SGBD não significa nada, com um Banco de Dados e um programa escrito para sua manipulação forma-se um sistema de BD.



Modelo de Dados
Modelos de dados conceituais (alto nível)
Modelos de dados físicos (baixo nível)
Modelos de dados lógicos (representativos ou de implementação)
Instancias
Os dados em um determinado momento são chamados de instâncias.

A cada novo registro inserido ou removido, o estado (instância) do banco se altera.

Restrições / Chaves
Uma chave é um conjunto mínimo de valores dos atributos que identifica unicamente uma tupla (linha). Garante a restrição de unicidade entre as tuplas de uma relação

SQL (Structured Query Languagesql)
SQL tem uma ligação com o modelo relacional pois o resultado de uma consulta SQL é uma tabela (também chamada de conjunto resultado).

A linguagem SQL se divide em subgrupos:

DDL (Data Definition Language):

É a linguagem que define a ESTRUTURA do BD.
Seus comandos permitem a criação, alteração e exclusão de objetos em um banco de dados.
Exemplo: CREATE, ALTER, DROP
DML(Data Manipulation Language):

Linguagem que manipula os dados no banco.
Seus comandos permitem a recuperação, inserção, alteração e exclusão de dados.
Exemplo: INSERT. UPDATE, DELETE
DQL (Linguagem de consulta de Dados):

Comando SELECT é a instrução Básica para recuperar informações.
O formato básico da declaração SELECT é composto por três cláusulas (SELECT, FROM e WHERE).
O que significa ACID ?
Atomicidade (a transação é executada totalmente ou é executada)
Consistência (sistema sempre consistente após uma operação)
Isolamento (transação não sofre interferência de outra transação concorrente)
Durabilidade (o que foi salvo não é mais perdido) Força a consistência ao final de cada transação