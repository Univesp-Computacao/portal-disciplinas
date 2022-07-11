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

## Tipos de Dados em C++

- **Bool:** valores True or False, em geral armazenam 1 byte
- **Char:** aramazena um único caracter também de um byte, como "a", ou "b" e assim por diante
- **Int:** utiliza 4 bytes e armazenam números inteiros entre -2.147.483.648 a 2.147.483.647
- **Double:** 8 bytes de memória e armazena números com menos de 15 casas decimais
- **Float:** 4 bytes de memória e armazena números com menos de 06 casas decimais

## Palavras reservadas ao C++
Palavras reservadas são um conjunto de 92 palavras que são excluivas para uso do C++, entre elas podemos citar

| - | - | - | - |
| :---: | :---: | :---: | :---: |
|`and` |`or` |`if` | `for` |
|`else` |`do` |`true`|`false`|
|`this` | `int` | `long` | `case` |
| `double` | `char` | `catch` | `break` |
| `const` | `private` | `return` | `void` |

Entre outras.

## Operadores em C++
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


## Funções
Uma função é uma coleção de _statements_ (instruções) que são executadas sequencialmente. Todo programa em C++ deve incluir uma função chamada `main()`. Quando você roda o programa a execução começa no topo da main.

A chamada de uma função é uma expressão que diz ao CPU par interromper a função corrente e executar outra função. Depois de executada, o CPU retoma as instruções do ponto em que parou.

Aqui está um simples código que mostra como uma função é definida e invocada:

```C++
#include <iostream> // para o std::cout

// Definição de uma função imprimir()
void imprimir() // imprimir() é o nome da função
{
    std::cout << "Dentro da função imprimir()\n";
}

// Definição da função main()
int main()
{
    std::cout << "Começando a main()\n";
    doPrint(); // Interrompendo a main() por chamar a função imprimir().  
    std::cout << "Encerrando a main()\n"; // esta instrução é feita depois da conclusão da função imprimir()

    return 0;
}
```
O output será:

```markdown
Começando a main()
Dentro da função imprimir()
Encerrando a main()
```

---
# Referências
- [Betrybe - C++](https://blog.betrybe.com/linguagem-de-programacao/cpp/)
- [Wikipedia - C++](https://en.wikipedia.org/wiki/C%2B%2B)
- [Learn C++](https://www.learncpp.com/)
