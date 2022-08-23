# Listas Ligadas 

Uma lista ligada é uma lista linear que a ordem lógica dos elementos **não** é a mesma da ordem física.

Os elementos estão espalhados na memória.

Cada elemento precisa indicar em que endereço o seu sucessor pode ser encontrado de modo a manter a ordem lógica.

Desvantagens:
- Retira o acesso em tempo constante a qualquer elemento, dado o índice do elemento.
- Precisa percorrer todos os elementos predecessores, um por um.
- A busca binária deixa de fazer sentido.

Vantagens:
- Número de elementos pode aumentar ou diminuir durante a execução do programa.
- A manutenção da ordem lógica não exigirá deslocamentos de elementos.


