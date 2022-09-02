# O Módulo Turtle
Turtle é um módulo embutido (built-in) do Python que tem por objetivo ensinar programação à crianças. 

Com este módulo temos essencialmente duas classes: Screen() e Turtle().


Aqui estão alguns exemplos do que é possível fazer com a Tartaruga. Estes exemplos foram retirados do [Portal Acervo Lima](https://acervolima.com/componente-react-suite-portal/), 
que por sua vez são traduções do portal [GeeksforGeeks](https://www.geeksforgeeks.org). Todos exemplos estão sob licença [CreativeCommons](https://creativecommons.org).


## Relógio Digital 
![relogio-digital](https://user-images.githubusercontent.com/72423464/163482332-329708df-da99-4902-999e-2edb2f8a8fc3.gif)

```python
import time
import datetime as dt
import turtle

# cria duas instâncias do objeto turtle
t = turtle.Turtle()  # para a hora em si
t1 = turtle.Turtle()  # para a borda

# cria a tela (SCREEN)
s = turtle.Screen()

# escolhe a cor de fundo da tela
s.bgcolor("green")

# cria três variáveis que armazenam a hora atual
segundos = dt.datetime.now().second
minutos = dt.datetime.now().minute
hora = dt.datetime.now().hour

# define a grossura (width) e a cor da caneta da borda para a instância t1
t1.pensize(3)
t1.color('black')

t1.penup()
t1.goto(-20, 0)
t1.pendown()

# desenha a borda
for i in range(2):
    t1.forward(200)  # distância horizontal
    t1.left(90)  # graus para a esquerda
    t1.forward(70)  # distância vertical
    t1.left(90)  # retorna para direita

# esconde a tartaruga t1
t1.hideturtle()

# cria um loop infinito que mantém a hora atualizada
while True:
    # mantém escondida a tartaruga t
    t.hideturtle()
    t.clear()

    # usa o método write() passando as horas, minutos e segundo
    # usa-se o zfill() para que sempre tenham duas casas, p.ex. quando for "2 horas" mostrará "02 horas"
    # e define o parâmetro font=()
    t.write(str(hora).zfill(2)
            + ":" + str(minutos).zfill(2) + ":"
            + str(segundos).zfill(2),
            font=("Arial Narrow", 35, "bold"))

    # pausa o programa por 01 segundo
    time.sleep(1)

    # aumenta manualmente os segundos
    segundos += 1

    # lógica de um relógio digital
    if segundos == 60:
        segundos = 0
        minutos += 1

    if minutos == 60:
        minutos = 0
        hora += 1

    if hora == 24:
        hora = 1

```


## Arco-íris
![arco-iris](https://user-images.githubusercontent.com/72423464/163484724-ef54932b-b65a-413c-b602-ae14afff448e.gif)

```python
import turtle
import time

sc = turtle.Screen()

pen = turtle.Turtle()


def semi_circle(col, rad, val):
    # atribui cor à caneta
    pen.color(col)

    # desenha um semicirculo com o método circle()
    # no caso, -180 é um parâmetro opcional, por default circle() desenha um circulo completo.
    pen.circle(rad, -180)

    # levanta a caneta, ou seja, NÃO desenha enquanto se move
    pen.up()

    # reposiciona a caneta
    pen.setpos(val, 0)

    # abaixa a caneta e reposiciona o ângulo
    pen.down()
    pen.right(180)


col = ['violet', 'indigo', 'blue',
       'green', 'yellow', 'orange', 'red']

# tamanho da tela
sc.setup(600, 600)

# cor de fundo
sc.bgcolor('#d6ffff')

pen.right(90)  # angulo a direita
pen.width(10)  # espessura do contorno
pen.speed(7)  # velocidade do desenho

# cria um laço iterativo que irá ser executadoi 07 vezes
# para cada iteração será selecionado uma cor diferente e
# a caneta será reposicionada
for i in range(7):
    semi_circle(col[i], 10 * (
            i + 8), -10 * (i + 1))

time.sleep(1)

pen.hideturtle()
```

## Octógono
![octogono](https://user-images.githubusercontent.com/72423464/163486437-37931390-aeec-4049-948a-3f5d2cc4589f.gif)
```python
import turtle
import time

ws = turtle.Screen()

t = turtle.Turtle()

t.pencolor("blue")
t.speed(3)
t.pensize(5)

# o loop abaixo será executado 08 vezes
# a cada iteração a caneta andará 100 e depois girará 45º à esquerda
for i in range(8):
    t.forward(100)
    t.left(45)

time.sleep(2)
```


## Teia de aranha
![teia-aranha](https://user-images.githubusercontent.com/72423464/163488332-2cdf1ad9-51dd-4c47-8766-71554a5697b3.gif)

```python
""""


O laço interno se preocupa com a construção de uma única espiral em espiral e com as camadas da teia,
enquanto o laço externo controla o número de espirais a serem construídas.


"""

# importando o módulo turtle como "t", não precisamos instanciar a classe
import turtle as t
import time

t.speed(2)

# A tartaruga é movida para frente e para trás para construir primeiro os fios.
# A tartaruga é girada em um ângulo de 60 graus para desenhar cada fio .
for i in range(6):
    t.forward(100)
    t.backward(100)
    t.right(60)
side = 50  # O comprimento da rosca espiral é definido como 50
t.fillcolor("Yellow")
t.begin_fill()

# O laço interno se preocupa com a construção de uma única espiral em espiral e com as camadas da teia,
# enquanto o laço externo controla o número de espirais a serem construídas.
for i in range(10):
    t.penup()
    t.goto(0, 0)
    t.pendown()
    t.setheading(0)
    t.forward(side)
    t.right(120)

    for j in range(6):
        t.forward(side - 2)
        t.right(60)
    side = side - 10  # reduzimos o tamanho em 10 a cada iteração.

t.end_fill()
time.sleep(2)
```

## Gráfico de Barras
![barras](https://user-images.githubusercontent.com/72423464/163488946-8cc22f86-b283-4455-a134-407993dc61b3.gif)

```python
# Python program to draw a turtle
import turtle


# Function that draws the turtle
def desenha_barras(t, height, color):
    # Começa o preenchimento
    t.fillcolor(color)
    t.begin_fill()
    t.left(90)
    t.forward(height)
    t.write(str(height))
    t.right(90)
    t.forward(40)
    t.right(90)
    t.forward(height)
    t.left(90)

    # para o preenchimento
    t.end_fill()


# xs é uma lista que recebe número de barras e suas alturas

xs = [48, 117, 150, 96, 134, 160, 90]
clrs = ["green", "red", "yellow", "black",
        "pink", "brown", "blue"]

maxheight = max(xs)
numbars = len(xs)
border = 7

# Set up the window and its
# attributes
wn = turtle.Screen()
wn.setworldcoordinates(0 - border, 0 - border,
                       80 * numbars + border,
                       maxheight + border)

# Cria instância da classe
tess = turtle.Turtle()
tess.pensize(3)

for i in range(len(xs)):
    desenha_barras(tess, xs[i],
                   clrs[i])

wn.exitonclick()```

## Estrela 
![estrela](https://user-images.githubusercontent.com/72423464/163490419-5e9b995a-5e73-4065-b7f1-a2a4ce163318.gif)

```python
estrela.py
```


## Smile
![smile](https://user-images.githubusercontent.com/72423464/163490695-94515a29-9a00-4ec5-b0df-5fe30c6145a7.gif)

```python
import turtle
import time

pen = turtle.Turtle()


def eye(col, rad):
    pen.down()
    pen.fillcolor(col)
    pen.begin_fill()
    pen.circle(rad)
    pen.end_fill()
    pen.up()


pen.fillcolor('yellow')
pen.begin_fill()
pen.circle(100)
pen.end_fill()
pen.up()

pen.goto(-40, 120)
eye('white', 15)
pen.goto(-37, 125)
eye('black', 5)
pen.goto(40, 120)
eye('white', 15)
pen.goto(40, 125)
eye('black', 5)

pen.goto(0, 75)
eye('black', 6)

pen.goto(-40, 85)
pen.down()
pen.right(90)
pen.circle(40, 180)
pen.up()

pen.goto(-10, 45)
pen.down()
pen.right(180)
pen.fillcolor('red')
pen.begin_fill()
pen.circle(10, 180)
pen.end_fill()
pen.hideturtle()

time.sleep(2)
```

## Relógio
![relogio](https://user-images.githubusercontent.com/72423464/163491342-08ecf69b-f880-4d33-b815-7e732e5d953c.gif)

```python

import turtle
import time
screen = turtle.Screen()
# configuração da tela
screen.setup(500, 500)
# instância turtle
clk = turtle.Turtle()
# cor da tartaruga
clk.color('Green')
# espessura contorno
clk.width(4)
def draw_hour_hand():
    clk.penup()
    clk.home()
    clk.right(90)
    clk.pendown()
    clk.forward(100)
# valores numericos do relogio
val = 0
# loop para imprimir numeros
for i in range(12):
    # incrementa 1
    val += 1
    # move a tartaruga
    clk.penup()
    # movimento circular
    clk.setheading(-30 * (i + 3) + 75)

    clk.forward(22)
    # coloca caneta na superfície
    clk.pendown()
    # move para linha tracejada
    clk.forward(15)

    clk.penup()

    clk.forward(20)
    # escreve numeros
    clk.write(str(val), align="center",
              font=("Arial",
                    12, "normal"))

clk.setpos(2, -112)
clk.pendown()
clk.width(2)
# preencher de verde
clk.fillcolor('Green')
# começa preenchimento
clk.begin_fill()
# faz circulo de radius 5
clk.circle(5)
# fim preenchimento
clk.end_fill()
clk.penup()
draw_hour_hand()
clk.setpos(-20, -64)
clk.pendown()
clk.penup()
# seleciona posição e escreve texto
clk.setpos(-30, -170)
clk.pendown()
clk.write(' Relógio com \n Turtle', font=("Arial", 12,
                              "normal"))
clk.hideturtle()
turtle.done()
time.sleep(2)
```

## Espirógrafo
![espirografo](https://user-images.githubusercontent.com/72423464/163491636-996a725c-4a5a-4544-85c9-48c0c868137f.gif)

```python
import turtle as tt
import time

tt.bgcolor('black')
tt.pensize(2)
tt.speed(15)
for i in range(6):

    for color in ('red', 'magenta', 'blue',
                  'cyan', 'green', 'white',
                  'yellow'):
        tt.color(color)

        tt.circle(100)

        tt.left(10)

    tt.hideturtle()

time.sleep(2)
```


