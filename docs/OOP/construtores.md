# Construtores

Um construtor (*constuctor* em inglês) é um bloco de código usado para inicializar um objeto de uma classe. A sua sintaxe é muito semelhante à de um método, porém, os dois tem propósitos bem diferentes.

O construtor é utilizado com o operador `new` para inicializar/criar uma instância/objeto de uma classe

## Declarando um Construtor

```
[modificador] <nome-construtor> (<lista-parametro){ 
		// corpo do construtor entre chaves
}
```

- começa com um modificador de acesso (_public_, _private_, _protected_, ou _default_);
- o nome do construtor  deve ter o mesmo nome da classe;
- os parâmetros são opcionais;
- constructores não aceitam nenhum tipo de retorno, o que retorna apenas é a instância da classe.

## Sobrecarregando um construtor (*Overload*)

Se uma classe posui **múltiplos construtores** ela é chamada de **sobrecarregada** (overloaded). Todos construtores irão possuir o mesmo nome que a classe o que muda é somente a existência de parâmetros, bem como sua quantidade, ordem, tipo de parâmetro.

```java

// Example.java

package exemplos;
public class Gato {
// Construtor #1
public Gato() {
System.out.println("Um gato foi criado.");
}
// Construtor #2
public Gato(String cor) {
System.out.println("Um gato  " + cor + " foi criado.");
}
}

``

Ao chamar a `main()` com o seguinte código:

```java
public static void main(String[]args){

            Gato gato_1 = new Gato();
            Gato gato_2 = new Gato("amarelo");

```

Teremos a seguinte saída:

```
Um gato foi criado.
Um gato amarelo foi criado.
```

# Estrutura de construtores

```java

//Declaração da classe
    
    public class Pessoa {
    
    //Atributos
    
    // Construtor(<lista-parametros>) #1
    
        // Invocação de métodos comuns métodos acessores/modificadores

    // Construtor(<outra-lista-parametros>) #2
        
        // Invocação de métodos ...
                
    // Construtor(<n-parametros>) #n ...
    
        // 
    
    // Método #1
    
    // Método #2
    
    // Método #n ...
    
    
    

```
## Referências
* https://www.javatpoint.com/java-constructor
* SHARAN, Kishori; DAVIS, Adam L. . **Beginning Java 17 Fundamentals**: Object-Oriented Programming in Java 17. Third edition. Apress.