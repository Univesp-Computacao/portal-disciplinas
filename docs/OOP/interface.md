Muitos softwares são utilizados para fazer simulações de problemas reais, tais como: mudanças ambientais, previsões climáticas, flutuações da bolsa de valores, tráfego de uma cidade, etc.

Vamos supor uma simulação da área de biologia do tipo predador-presa. Para simplificar pensemos na relação de coelho-raposa dentro de uma localidade. Quanto maior o número de coelhos, mais presas, maiores são as chances de as raposas se alimentarem e se reproduzirem, portanto, maior número de raposas, o que levaria por consequência, a uma diminuição do número de coelhos. 

Poderíamos pensar na seguinte classe para coelho:

```java

public class Rabbit
{
    //campos estáticos omitidos.
        
    // Características individuais (campos de instância).
    
    // A idade do coelho.
    private int age;
	
    // Coelho vivo ou não.
    private boolean alive;
	
    // A posição do coelho
    private Location location;
	
    // O campo ocupado
    private Field field;
    
    //Métodos omitidos.
}

```

E a seguinte classe para raposas:

```java

public class Fox
{ 
    //Campos estáticos omitidos
 
    // A idade de uma raposa.
    private int age;
	
    // Raposa viva ou não.
    private boolean alive;
	
    // A posição da raposa
    private Location location;
	
    // O campo ocupado
    private Field field;
	
    // O nível de alimento da raposa que aumenta comendo coelhos.
    private int foodLevel;

    //Métodos omitidos.
}

```


Facilmente enxergamos que ambos animais tem atributos em comum como `age`, `alive` e `location`. Isso nos permitiria criar uma superclasse Animal que possuísse esses atributos.

Mas essa superclasse Animal não seria como as outras, pois, ela não será o molde para nenhum objeto, portanto, ela seria ou uma interface ou mesmo uma classe abstrata.


## O que é Interface?

A interface é como um template que outras classes podem seguir/implementar. Isso permite que classes de diferentes hierarquias tenham atributos iguais.
Uma interface define um conjunto de assinaturas de métodos que outras classes devem implementar, ela apenas define um comportamento base para um conjunto de classes.

### Implementando uma interface

No exemplo que demos acima, de uma superclasse Animal e de duas subclasses raposa e coelho, teríamos a seguinte sintaxe de implementação:

```java

public class Coelho implements Animal;
public class Raposa implements Animal;


```

## O que é Classe Abstrata?

Muito parecida com a interface, a classe abstrata não é o molde para nenhum objeto, mas sim, uma classe-pai, ou seja, ela contém métodos e atributos que serão **herdados** por outras classes. 
As classes abstratas também não podem instanciar objetos, cabendo a instanciação às classes concretas.

### Diferenças entre Interface e Classe Abstrata

|Classe Abstrata | Interface                                        |
|---|--------------------------------------------------|
|Pode possui atributos de instância	| Possui apenas constantes                         |
|Possui métodos de diversas visibilidade e métodos implementados ou abstratos | Todos os métodos são public e abstract|
|É estendida por classes (sub-classes)	| É implementada por classes|
|Uma subclasse só pode estender uma única classe abstrata	| Uma classe pode implementar mais de uma interface |
|Hierarquia de herança com outras classes abstratas	| Hierarquia de herança com outras interfaces      |


## Referências

- [Java - Classes Abstratas](http://www.universidadejava.com.br/java/java-classes-abstratas/)
- [Classes Abstratas vs Interfaces](https://www.treinaweb.com.br/blog/classes-abstratas-vs-interfaces)
- [USP -  Prof. Marcio Delamaro - Interfaces](https://edisciplinas.usp.br/pluginfile.php/3335003/mod_resource/content/1/Interface.pdf)
- [POLIMORFISMO E INTERFACES - Dilvan Moreira](https://edisciplinas.usp.br/mod/resource/view.php?id=2383619)