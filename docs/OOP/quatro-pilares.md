# Paradigma Orientado à Objetos e Java

Apesar de ser comum ouvir falar em Java como uma linguagem orientada a objetos, isso não é verdade, pois o Java também pode ser usado como uma linguagem procedural. A Orientação a Objetos é pertinente ao paradigma, enquanto a linguagem é responsável por fornecer meios de implementar aquele paradigma. Iremos ver em resumo os quatro pilares da POO.

## Abstração

Programas de computador podem variar de algumas linhas à centenas de milhares de linhas. Para facilitar a manutenção de um programa monolito é comum decompor o programa em subprogramas menores. A abstração é o processo de expor detalhes essenciais de uma entidade, enquanto os detalhes irrelevantes são ignorados, facilitando a manutenção e o entendimento.
A relevância de um detalhe está ligada a seu contexto, por exemplo, pensemos num teclado, o contexto para o usuário é o mais simples possível, ele apenas deve ter acesso às teclas e pronto, já para o contexto da máquina o mais importante é o circuito elétrico interno do teclado, aquilo que fica por trás das teclas, oculto ao usuário.

## Encapsulamento

Linguagens de programação dão suporte a encapsulamento de diversas maneiras: um procedimento é um encapsulamento de um conjunto de passos para executar uma tarefa; um vetor (*array*) é o encapsulamento de diversos elementos; etc. Na Programação Orientada à Objetos, o encapsulamento é o processo de agrupar dados e procedimentos em uma entidade chamada de classe.

No Java você pode encapsular dados e procedimentos dentro de uma **classe**, é possível encapsular classes dentro de **pacotes** (*packages*) e pacotes dentro de um **módulo**.

## Herança

O mecanismo de herança permite que você defina uma nova abstração através de uma abstração já existente. A nova abstração pode ser chamada de subtipo, subclasse ou classe derivada, enquanto a classe originária é chamada de supertipo, superclasse,  como também, costuma-se referenciar esta por classe-pai e aquela por
classe-filha.
Ao nível da programação, a herança provê um mecanismo de reutilização de código. A partir da derivação de uma classe genérica é possível criar classes específicas.

## Polimorfismo

Permite que uma entidade assuma diferentes significados em diferentes contextos, com o propósito de se escrever códigos que sejam reutilizáveis e de fácil manutenção. A capacidade polimórfica decorre diretamente da herança, pois permite que uma variável de **referência** e o **objeto** sejam diferentes, isso ocorre através da sobrescrita de métodos, quando a subclasse sobrescreve o método implementado na superclasse.

O polimorfismo ainda pode ser dividido em dois tipos:

- Ad hoc: define uma interface comum para um conjunto arbitrário de tipos especificados individualmente.
- Universal : não especifica tipos concretos e, em vez disso, usa símbolos abstratos que podem substituir qualquer tipo.

## Referências

- [https://en.wikipedia.org/wiki/Polymorphism_(computer_science)](https://en.wikipedia.org/wiki/Polymorphism_%28computer_science%29 "https://en.wikipedia.org/wiki/Polymorphism_(computer_science)")

- FIAP - Nano Cursos - Java Fundamentos - https://on.fiap.com.br/

- SHARAN, Kishori; DAVIS, Adam L. . **Beginning Java 17 Fundamentals**: Object-Oriented Programming in Java 17. Third edition. Apress.