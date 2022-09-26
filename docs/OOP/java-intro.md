# Java e Orientação a Objetos

## Introdução Java
A primeira versão da linguagem Java surgiu em 1995, criada por alguns desenvolvedores da Sun Microsystem. A ideia inicial era desenvolver uma linguagem para controlar pequenos dispositivos, como televisores, videocassetes e aparelhos de TV a cabo. Mas JAVA acabou dominando a área de sistemas de informação, principalmente sistemas para a Web.


O código Java é convertido em bytecodes interpretados no ambiente de execução do Java para executá-los. Se for necessário mais desempenho, esse ambiente de execução transforma os bytecodes em código de máquina nativo para a CPU específica, ganhando assim desempenho.



A linguagem Java é Compilada e Interpretada. Primeiramente, os arquivos de código-fonte Java com extensão “.java” são compilados para bytecodes, também conhecidos como arquivos de extensão “.class”. Existe uma máquina virtual, conhecida como JVM (Java Virtual Machine), que é capaz de interpretar (executar) os arquivos Java compilados.

## Programação Orientada a Objetos 

Trazer para a programação os conceitos de objetos da vida real e a criação de moldes para esses objetos, favoreceu toda uma nova linha de sistemas otimizados, reaproveitáveis e de fácil atualização.

Um objeto  é gerado a partir de um molde ou classe, seguindo os princípios do mundo real. Um objeto representa uma entidade que pode ser física, conceitual ou de software.

Um objeto é uma entidade com fronteira e identidade bem definidas que encapsulam o **Estado** e **Comportamento**. O **Estado** se refere a  atributos e relacionamentos, enquanto o **comportamento** se refere a operações e métodos.

### Quatro princípios da OOP
- **Abstração**: extrair informações do mundo real para o mundo virtual.
- **Encapsulamento**: criação de interface para o usuário final protegendo os mecanismos internos de funcionamento do objeto.
- **Modularização**: reutillização e organização dos objetos.
- **Hierarquia**: herança de variáveis e métodos de uma classe para outra.


## Variáveis e Tipos de Dados
Java é uma linguagem fortemente tipada, pois cada variável precisa ter um tipo declarado. Existem oito tipos primitivos para armazenamento de informações. Tipos primitivos não são objetos, eles são partes internas da linguage

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

Além disso, temos tipos não primitivos de dados, caso de **String** que corresponde a uma cadeia de caracteres Unicode, e **Object**, que se refere a qualquer objeto genérico.


## IDEs para Java:

- Eclipse (IDE líder para Java)
- IntelliJ
- Netbeans
- JDeveloper
