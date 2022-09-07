# Tabela Hash

## Definição
Também conhecida como **tabela de dispersão** ou **tabela de espalhamento** é uma estrutura de dados que associa chaves e valores. Em outras linguagens de programação pode ser referida como: dicionários, arrays associativos, mapas, entre outros.

A forma mais simples de se pensar em uma tabela hash é como um vetor de registros.


## Visualização 

![hash-table](https://user-images.githubusercontent.com/72423464/188905735-a5572714-0d85-4ada-9c12-4661fe17d562.gif)

## Características

- Tabelas hash armazenam uma coleção de registros com chaves;
- A partir da aplicação de uma função, a chave é transformada em um endereço da tabela; 
- Cada chave é interpretada como um valor numérico, um índice no vetor;
- O local de um novo registro depende do valor hash de sua chave;
- Quando ocorre uma colisão, é usado o próximo local disponível;
- É possível encadear os valores em um índice usando listas ligadas;
- Quando deletamos um registro, o espaço vazio ganha uma conotação especial.

## Inserindo novo registro

Supondo que estamos implementando uma tabela hash de tamanho **11** indexado de **0 a 10**. 

Se fizermos a inserção de valores menores do que o tamanho da tabela, eles serão inseridos no índice correspondente ao valor da chave, como por exemplo, no caso de adicionarmos chaves de valor **2**, **5** e **9**.

![image](https://user-images.githubusercontent.com/72423464/188945443-c803065c-bb7b-461b-b79b-211c3750b3a1.png)


Para casos em que o valor da chave é maior que o tamanho da tabela, precisamos usar uma **função de dispersão**.

Uma função de dispersão _h_ transforma uma chave _x_ em um endereço-base _h(x)_ na tabela hash.

Se utilizarmos o **Método da Divisão** teremos que encontrar o resto da divisão do valor da chave pelo tamanho da tabela.

Por exemplo, se temos uma chave de **valor 15** ela será inserida no **índice 4**, pois ```15 % 11 = 4```

![image](https://user-images.githubusercontent.com/72423464/188945769-6eb289cd-9296-4f6f-9d4a-d7564a0c79a9.png)


## Função de Dispersão

Uma função de dispersão deve satisfazer as seguintes condições: 

- produzir um número baixo de colisões;
- ser facilmente computável;
- ser uniforme.

O **Método da Divisão** costuma ser o mais fácil e eficiente, além de ser muito utilizado.
Existem alguns critérios em relação ao tamanho da tabela que ajudam a obter resultados mais práticos, tais como:

- O tamanho da tabela não deve ser número par;
- Não deve ser potência de 2;
- Deve ser, de preferência, um número primo.

Além do Método da Divisão, podemos usar o **Método da Dobra** e o **Método da Multiplicação** .

### Transformação alfa-numérica

Também temos casos em que as chaves não são valores numéricos, como o nome de pessoas.
A solução para isso é transformar o texto em número, já que, do ponto de vista do computador, **todos os dados são representações numéricas**.

Como na tabela ASCII existe um inteiro associado a um caractere, podemos somar caractere por caractere para obter uma chave numérica. Se temos uma chave de valor "Fulano":

| Caractere   | Inteiro            |
| ------------- |:-------------:|
| "F"   | 70 |
| "u"      |  117    |
| "l" | 108      |
| "a" | 97      |
| "n" | 110      |
| "o" | 111      |
| **Soma:** |  **613**     |

O valor numérico para a chave "Fulano" seria 613.

## Colisões

 As colisões ocorrem quando chaves diferentes são mapeadas para o mesmo endereço de memória, o que pode causar ambiguidades sobre o registro que deverá ocupar aquele endereço de memória.
 
 🚧 🚧 🚧

---

# Referências
- [IFRN - Estrutura de Dados- Profa. Camila Taumaturgo]([url](https://docente.ifrn.edu.br/camilataumaturgo/disciplinas/2014.2/estruturas-de-dados/tabela-hash))
- [USP - Hash Table - Apresentação]([url](https://dcm.ffclrp.usp.br/~augusto/teaching/icii/Hash-Tables-Apresentacao.pdf))
- [Medium - Jamin Lee - Has Table Animations]([url](https://junminlee3.medium.com/hash-tables-animations-that-will-make-you-understand-how-they-work-d1bcc850ba71))
