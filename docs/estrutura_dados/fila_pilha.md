# Fila e Pilha  

Tanto fila como pilha são estrutura de dados **lineares**, ou seja, possuem ligação com um único antecedente e com um único sucessor, desse modo:

![image](https://user-images.githubusercontent.com/72423464/184858945-0722a600-5a37-472c-990b-aadb75c7cc33.png)



## Pilha (vetorial)

Uma pilha (ou _stack_ em inglês) é uma estrutura linear na qual **inserções e remoções ocorrem no topo da pilha**.

Numa pilha, a manipulação dos elementos é realizada em apenas uma das extremidades, chamada de topo, em oposição a outra extremidade, chamada de base.

**Características:**

- O último elemento a entrar tem que ser o primeiro a sair (_Last-In-First-Out_).
- Permitem acesso a apenas o último item inserido.
- Inserções e remoções ocorrem no topo.

![pilha](https://user-images.githubusercontent.com/72423464/184860157-8d7d21d5-ed30-4cb3-8676-f41106b7b178.gif)

**Principais funções:**

- `isEmpty()` : chamada para verificar se a pilha está vazia.
- `isFull()` : chamada para verificar se a estrutura está completa (quando possui tamanho fixo).
- `push()` :  inserção de elementos no topo da pilha; empilhar.
- `pop()` : remoção do elemento que está no opo da pilha; desempilhar.

**Principais usos** 

- O comando de desfazer a última operação (ctrl+z / cmd+z)
- Navegação entre páginas.
- Função recursiva;

## Fila (vetorial)
Uma fila (ou _queue_) é uma estrutura linear na qual as **inserções ocorrem no final** e as **exclusões ocorrem no início**.

Todas as operações em uma fila podem ser imaginadas como as que ocorre numa fila de pessoas num banco, exceto que o elementos não se movem na fila, conforme o primeiro elemento é retirado. Isto seria muito custoso para o computador. O que se faz na realidade é indicar quem é o primeiro.

**Caracterísiticas**

- O primeiro elemento a entrar na estrutura tem que ser o primeiro a sair (_First-In-First-Out_).
- Inserções ocorrem no final e remoções ocorrem no início.

![fila](https://user-images.githubusercontent.com/72423464/185724135-22906bb9-0ca6-4a2f-aa77-41db37719278.gif)


**Principais funções**

- `queue()` - enfileirar
- `dequeue()` - desinfileirar 
- Além das funções `isEmpty()` e `isFull()` , semelhantes à pilha.

**Principais usos**

- Documentos enviados para impressões.
- Troca de mensagens entre processos em Sistemas Operacionais.
- Troca de mensagens entre computadores em uma rede.


***
## Referências

- https://www.cos.ufrj.br/~rfarias/cos121/pilhas.html
- https://www.cos.ufrj.br/~rfarias/cos121/filas.html
- https://cathyatseneca.github.io/DSAnim/web/llstack.html
