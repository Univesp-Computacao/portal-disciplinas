# Conceitos Básicos C++

Criada como uma extensão da linguagem C pelo dinamarquês Bjarne Stroustrup, o "C com classes" é uma linguagem multiparadigma, quase sempre implementada de modo compilado,considerada uma linguagem de nível médio. Apareceu pela primeira vez em 1985 e ainda hoje é amplamente utilizada em sistemas embarcados, jogos, bibliotecas gráficas, sistemas operacionais entre outros.

## Hello World em C++

```C++
#include <iostream>

int main()
{
    std::cout << "Hello, world!\n";
}
```


- `#include <iostream>`: biblioteca utilizada para declarar objetos que realizam o controle do input e do output estabelecidos no código.
- `int main()`: função utilizada para demonstrar o ponto de início de execução do programa.
- `std::cout << "string";`: função padrão para enviar dados para o console imprimi-los em forma de texto. 

# Tipos de Dados em C++

- **Bool:** valores True or False, em geral armazenam 1 byte
- **Char:** aramazena um único caracter também de um byte, como "a", ou "b" e assim por diante
- **Int:** utiliza 4 bytes e armazenam números inteiros entre -2.147.483.648 a 2.147.483.647
- **Double:** 8 bytes de memória e armazena números com menos de 15 casas decimais
- **Float:** 4 bytes de memória e armazena números com menos de 06 casas decimais

# Palavras reservadas ao C++
Palavras reservadas são um conjunto de 92 palavras que são excluivas para uso do C++, entre elas podemos citar

| - | - | - | - |
| :---: | :---: | :---: | :---: |
|`and` |`or` |`if` | `for` |
|`else` |`do` |`true`|`false`|
|`this` | `int` | `long` | `case` |
| `double` | `char` | `catch` | `break` |
| `const` | `private` | `return` | `void` |

Entre outras.

# Operadores em C++
Operadores em programação é um cálculo matemático envolvendo zero ou mais valores que originam um novo valor.
A operação em específico é determinado por um símbolo (ou par de símbolos) chamado **operador**.

- Adição: ` + `
- Subtração: ` - `
- Multiplicação: ` * `
- Divisão: ` / `
- Atribuição:  ` = `
- Inserção: ` << `
- Extração: ` >> `
- Igualdade: ` == `
- Módulo: ` % `


# Funções


---
# Referências
- [Betrybe - C++](https://blog.betrybe.com/linguagem-de-programacao/cpp/)
- [Wikipedia - C++](https://en.wikipedia.org/wiki/C%2B%2B)
- [Learn C++](https://www.learncpp.com/)
