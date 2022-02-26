# Agora que você sabe o que é uma rede e como ela é composta, vamos fazer um projeto simples de rede: A conexão entre dois computadores

Para isso vamos usar dois aparelhos conectados a internet, como não sei como você está acessando esse material, vou usar um computador e um aparelho android. Esse teste pode ser feito usando tanto android - android ou PC - PC. Basta que ambos esteja conectados na internet.

Vamos precisar também do numero IP dos aparelhos. Meu computador tem o IP: **192.168.1.21**, e  o do meu celular android é **192.168.1.3**

Agora vai no seu terminal e use o ping para se comunicar com o outro dispositivo.
~~~
ping 192.168.1.3
~~~
Para finalizar o ping digite ctrl+c ou feche o terminal.

E ele vai retorna:
~~~
PING 192.168.1.3 (192.168.1.3) 56(84) bytes de dados.
64 bytes de 192.168.1.3: icmp_seq=1 ttl=64 tempo=112 ms
64 bytes de 192.168.1.3: icmp_seq=2 ttl=64 tempo=35.3 ms
64 bytes de 192.168.1.3: icmp_seq=3 ttl=64 tempo=53.8 ms
64 bytes de 192.168.1.3: icmp_seq=4 ttl=64 tempo=77.2 ms
~~~

Agora se você não tem acesso a outro dispositivo, tenho uma solução.

Va lá no seu terminal e digite:
~~~
ping 127.0.0.1
~~~

Este tipo de endereçamento chamamos de loopback, em que ele enviará a informação para ele mesmo para verificar se está tudo funcionando nesta transmissão interna. Lembrando que os endereços que começam com 127 são reservados para o loopback.
>Também é possivel usar o localhost no lugar do numero IP para realizar o loopback.

~~~
ping localhost
~~~

### Para pesquisar:

>**Hub**: é um equipamento utilizado para interconectar diversos dispositivos finais.
>**NAT** é um método de tradução de endereços privados e públicos.
>**Servidor** é uma máquina centralizada que oferece serviços a um cliente (ex: computador)
>**Máscara de rede** é usado para determinar se dois equipamentos estão na mesma rede

## Protocolos

Os protocolos em redes de telecomunicações seguem uma hierarquia e cada um é responsável por determinada função na comunicação. Apesar de a tecnologia ter atingido um ponto importante nos protocolos e na sua segurança nem sempre foi assim e dessa forma, foi criado um modelo que tinha como intuito padronizar o desenvolvimento de hardware e software dos mais variados tipos de fabricantes para que pudessem assim se comunicar, mesmo que um tivesse alguns recursos a mais que o do outro fabricante, a comunicação deveria ser estabelecida. Para isso, foi definido que esses protocolos de comunicação seriam divididos em 7 camadas de comunicação, o chamado modelo OSI (Open System Interconnection) . O protocolo TCP por exemplo, encontra-se na camada 4 que é conhecida como camada de transporte, o protocolo IP encontra-se na camada 3 que é conhecida como camada de rede.
A parte de protocolos é um assunto muito vasto e sugiro que faça uma pesquisa sobre o modelo OSI e os principais protocolos que temos em cada camada.

## Links uteis para continuar a aprender sobre redes

Para iniciar com os estudos em rede:
[Recomendo o conteúdo do Professor Guanabara que está disponivel no youtube](https://www.youtube.com/playlist?list=PLHz_AreHm4dkd4lr9G0Up-W-YaHYdTDuP)

Para se aprofundar com os estudos em rede:
[Recomendo o conteúdo do Hardware Redes Brasil qie está disponivel no youtube](https://www.youtube.com/playlist?list=PLAp37wMSBouBnNup2tD-mC36JT96vHBZy)