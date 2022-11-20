# Array e ArrayLists

## Definição

Objetos **array** são estrutura de dados do mesmo tipo relacionados, que facilitam a organização de grupos de valores relacionados. O número de posição do elemento é chamado de **índice**.


## Declarando e criando Arrays

Como outros objetos, arrays são criados com a palavra chave `new` e é necessário especificar o tipo de elementos que o array irá aramazenar e o número de elementos. Por exemplo:

```java
int[] c = new int[12]
```

O código acima cria um arrray de **inteiros** de tamanho **12** com o nome **c**.

### Utilizando um inicializador de array

Você pode criar um array e inicializar seus elementos com um **inicializador de array** — uma lista separada por vírgulas entre chaves:

```java

int[] n = { 10, 20, 30, 40, 50 };

```

Se percorrermos o array com um laço, imprimindo o index e seu valor correspondente a cada interação, com o seguinte código:

```java

System.out.printf("%s%8s%n", "Index", "Valor"); // títulos de coluna
// gera saída do valor de cada elemento do array
for (int i = 0; i < n.length; i++)
    System.out.printf("%5d%8d%n", i, n[i]);

```

Teremos o seguinte output:
```
Index   Valor
    0      10
    1      20
    2      30
    3      40
    4      50
```


## Estudo de caso: simulação de embaralhamento e distribuição de cartas

Objetivo: Usar números aleatórios e criar um array para armazenar objetos que representam cartas de baralho.

A classe "Card" tem um método construtor para atribuir um valor de face (ás, dois,três... valetes, damas, reis) e um de naipe (coração, paus, espadas e ouros).
A Classe DeckOfCards cria um baralho de 52 cartas, e possui atributo para identificar qual é a carta atual e métodos para embaralhar as cartas.


### Código

=== "Card.java"

    ```java
    public class Card
    {
        private final String face; // face da carta ("Ace", "Deuce", ...)
        private final String suit; // naipe da carta ("Hearts", "Diamonds", ...)

        // construtor de dois argumentos inicializa face e naipe da carta
        public Card(String cardFace, String cardSuit)
        {
            this.face = cardFace; // inicializa face da carta
            this.suit = cardSuit; // inicializa naipe da carta
        }

        // retorna representação String de Card
        public String toString()
        {
            return face + " of " + suit;
        }
    } // fim da classe Card
    ```

=== "DeckOfCards.java"

    ```java
    
    import java.security.SecureRandom;
    
    public class DeckOfCards
    {
        private Card[] deck; // array de objetos Card
        private int currentCard; // índice da próxima Card a ser distribuída (0-51)
        private static final int NUMBER_OF_CARDS = 52; // número constante de Cards
        // gerador de número aleatório
        private static final SecureRandom randomNumbers = new SecureRandom();
    
        // construtor preenche baralho de cartas
        public DeckOfCards()
        {
            String[] faces = {"Ace", "Deuce", "Three", "Four", "Five", "Six",
                    "Seven", "Eight", "Nine", "Ten", "Jack", "Queen", "King"};
            String[] suits = {"Hearts", "Diamonds", "Clubs", "Spades"};
            deck = new Card[NUMBER_OF_CARDS]; // cria array de objetos Card
            currentCard = 0; // a primeira Card distribuída será o deck[0]
    
            // preenche baralho com objetos Card
            for (int count = 0; count < deck.length; count++)
                deck[count] = new Card(faces[count % 13], suits[count / 13]);
        }
    
        // embaralha as cartas com um algoritmo de uma passagem
        public void shuffle()
        {
            // a próxima chamada para o método dealCard deve começar no deck[0] novamente
            currentCard = 0;
            // para cada Card, seleciona outra Card aleatória (0-51) e as compara
            for (int first = 0; first < deck.length; first++) {
                // seleciona um número aleatório entre 0 e 51
                int second = randomNumbers.nextInt(NUMBER_OF_CARDS);
                // compara Card atual com Card aleatoriamente selecionada
                Card temp = deck[first];
                deck[first] = deck[second];
                deck[second] = temp;
            }
        }
    
        // distribui uma Card
        public Card dealCard()
        {
            // determina se ainda há Cards a serem distribuídas
            if (currentCard < deck.length)
                return deck[currentCard++]; // retorna Card atual no array
            else
                return null; // retorna nulo para indicar que todos as Cards foram distribuídas
        }
    }

    ```

=== "DeckOfCardsTest.java"

    ```java
    
    public class DeckOfCardsTest
    {
        // executa o aplicativo
        public static void main(String[] args)
        {
            DeckOfCards myDeckOfCards = new DeckOfCards();
            myDeckOfCards.shuffle(); // coloca Cards em ordem aleatória

            // imprime todas as 52 cartas na ordem em que elas são distribuídas
            for (int i = 1; i <= 52; i++) {
                // distribui e exibe uma Card
                System.out.printf("%-19s", myDeckOfCards.dealCard());
                if (i % 4 == 0) // gera uma nova linha após cada quarta carta
                    System.out.println();
            }
        }
    } // fim da classe DeckOfCardsTest
    
    ```

Como as cartas são embaralhadas, um output possível será: 

```
Seven of Diamonds  Queen of Spades    Six of Hearts      Three of Spades    
Three of Clubs     Eight of Spades    Eight of Hearts    Nine of Diamonds   
Seven of Clubs     Three of Diamonds  Five of Hearts     Six of Clubs       
King of Clubs      Ace of Hearts      Eight of Clubs     Nine of Hearts     
Ace of Spades      King of Diamonds   Four of Hearts     Eight of Diamonds  
Jack of Hearts     Jack of Diamonds   Ace of Diamonds    Queen of Diamonds  
King of Hearts     Ten of Spades      Deuce of Diamonds  Nine of Spades     
Five of Diamonds   Ten of Diamonds    Ten of Hearts      Six of Diamonds    
Jack of Spades     Three of Hearts    Four of Clubs      Four of Spades     
Four of Diamonds   Ace of Clubs       Queen of Hearts    Nine of Clubs      
Jack of Clubs      Ten of Clubs       Five of Spades     Seven of Spades    
Seven of Hearts    Deuce of Hearts    Six of Spades      Deuce of Spades    
King of Spades     Deuce of Clubs     Queen of Clubs     Five of Clubs     
```


A cada nova execução do programa teremos um output com ordem diferente, mas sempre com as mesmas 52 cartas.

## Referências

**Deitel, Paul**. Java: como programar / Paul Deitel, Harvey Deitel; tradução Edson Furmankiewicz; revisão técnica Fabio Lucchini. -- São Paulo: Pearson Education do Brasil, 2017