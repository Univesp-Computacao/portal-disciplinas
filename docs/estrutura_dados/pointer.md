# C++ Ponteiro

Com ponteiros a execução de tarefas de programação podem ser simplificadas, e algumas tarefas, 
como a **alocação dinâmica da memória**, só podem ser relizadas com ponteiros.

## Endereço de variáveis

Cada variável tem seu local na memória e cada local define um endereço que pode ser acessado utilizando o operador "E comercial" (&),
que representa um endereço na memória. O exemplo abaixo irá retornar o endereço de uma variável definida: 

```cpp
#include <iostream>
 
using namespace std;
 
int main()
{
   int var1;
   char var2[10];
 
   cout << "Endereço da variável var1: ";
   cout << &var1 << endl;
 
   cout << "Endereço da variável var2 : ";
   cout << &var2 << endl;
 
   return 0;
}

```

Após compilação e execução, temos o seguinte resultado:

```
Endereço da variável var1: 0x7fffc99d6578
Endereço da variável var2 : 0x7fffc99d657e
```

## Ponteiro

Depois de ter visto o que é um endereço na memória e como acessá-lo, o entendimento de um ponteiro será mais fácil.
Ponteiro é uma variável cujo valor é o endereço de outra variável, ou seja, o endereço direto de uma locação na memória.
Como qualquer variável ou constante, um ponteiro deve ser declarado antes de usá-lo para armazenar o endereço de outra variável.
De forma geral, um ponteiro se declara assim:

```cpp
int *number; /* um ponteiro para variáveis do tipo inteiro */ 
float *decimal_number; /* um ponteiro para um float*/
char *character; /* um ponteiro para variáveis do tipo char */
```
Todo ponteiro é um longo hexadecimal representando um endereço na memória.

## Usando Ponteiros 

Para usar o ponteiro, normalmente seguimos os seguintes passos: 
1. Definir um ponteiro;
2. Atribuir o endereço da variável ao ponteiro;
3. Acessar o valor do endereço disponível na variável ponteiro.


Isso irá retornar o valor da variável no endereço específico pelo operador * . Exemplo:

```cpp
#include <iostream>
 
using namespace std;
 
int main()
{
   int var = 20; // declaração de variável
   int *int_pointer; // declaração da variável ponteiro
 
   int_pointer = &var; // armazena o endereço da "var" no específico ponteiro
 
   cout << "Valor da variável var: ";
   cout << var << endl;
 
   // gera o endereço armazenado na variável ponteiro
   cout << "Endereço armazenado na variável int_pointer: ";
   cout << int_pointer << endl;
 
   // accessa o valor do endereço no ponteiro
   cout << "Valor da variável *int_pointer: ";
   cout << *int_pointer << endl;
 
   return 0;
}

```
Após compilar e executar temos o seguinte resultado:

![image](https://user-images.githubusercontent.com/72423464/183629513-e46a7669-1c16-4c0e-92ad-45a73ea4d979.png)


## Referências
https://cplusplus.com/doc/tutorial/pointers/

https://www.simplilearn.com/tutorials/cpp-tutorial/pointers-in-cpp

https://iditect.com/guide/cplusplus/cpp-pointers.html
