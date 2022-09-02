# Listas Encadeadas / _Linked Lists_

## Definição
Uma lista ligada é uma lista linear que a ordem lógica dos elementos **não** é a mesma da ordem física.

Os elementos estão em sequência, ou seja, tem exatamente um **sucessor** e um **predecessor**, porém, 
estes elementos estão espalhados na memória.

Cada elemento precisa indicar em que endereço o seu sucessor pode ser encontrado de modo a manter a ordem lógica.

Isso é feito através de um ponteiro.

## Vantagens:
- Maior controle na inserção e remoção de elementos.
- Número de elementos pode aumentar ou diminuir durante a execução do programa.
- A manutenção da ordem lógica não exigirá deslocamentos de elementos.

## Desvantagens:
- Retira o acesso em **tempo constante** a qualquer elemento, dado o índice do elemento.
- Precisa percorrer todos os elementos predecessores, um por um.
- A busca binária deixa de fazer sentido.

# Implementação de Pilha com lista Encadeada(_Linked List_).

## Estrutura do projeto

|
|__pilha.h <br>
|__pilha.cpp <br>
|__main.cpp <br>

=== "pilha.h"

     ```cpp
        codigo
    ```
   
=== "pilha.cpp"

   

    ```cpp
        #include ""
    ```

=== "main.cpp"

     ```cpp
        #include ""
    ```
    
## Alguns detalhes da implmentação

- ```typedef``` é usado para definir previamente o tipo de uma variável.
- ```private``` and ```public``` são níveis de configuração/permissão dentro de uma classe.

## Entendendo a função **main()** da Pilha





Problema: Como buscar um elemento usando busca binária? 
??? note "Espiar a resposta" A busca binária é um algoritmo de busca de um elemento em vetores que segue o
paradigma de **divisão e conquista**. 


---
# Referências deste trabalho
- [Prof. Douglas Maioli - Aula 05 Estrutura de Dados - Lista Encadeada]([url](https://www.youtube.com/watch?v=84wIYtNUKEg&list=PLrOyM49ctTx_AMgNGQaic10qQJpTpXfn_&index=6))
- [Prof. Douglas Maioli - Aula 06 - Estrutura de Dados - Lista Encadeada]


