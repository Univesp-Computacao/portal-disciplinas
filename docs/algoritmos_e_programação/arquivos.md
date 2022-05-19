Manipulação de Arquivos


A manipulação de arquivos sempre foi um tema central na computação, pois afinal,
não é muito útil ter que executar repetidas vezes o mesmo códigopara manter um histórico de resultados. 

A manipulação de arquivos é um recurso poderoso que serve basicmanete para transferr informação para alguma arquivo de texto, que seja facilmente guardado por qualquer tipo de Sistema Operacional (*.html, *.txt, *.csv, *.md, etc.). Mas por se tratar do uso direto de recursos da máquina, 
devemos monitorar esse uso para não prejudicar apenas a aplicação mas o sistema operacional de quem a usa. 

Mas por que manipular arquivos é tão especial? Porque permite de maneira simples
a persistência dos dados, ou seja, estamos transferindo o que o Python armazena na RAM para um HD/SSD.

Como no simples exemplo abaixo: 
```python
mensagem = "Variavel para gravar informacao em tipo string"

with open("output.txt", 'w') as arquivo:
    arquivo.write(mensagem)

```
Como **resultado** deste comando temos a transferência do valor de string que a variável `mensagem` assumiu temporariamente na memória RAM e escrevemos em um HD/SSD, de modo a preservar a informação, visto que o linguagens de programação isoladas não possuem poder de persistência de dados, precisando armazenar em arquivos diretamente no Sistema Operacional, ou, em softwares especializadas, como Bancos de Dados.

![Uploading image.png…]()

Sem precisar importar nenhum módulo específico utilizamos a função open() que retorna um objeto de manipulação de arquivos.

![Uploading image.png…]()

Dentro da função `open()`, passamos apenas dois parâmetros: o **nome do arquivo** e o **modo de abertura**, e este arquivo ficou
armazenada em uma variável do nosso programa (`arquivo`)

Alguns podem pensar que a funçção `open()` irá abrir o arquivo no sistema operacional, mas não, ela apenas cria uma conexão entre a memória RAM
e o HD/SSD.

![Uploading image.png…]()

Usamos o método `write()` para escrever dentro do arquivo, passando como argumento uma string ou mesmo uma outra variável que aponte para uma string.

Com o with no início da expressão estamos indicando que estamos trabalhando em contexto, ou seja, o arquivo será automaticamente fechado após ouso. 

***
# Criando Arquivos .txt, .csv

Para tornar o uso de arquivos verossímil à realidade vamos dar um exemplo bem casual. Suponha que você precise consultar alguns CEPS em uma base de dados e armazene o valor do dado desejado. 

Vamos usar a API viacep para mostrar como acessar, selecionar e armazenar uma informação. 

![Uploading image.png…]()

Explicando o código:


