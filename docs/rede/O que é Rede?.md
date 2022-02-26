# Para iniciar vamos nos perguntar, o que é a rede?

>Em termos mais simples, uma rede consiste em dois ou mais computadores que estão conectados para compartilhar informações. Todas as redes, não importa quão complexas sejam, baseiam se neste principio simples. Embora isto possa parecer como uma idéia basica, o conceito foi uma grande conquista na área das comunicações, ou seja, desde um ambiente doméstico, em que temos dois computadores e uma impressora, até grandes corporações com centenas de usuários, máquinas potentes com servidores, até a mais famosa, a internet.

* * *
## Endereço de IP, como chegar lá?

Vamos lembrar como era alguns anos atrás quando ainda enviávamos cartas: era necessario uma carta com o destinario e o endereço para que o carteiro saber aonde devia entregar a carta. No mundo da internet, o processo de identificação será parecido. O processo de identificação das máquinas é chamado de endereçamento IP. 

Vamos abrir o terminal de comando e verificar nosso endereço IP.

No Mac e Linux:
~~~bash
ifconfig
~~~
**Verificar inet**

No Windows:
~~~bash
ipconfig
~~~
**Verificar o Endereço IPv4**

Em todo o caso o numero do seu IP parecido com esse ***192.168.1.21***.

* * *
## Certo agora sei o que é endereço de IP, mas para que serve?

Ele serve para dizer seu endereço, ou seja, a casa que você mora por exemplo. E vamos tentar encontrar o endereço do Google. Mas para isso vamos usar uma ferramenta chamada **ping**.

Lá no seu terminal digite:

~~~bash
ping www.google.com.br
~~~

E você vai recever um retorno parecido com esse:

~~~bash
PING www.google.com.br (142.251.129.35) 56(84) bytes de dados.
64 bytes de gru06s72-in-f3.1e100.net (142.251.129.35): icmp_seq=1 ttl=120 tempo=3.22 ms
64 bytes de gru06s72-in-f3.1e100.net (142.251.129.35): icmp_seq=2 ttl=120 tempo=4.18 ms
64 bytes de gru06s72-in-f3.1e100.net (142.251.129.35): icmp_seq=3 ttl=120 tempo=4.12 ms
64 bytes de gru06s72-in-f3.1e100.net (142.251.129.35): icmp_seq=4 ttl=120 tempo=4.54 ms
~~~

E apareceu um numero estranho na primeira linha após o Google, o que será esse numero?

Bem se você reparou no seu ip, ele é bem parecido né? Então esse é o numero IP do Google **142.251.129.35** se você copiar e colar no seu navegador ele vai te direcionar para pagina de pesquisa do Google.

Por trás dos panos é assim que a rede se conecta, claro que ainda tem um pouco mais de informação envolvido mais vamos chegar lá, vou dá algumas dicas para pesquisar: DNS, ICMP, RTT e TTL.

>DNS - Domain Name System
>ICMP - Internet Control Message Protocol
>RTT - Round trip time
>TTL - Time to Live

Curiosidade: O ping usa o protocolo ICMP, para enviar uma requisição (Echo Request) para máquina remota e aguarda o retorno dessa máquina remota (Echo Reply).

* * *
## Certo me conectei no site do Google que é uma empresa dos EUA, como isso é possivel?

Bom, é verdade como um computador aqui no Brasil se conectar em um computador lá nos EUA?
>A conexão segue por uma rota, entre você e o destino, ou seja, ele vai passar por diversos dispositivos que estão mediano essa conexão.

Vamos abrir o terminal novamente e digite:

No Windows:
~~~
tracert www.google.com.br
~~~

No Mac ou Linux:
~~~
traceroute www.google.com.br
~~~

E ele vai te responder dessa forma:
~~~
 1  _gateway (192.168.1.21)  0.805 ms  0.757 ms  1.620 ms
 2  10.255.1.2 (10.255.1.2)  2.803 ms  2.880 ms  2.940 ms
 3  10.55.55.1 (10.55.55.1)  3.245 ms  3.715 ms  3.542 ms
 4  * * *
 5  218.30.38.13 (218.30.38.13)  4.907 ms  5.420 ms  5.667 ms
 6  84.16.7.214 (84.16.7.214)  7.380 ms  7.712 ms  7.973 ms
~~~

Veja que o IP está mudando para cada linha que ele retorna, ou seja, ele está indo em direção ao endereço da Google para se comunicar com ele. Ele pode ter mais ou menos linhas, mas a logica é simples a requisão vai para o seu provedor de internet e lá recebe a resposta do endereço que você está procurando. 

Temos outro detalhe para aborda sobre essa rota:
~~~
4  * * *
~~~

Na rota numero **4*** ela retornou diferente das outras com os asterisco, o que significa?
Basicamente a pessoa/empresa que administra esse IP pode ter desabilitado a resposta do ICMP da máquina, para evitar a sobrecarga de tráfego e por questões de segurança.
