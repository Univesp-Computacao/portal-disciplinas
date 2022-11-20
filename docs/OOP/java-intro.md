# Java e Orientação a Objetos

## Introdução Java
A primeira versão da linguagem Java surgiu em 1995, criada por alguns desenvolvedores da Sun Microsystem. A ideia inicial era desenvolver uma linguagem para controlar pequenos dispositivos, como televisores, videocassetes e aparelhos de TV a cabo. Mas JAVA acabou dominando a área de sistemas de informação, principalmente sistemas para a Web.

O código Java é convertido em bytecodes interpretados no ambiente de execução do Java para executá-los. Se for necessário mais desempenho, esse ambiente de execução transforma os bytecodes em código de máquina nativo para a CPU específica, ganhando assim desempenho.


A linguagem Java é Compilada e Interpretada. Primeiramente, os arquivos de código-fonte Java com extensão “.java” são compilados para bytecodes, também conhecidos como arquivos de extensão “.class”. Existe uma máquina virtual, conhecida como JVM (Java Virtual Machine), que é capaz de interpretar (executar) os arquivos Java compilados.


## Variáveis e Tipos de Dados

:pushpin: Variáveis são espaços na memória onde se guardam dados.

Java é uma linguagem fortemente tipada, pois cada variável precisa ter um tipo declarado. Existem oito tipos primitivos para armazenamento de informações. Tipos primitivos não são objetos, eles são partes internas da linguage

Para declarar uma variável:

- Digite seu tipo: `int` , `float` , `String` , etc.
- Dê um nome: `nome` ,  `idade` , `i` , etc.
- Use o sinal de atribuição `=` para atribuir um valor a variável. (opcional)
- Dê um valor a variável: `"Paula"` , `19` , `1.88` , etc. (opcional)

Java possui 8 tipos de dados primitivos:

### Números inteiros
| Tipo  | Armazenamento | Intervalo                      |
|-------|---------------|--------------------------------|
| int   | 4 bytes       | –2.147.483.648 a 2.147.483.647 |
| short | 2 bytes       | –32.768 a 32.767               |
| long  | 8 bytes       | –9.223.372.036.854.775.808 a 9.223.372.036.854.775.807|
| byte  | 1 byte        | -128 a 127                     |


### Números decimais

| Tipo   | Armazenamento | Intervalo                      |
|--------|---------------|--------------------------------|
| float  | 4 bytes       | aprox +/- 3.40282347E+38F (6-7 dígitos decimais significativos)|
| double | 8 bytes       | aprox +/- 1.797693134862311570E+308 (15 dígitos decimais significativos)|

O tipo **char** é utilizado para armazenar caracteres individuais, como letras, algarismos, sinais de pontuação, entre outros.

O último tipo é o **boolean**, que possui somente dois valores, verdadeiro ( true) ou falso ( false). No Java não é possível converter números inteiros em valores booleanos.

### Tipos de Dados Não Primitivos
Além disso, temos tipos **não primitivos** de dados, caso de **String** que corresponde a uma cadeia de caracteres Unicode, e **Object**, que se refere a qualquer objeto genérico.

## Operadores Aritméticos

Em Java temos os seguintes operadores:

- Soma: `+`
- Subtração: `-`
- Multiplicação: `*`
- Divisão: `/`
- Módulo: `%`

```java
public class Main {

	public static void main(String[] args) {
		int a;
		int b = 2;
		a = 3;
		
		int soma = a + b;
		int subtracao = a - b;
		int multiplicacao = a * b;
		int divisao = a / b;  // o resultado será int pois a variável foi declarada como int
		int modulo = a % b;
		
		System.out.println(soma);
		System.out.println(subtracao);
		System.out.println(multiplicacao);
		System.out.println(divisao);
		System.out.println(modulo);

	}

}
```

## Cast

É quando convertemos um valor de um tipo para outro.

Por exemplo, se queremos dividir os valores armazenados em 2 variáveis do tipo inteiro, o resultado será entendido como se também fosse do tipo inteiro. Por isso usamos o cast, para converter essa variável para float (ou double) na hora da operação.

```java

public class Main {

	public static void main(String[] args) {
		int a;
		int b = 2;
		a = 3;
		
		int divisaoint = a / b;  // resultado int
		float aindaint = a / b; // apesar de ser um float, as variáveis a e b ainda são int
		float divisaocast = (float) a / (float) b;
		// Ao fazer o cast, a e b são convertidos para float apenas na hora da operação
		

		System.out.println(divisaoint);
		System.out.println(aindaint);
		System.out.println(divisaocast);

	}

}

/*
Veja que apenas declarar a variável como float não é suficiente para fazer
a operação dar certo. É necessário fazer o cast (conversão).
*/

```
## Estruturas Condicionais

Usam condições para decidir que caminho seguir.

Para isso usamos operadores de comparação para comparar 2 expressões. Os operadores são:

