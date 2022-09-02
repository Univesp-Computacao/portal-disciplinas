# Listas Ligadas 

## Definição
Uma lista ligada é uma lista linear que a ordem lógica dos elementos **não** é a mesma da ordem física.

Os elementos estão em sequência, ou seja, tem exatamente um **sucessor** e um **predecessor**, porém, 
estes elementos estão espalhados na memória.

Cada elemento precisa indicar em que endereço o seu sucessor pode ser encontrado de modo a manter a ordem lógica.

Isso é feito através de um ponteiro.

## Vantagens:
- Número de elementos pode aumentar ou diminuir durante a execução do programa.
- A manutenção da ordem lógica não exigirá deslocamentos de elementos.

## Desvantagens:
- Retira o acesso em tempo constante a qualquer elemento, dado o índice do elemento.
- Precisa percorrer todos os elementos predecessores, um por um.
- A busca binária deixa de fazer sentido.

# Implementação de Fila com lista ligada.

## Estrutura do projeto

=== "fila.h"

    - Arquivo que contém as classes do algoritmo.
   
=== "fila.cpp"

    - Arquivo que detalha as funções usadas na classe.

    ```cpp
        #include ""
    ```

=== "main_fila.cpp

    - Contém a função principal, responsável por iniciar o programa.
    

*** 
## Referências
https://www.youtube.com/watch?v=84wIYtNUKEg&list=PLrOyM49ctTx_AMgNGQaic10qQJpTpXfn_&index=6

