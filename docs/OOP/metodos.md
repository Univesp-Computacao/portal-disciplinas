# Métodos

Um método em uma classe define o comportamento dos objetos ou mesmo o comportamento da classe em si. O método pode ser invocado para que executemos seu código. Opcionalmente um método pode aceitar valores de entrada (*input values*) na hora de sua invocação, que são conhecidos como parâmetros.

## Declarando Métodos de uma Classe

```
[modificador] <tipo-retorno> <nome-metodo> (<lista-parametro>) {
    // Corpo do método vai aqui
}

```

* modificador é uma lista opcional de modificadores para o método
* tipo-retorno é o tipo de dado do valor a ser retornado pelo método
* lista-parametro é uma lista opcional de parâmetros que o método aceita. Quando tem mais de um eles são separados por vírgula.
* corpo do método é o código que será executado ao ser invocado tal método.

Convencionalmente um método em Java começa com uma letra minúscula e a próxima palavra com maiúscula, por exemplo, *adicionarProduto*, *removerProduto*, *depositarDinheiro* .

Um método tem uma assinatura que identifica tal método em determinado contexto. A assinatura de um método é a combinação das seguintes partes:

* Nome do método
* Número de Parâmetros
* Tipo de dado dos parâmetros
* Ordem dos parâmetros 


## Variáveis Locais

Uma variável declarada dentro de um método, de um construtor ou de um bloco de código é chamada de variável local. Uma variável local existe somente durante a execução daquele método, ou seja, ela é temporária e não pode ser utilizada fora do escopo.  

Obs: se uma variável local de um método possui o mesmo nome que uma variável da classe em que o método está contido, a variável local possui precedência.

## O Método *main()*

O método main se declara da seguinte maneira: 

```
public static void main(String[] args) {
	// corpo do método vai aqui
}
```

Dois modificadores `public` e `static` são utilizados na declaração da main(). O `public` faz ele ser acessível de qualquer lugar da aplicação desde que a classe na qual ele seja declarada esteja acessível. O modificador `static` faz ele ser uma classe método, ou seja, ele pode ser invocado usando o nome da classe. 

O tipo de retorno é do tipo `void` que significa que ele não retorna nenhum valor ao seu invocador. 
O método main() aceita um único parâmetro do tipo String array (`String[]`) e a palavra 'args' define o nome do parâmetro. 

O método main() é responsável por inicar a execução do código na JVM (Java Virtual Machine).

## A Palavra-chave *this*

A palavra-chave *this* é uma referência a  instância de uma classe e só pode ser utilizada no contexto de uma instância. *This* em inglês significa "isso", "isto" e tem a finalidade de apontar para a própria classe, distinguindo variáveis de mesmo nome. 

Por exemplo: 
```java
 public Funcionario( String nome, int ID, double salario){
    this.nome = nome;
    this.ID = ID;
    this.salario = salario;
 }

```

Visualizamos que o `this.nome` é a variável nome da classe Funcionário e `nome` é o parâmetro que foi recebido para criar um objeto. 

Veremos outros usos da palavra-chave *this* no  artigo sobre Construtores.


## Nível de acesso para métodos

O nível de acesso para os métodos de uma classe determinam quais partes do programa podem ser acessados. São quatro os tipos de modificadores usados para métodos (como também para atributos):

* public
* private
* protected
* default (package-level access)

Quando declaramos um método como `public` ele pode ser acessado de qualquer lugar desde que a classe também esteja acessível.

Quando declaramos um método como `private` ele pode ser acessado apenas no corpo da classe declarada e em nenhum outro lugar.

Quando declaramos um método como `protected` ele pode ser acessado do mesmo pacote ou de descendentes da classe, mesmo se os descendentes estiverem em diferentes pacotes.

Se não declararmos **nenhum modificador** de acesso, automaticamente ele será declarado como `default` e o método poderá ser acessado pelo mesmo pacote.


## Referências
* https://www.javaprogressivo.net/2012/10/Auto-referencia-com-o-this-Invocando-metodos-de-Classes-e-Objetos.html
* SHARAN, Kishori; DAVIS, Adam L. . **Beginning Java 17 Fundamentals**: Object-Oriented Programming in Java 17. Third edition. Apress.