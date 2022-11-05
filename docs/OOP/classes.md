
# Classes

## O que são classes?
Classes são a unidade básica da programação orienta à objetos. Se olharmos ao nosso redor encontraremos milhares de objetos e cada um pertence a uma classe. Podemos olhar a um livro e dizer que ele é da classe de livros em geral e, mais especificamente, dizer se ele é da classe de livro literário, didático, infantil, etc.

Podemos a olhar a nós mesmos e afirmar que fazemos parte da classe humana, mas cada um de nós tem propriedades e comportamentos únicos, como gostos, altura, nome, etc.  Seria como se disséssemos que cada ser humano é de uma instância da classe humana.

Então podemos dizer em primeiro que cada objeto é uma entidade separada, e em segundo, que cada ojeto compartilha propriedades e comportamentos comuns com a classe originária.

## Declarando Classes em Java

A sintaxe genérica para declarar uma classe em java é: 

```java
[modificador] class <nome-da-classe> {
    // Corpo da classe vai aqui
}
```

* Modificadores são opcionais; eles são palavras-chave para definir o acesso à classe. Uma classe pode ter zero ou mais modificadores.
* O nome-da-classe deve começar com maiúsculo e se for nome composto, o primeiro caractere de cada palavra deve ser sempre maiúsculo.
* O corpo da classe contém diferentes componentes como campos e métodos.

## Declarando campos em uma classe

Campos representam propriedades/atributos de um objeto. O tipo de dados precede o nome do campo. Opcionalmente um campo pode ser inicializado com um valor ou apenas ser declarado. É um boa prática declarar campos com a primeira letra minúscula e, quando for composto, a próxima palavra começar com maiúscula, por exemlo: `nome`, `genero`, `primeiroNome`, `corPreferida`.

```java
// Pessoa.java
class Pessoa{
    String nome;
    String genero;
    int idade
```
Todo objeto da classe Pessoa terá os atributos _nome_, _genero_ e _idade_.

## Criando uma instância de uma classe
Usamos o operador `new` para chamar o construtor da classe cuja instância está sendo criada e alocada no _heap_. O seguinte código cria uma instância da classe Pessoa:

```java
new Pessoa();
```

Como nesse caso não criamos nenhum construtor para a classe Pessoa, o compilador do Java irá adicionar um construtor _default_.

Mas na declaração acima, apesar de termos criado uma instância de Pessoa, não temos controle sobre ela pois não demos um nome a ela, ou mais propriamente, não atribuímos a essa instância nenhuma variável. 
A maneira mais correta para criarmos uma instância seria: 

```java
Pessoa jack = new Pessoa();
```

## Usando a notação ponto para acessar campos de uma classe

Usamos o seguinte padrão para referir a variáveis contidas em classes: 

```
<nome-referencia-instancia>.<nome-da-variavel>
```

Que no caso do nosso exemplo seria `jack.nome`. Para atribuirmos um valor ao nome faríamos o seguinte: 

```java

jack.nome = "Jack Sparrow";
```
 
## Referências

* https://www.devmedia.com.br/boas-praticas-de-programacao/21137
* SHARAN, Kishori; DAVIS, Adam L. . **Beginning Java 17 Fundamentals**: Object-Oriented Programming in Java 17. Third edition. Apress.