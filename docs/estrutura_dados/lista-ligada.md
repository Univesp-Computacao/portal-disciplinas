# Listas Encadeadas / _Linked Lists_

## Definição
Uma lista ligada é uma lista linear que a ordem lógica dos elementos **não** é a mesma da ordem física.

Os elementos estão em sequência, ou seja, tem exatamente um **sucessor** e um **predecessor**, porém, 
estes elementos estão espalhados na memória.

Cada elemento precisa indicar em que endereço o seu sucessor pode ser encontrado de modo a manter a ordem lógica.

Isso é feito através de um ponteiro.

### Vantagens:
- Maior controle na inserção e remoção de elementos.
- Número de elementos pode aumentar ou diminuir durante a execução do programa.
- A manutenção da ordem lógica não exigirá deslocamentos de elementos.

### Desvantagens:
- Retira o acesso em **tempo constante** a qualquer elemento, dado o índice do elemento.
- Precisa percorrer todos os elementos predecessores, um por um.
- A busca binária deixa de fazer sentido.



## Implementação de Pilha

Segue abaixo a estrutura do código implementado na videoaula 08.
Esta estrutura de dados está programada para guardar apenas dados do tipo ```char```, mas é possível mudar isso sem precisar alterar muito o código.

| <br>
|__stack.h <br>
|__node_type.h <br>
|__stack_alinhamento.cpp <br>
|__stack_encadeado.cpp <br>


=== "node_type.h"
```cpp
typedef char ItemType;
/*
 Estrutura usada para guardar 
 a informação e o endereço do 
 próximo elemento.
*/
struct NodeType
{
  ItemType info;
  NodeType* next;
};


```

=== "stack.h"

```cpp
#include "node_type.h"
class Stack {
public:
Stack();  // Construtor       
~Stack(); // Destrutor
bool isEmpty() const;
bool isFull() const;
void print() const;

void push(ItemType);
ItemType pop();  


private:
NodeType* structure;
};
        
    ```
   
=== "stack_alinhamento.cpp"

```cpp

#include "stack.h"
#include <iostream>

using namespace std;

int main() {
ItemType character;
Stack stack;  
ItemType stackItem;

cout << "Insira uma string." << endl;
cin.get(character);

bool isMatched = true;  
while (isMatched && character != '\n')
{
  if (character == '{' || character== '(' || character==  '['){  
 stack.push(character);
  }
  if(character == '}' || character== ')' || character==  ']'){    
 if (stack.isEmpty()) {
   isMatched = false;
 } else {
   stackItem = stack.pop();
   isMatched = (
             (character == '}' && stackItem== '{')
             || (character== ')' && stackItem == '(')
             || (character== ']' && stackItem == '[')
             );
 }
  }
  cin.get(character);
}


if (isMatched && stack.isEmpty() ) {
cout << "Bem formada \n";
} else {
cout << "Mal formada \n";
}
}    

```

=== "stack_encadeado.cpp"

```cpp
#include "stack.h"
#include <iostream>

using namespace std;

int main() {
ItemType character;
Stack stack;  
ItemType stackItem;

cout << "Insira uma string." << endl;
cin.get(character);

bool isMatched = true;  
while (isMatched && character != '\n')
{
if (character == '{' || character== '(' || character==  '['){  
stack.push(character);
}
if(character == '}' || character== ')' || character==  ']'){    
if (stack.isEmpty()) {
 isMatched = false;
} else {
 stackItem = stack.pop();
 isMatched = (
           (character == '}' && stackItem== '{')
           || (character== ')' && stackItem == '(')
           || (character== ']' && stackItem == '[')
           );
}
}
cin.get(character);
}


if (isMatched && stack.isEmpty() ) {
cout << "Bem formada \n";
} else {
cout << "Mal formada \n";
}
}


```
    
## Alguns detalhes da implmentação

- ```typedef``` é usado para definir previamente o tipo de uma variável.
- ```private``` and ```public``` são níveis de configuração/permissão dentro de uma classe.
- ```struct``` parecido com clase, porém, toda a interface é pública.
- ```try``` e ```catch``` [...]




---
# Referências deste trabalho

- [Prof. Douglas Maioli - Aula 05 Estrutura de Dados - Lista Encadeada]([url](https://www.youtube.com/watch?v=84wIYtNUKEg))
- [Prof. Douglas Maioli - Aula 06 - Estrutura de Dados - Lista Encadeada]([url](https://www.youtube.com/watch?v=zu0Xw5gPft0&t=892s))
- [Autor UNIVESP -  Estruturas de Dados - Pilha (lista Encadeada)]([url](https://www.youtube.com/watch?v=Xlkh6-10ILw)

