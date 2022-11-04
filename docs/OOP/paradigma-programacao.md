# Paradigmas de Programação

Programar é providenciar soluções usando modelos computacionais suportados por uma linguagem de programação. Antes mesmo de solucionar o problema já temos que ter uma visão do problema e da solução.

Conforme o dicionário Oxford o termo paradigma se traduz por "um exemplo que serve como modelo; padrão.", logo paradigmas de programação são um conjunto de conceitos e ideias que constituem um modelo de visão da realidade.

Um único problema pode ter mais de um meio de solução, isso se dá, pois, podemos combinar dados e algoritmos de maneira que obtenhamos o mesmo resultado por caminhos complemente diferentes. As linguagens de programação podem ter o viés de algum paradigma específico ou mesmo ser multiparadigma.

## Paradigma Imperativo
>>> Semelhante ao comportamento imperativo das linguagens naturais que expressam ordens, programas imperativos são uma sequência de comandos para o computador executar.

Características centrais das linguagens imperativas: 
* as variáveis, que modelam as células de memória;
* comandos de atribuição, baseados nas operações de transferência dos dados e instruções; 
* a execução sequencial de instruções;
* e a forma iterativa de repetição, o método mais eficiente desta arquitetura

FORTRAN, COBOL, e C são alguns examplos de linguagem de programação que suportam o paradigma imperativo.


## Paradigma Procedural

Muito parecido com o paradigma imperativo com uma diferença: múltiplos comandos numa unidade são chamados _procedimento_, equiparável a métodos, funções, rotinas. A principal consequência disso é a reutilização do código em diferentes partes do programa, fazendo a invocação do procedimento. Java, C++, PHP entre outras, são linguagens que suportam o paradigma procedural.

## Paradigma Declarativo

Um contraste com o paradigma Imperativo, pois descrevemos o problema e o computador acha a solução. É mais importante pensar no que é o problema do que em como resolvê-lo.

Dá para pensar, por exemplo, num programa escrevendo num banco de dados SQL (Structured Query Language), onde você especifica o dado a ser salvo e o "motor" do banco de dados se encarrega de salvar aquele dado para você. O Foco não está no "como" e sim no "que".

Neste paradigma, ao contrário do imperativo, o algoritmo produz novos dados ao invés de apenas manipulá-lo.

Podemos citar o PROLOG como liguagem que utiliza esse paradigma.

## Paradigma Funcional

Baseado no conceito de funções matemáticas. Enfatiza o processamento de valores através do uso de expressões e funções. Tais funções podem ser passadas como parâmetros de outras funções.
Um exemplo de Linguagem que usa esse procedimento é o LISP e seu dialeto Scheme, usada em softwares como AutoCAAD, Audacity, GIMP e Emacs.

Outra linguagem funcinoal famosa é o R, usado para estatística. 

Uma característica importante é a recursividade, onde uma função invoca a si mesma, permitindo a criação de um laço.

## Paradigma Orientado à Objetos

Um objeto é uma entidade abstrata que contém dados e algoritmos, dados são o **estado** de um objeto, já os algoritmos são o **comportamento** desse objeto. 

As **classes** são unidades básicas da Orientação a Objetos. Objetos similares são agrupados em uma mesma classe, é possível criar objetos a partir da classe, como também chamamos a criação de um objeto de instanciação.

Diferentes objetos de uma mesma classe podem conter valores de estado diferentes, ou seja, o estado de um objeto é mantido privado de um outro objeto. E é através dos métodos que acessamos/alteramos esses valores (estados).

Um método especial é o **método construtor** de uma classe: ele fornece valores iniciais ao objeto, ou permite que tais valores sejam determinados na criação. Uma classe pode ter mais de um construtor. 

O paradigma de Orientação a Objetos é prático, natural e intuitivo, quando pensamos na relação com os problemas reais. Mesmo assim, pode ser complexo seu aprendizado, levando algum tempo para compreender os seus principais conceitos: abstração, encapsulamento, polimorfismo e herança. 
## Referências
[PUCRS - Paradigma Imperativo](https://www.inf.pucrs.br/~gustavo/disciplinas/pli/material/paradigmas-aula09.pdf)
[Wikipedia - Programação Imperativa](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_imperativa)
[guia.dev -  Pradigmas de Programação](https://guia.dev/pt/pillars/languages-and-tools/programming-paradigms.html#:~:text=de%20baixa%20legibilidade.-,Procedural,m%C3%A9todos,%20fun%C3%A7%C3%B5es,%20rotinas).)
[Profa. Isabel Harb Manssour - Paradigmas de Linguagem I](https://www.inf.pucrs.br/~gustavo/disciplinas/pli/material/paradigmas-aula01.pdf)