- Igual: `==`
- Diferente: `!=`
- Maior: `>`
- Menor: `<`
- Maior ou igual: `>=`
- Menor ou igual: `<=`

### if / else if / else

```java
public class Main {

	public static void main(String[] args) {
		int nota = 70;
		
		if (nota >= 80) {
			System.out.println("A");
		} else if (nota >= 60) {
			System.out.println("B");
		} else if (nota >= 40) {
			System.out.println("C");
		} else {
			System.out.println("D");
		}
		

	}

}

```

### Operador Ternário
O operador ternário (`?`) é um recurso para tomada de decisões com objetivo similar ao do `if / else` mas codificado em apenas uma linha.

- No código, a expressão booleana `isWeekend` é avaliada.
- Caso ela seja verdade, tudo que estiver entre o operador ternário `?` e a pontuação `:` , será executado.
- Caso contrário, será executado tudo que estiver após a pontuação `:`

```java
public class Main {

	public static void main(String[] args) {
		boolean isWeekend = false;
		
		String message = isWeekend ? "It is weekend" : "It is not weekend";
		
		System.out.println(message);
		

	}

}

```
### Switch

```java 
public class Main {

	public static void main(String[] args) {
		String nota = "E";
		
		switch (nota) {
			case "A":
			case "B":
				System.out.println("Aluno aprovado");
				break;
			case "C":
				System.out.println("Aluno em recuperação");
				break;
			case "D":
				System.out.println("Aluno reprovado");
				break;
			default:
				System.out.println("Nota inválida");
		}

	}

}
```


## Estruturas de Repetição 

### While
- Usamos o `while` quando não sabemos exatamente quantas vezes o código será repetido
- A condição para interrupção da repetição se dá através de uma condição booleana.

```java
public class Main {
	
    public static void main(String[] args) {
        int i = 0;
        while (i < 5) {
          System.out.println(i);
          i++;
        }
    }
}


```

### Do-While
É uma variante do `while` , com a diferença que o bloco de código será executado primeiro, e somente depois é que será analisada a condição. Se a condição for verdadeira será executada mais uma vez, quando for falsa, irá interromper.
```java
public class Main {
	
    public static void main(String[] args) {
        int i = 0;
        do {
          System.out.println(i);
          i++;
        }
        while (i < 5);
    }
}


```


### For

- Como parâmetro coloca-se:
    - uma variável de controle
    - uma comparação
    - um incremento ou decremento

```java 
public class Main {
	
    public static void main(String[] args) {
        for (int i = 0; i <= 10; i++) {
            System.out.println(“A variável i agora vale “ + i);
        }
    }
	
}
```


## Classes do Java
### LocalDate

- LocalDate é uma classe Java para datas.
- Usa o formato ISO-8601
- É necessário importar `import java.time.LocalDate;`

```java 
// importa a classe LocalDate para trabalhar com data e hora
import java.time.LocalDate;
public class Main {

	public static void main(String[] args) {
		
		// Recupera as informações de data (ano, mês, dia) local e guarda em uma variável do tipo LocalDate
		LocalDate hoje = LocalDate.now();
		System.out.println(hoje);
		
		System.out.println(hoje.getDayOfWeek());  // Dia da semana
		System.out.println(hoje.getDayOfMonth());  // Dia do mês
		
	}

}
```
### Locale
- Classe usada para a localidade (USA, Austrálias, etc.)
- É necessário importar `import java.util.Locale;`

Para mostrar as informações de data traduzidas é necessário usar a classe Locale
Aqui é criada uma localidade usando a classe e essa localidade recebe o nome de portugal
É passado como parâmetro a língua ("pt") e o país ("PT")

Para imprimir usando as informações de acordo com o país, usamos `getDisplayName`
Usamos também `TextStyle` para o modo de exibição (deve ser importado)
Por fim, usamos a localidade criada acima.

```java 
// importa a classe LocalDate para trabalhar com data e hora
import java.time.LocalDate;

// importa a classe TextStyle para o formato
import java.time.format.TextStyle;

// importa a classe Locale
import java.util.Locale;

public class Main {

	public static void main(String[] args) {
		
		LocalDate hoje = LocalDate.now();
		
		/* Para mostrar as informações de data traduzidas é necessário usar a classe Locale
		Aqui é criada uma localidade usando a classe e essa localidade recebe o nome de portugal
		É passado como parâmetro a língua ("pt") e o país ("PT")
		*/
		Locale portugal = new Locale("pt", "PT");
		
		/* Para imprimir usando as informações de acordo com o país, usamos getDisplayName
		Usamos também TextStyle para o modo de exibição (deve ser importado)
		Por fim, usamos a localidade criada acima
		*/
		System.out.println(hoje.getDayOfWeek().getDisplayName(TextStyle.FULL, portugal));
		
	}

}
```

## IDEs para Java:

- Eclipse (IDE líder para Java)
- IntelliJ
- Netbeans
- JDeveloper
