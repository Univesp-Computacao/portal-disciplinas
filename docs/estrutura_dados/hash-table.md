# Tabela Hash

## Definição
Também conhecida como **tabela de dispersão**, **tabela de espalhamento** ou **tabela de indexação** é uma estrutura de dados que associa chaves e valores. 

Em outras linguagens de programação pode ser referida como: dicionários, arrays associativos, mapas, entre outros.

A forma mais simples de se pensar em uma tabela hash é como um vetor de registros.


## Visualização 

![hash-table](https://user-images.githubusercontent.com/72423464/188959969-e626ebe8-0bce-40bd-9a03-ab00303133aa.gif)


## Características

- Tabelas hash armazenam uma coleção de registros com chaves;
- A partir da aplicação de uma função, a chave é transformada em um endereço da tabela; 
- Cada chave é interpretada como um valor numérico, um índice no vetor;
- O local de um novo registro depende do valor hash de sua chave;
- Quando ocorre uma colisão, é usado o próximo local disponível;
- É possível encadear os valores em um índice usando listas ligadas;
- Quando removemos um registro, o local deve ser marcado para facilitar as buscas.

## Inserindo novo registro

Supondo que estamos implementando uma tabela hash de tamanho **11** indexado de **0 a 10**. 

Se fizermos a inserção de valores menores do que o tamanho da tabela, eles serão inseridos no índice correspondente ao valor da chave, como por exemplo, no caso de adicionarmos chaves de valor **2**, **5** e **9**.

![image](https://user-images.githubusercontent.com/72423464/188945443-c803065c-bb7b-461b-b79b-211c3750b3a1.png)


Para casos em que o valor da chave é maior que o tamanho da tabela, precisamos usar uma **função de dispersão**.

Uma função de dispersão _h_ transforma uma chave _x_ em um endereço-base _h(x)_ na tabela hash.

Se utilizarmos o **Método da Divisão** teremos que encontrar o resto da divisão do valor da chave pelo tamanho da tabela.

Por exemplo, se temos uma chave de **valor 15** ela será inserida no **índice 4**, pois ```15 % 11 = 4```

![image](https://user-images.githubusercontent.com/72423464/188945769-6eb289cd-9296-4f6f-9d4a-d7564a0c79a9.png)


## Função de Dispersão / _Hash Functions_



Uma função de dispersão é utilizada para espalhar os elementos que queremos armazenar e deve satisfazer as seguintes condições: 

- produzir um número baixo de colisões;
- ser facilmente computável;
- ser uniforme.

O **Método da Divisão** costuma ser o mais fácil e eficiente, além de ser muito utilizado.
Existem alguns critérios em relação ao tamanho da tabela que ajudam a obter resultados mais práticos, tais como:

- O tamanho da tabela não deve ser número par;
- Não deve ser potência de 2;
- Deve ser, de preferência, um número primo.

Além do Método da Divisão, podemos usar o **Método da Dobra** e o **Método da Multiplicação** .

### Transformação Alfa-numérica

Também temos casos em que as chaves não são valores numéricos, como o nome de pessoas.
A solução para isso é transformar o texto em número, já que, do ponto de vista do computador, **todos os dados são representações numéricas**.

Como na tabela ASCII existe um inteiro associado a um caractere, podemos somar caractere por caractere para obter uma chave numérica. Se temos uma chave de valor "Fulano", teremos após a função, uma chave de valor 613.

| Caractere   | Inteiro            |
| ------------- |:-------------:|
| "F"   | 70 |
| "u"      |  117    |
| "l" | 108      |
| "a" | 97      |
| "n" | 110      |
| "o" | 111      |
| **Soma:** |  **613**     |


## Tratamento de Colisões

As colisões ocorrem quando chaves diferentes são mapeadas para o mesmo endereço de memória, o que pode causar ambiguidades sobre o registro que deverá ocupar aquele endereço de memória.

Para resolver colisões, podemos utilizar tanto um espaço de memória adicional quanto um espaço no próprio arranjo.

### Encadeamento Separado

Também conhecido como encadeamento exterior, ou em inglês como _separate chaining_.

Cada célula da tabela hash seria na verdade um ponteiro para uma lista encadeada, com isso as colisões são mantidas em uma estrutura de dados separada.  



### Teste Linear

Também conhecido como sondagem linear ou em inglês, como _linear probing_, _open adressing_ ou _rehash_ .

Quando ocorre uma colisão, percorre-se a tabela hash buscando por uma posição ainda não ocupada.

As colisões serão tratadas sem alocação de memória adicional, ou seja, todos os elementos estão armazenados na própria tabela hash.




### Fator de Carga

- Fator de carga é a divisão dos números ocupados em uma tabela pelo tamanho total da tabela.
- Quanto maior o fator de carga, mais lento é o processo de recuperação. 
- No encadeamento separado, o fator de carga assume valor maior que 1.
- No encadeamento aberto, o fator de carga assume valor entre 0 e 1.
 
## Aplicações da Tabela Hash

- Busca de elementos em base de dados.
- Verificação de integridade de dados e autenticação de mensagens. 
- Armazenamento de senhas com segurança.
- Criptografia (MD5 e SHA).


---

# Referências
- [IFRN - Estrutura de Dados- Profa. Camila Taumaturgo]([url](https://docente.ifrn.edu.br/camilataumaturgo/disciplinas/2014.2/estruturas-de-dados/tabela-hash))
- [USP - Hash Table - Apresentação]([url](https://dcm.ffclrp.usp.br/~augusto/teaching/icii/Hash-Tables-Apresentacao.pdf))
- [Medium - Jamin Lee - Has Table Animations]([url](https://junminlee3.medium.com/hash-tables-animations-that-will-make-you-understand-how-they-work-d1bcc850ba71))
- [IME - USP - Hashing]([url](https://www.ime.usp.br/~pf/estruturas-de-dados/aulas/st-hash.html))
- [Acervo Lima - Encadeamento Separado]([url](https://acervolima.com/hashing-conjunto-2-encadeamento-separado/)) 
