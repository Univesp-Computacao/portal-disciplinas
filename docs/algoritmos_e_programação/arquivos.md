# Manipulação de Arquivos


A manipulação de arquivos sempre foi um tema central na computação, pois afinal,
não é muito útil ter que executar repetidas vezes o mesmo código para manter um histórico de resultados, já que, a linguagem de programação em si, não é capaz de armazenar dados.

A manipulação de arquivos é um recurso poderoso que serve basicamente para transferir informação para algum arquivo de texto, que seja facilmente guardado por qualquer tipo de Sistema Operacional (*.html, *.txt, *.csv, *.md, etc.). Mas por se tratar do uso direto de recursos da máquina, 
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


Sem precisar importar nenhum módulo específico utilizamos a função `open()` que retorna um objeto de manipulação de arquivos.


Dentro da função `open()`, passamos apenas dois parâmetros: o **nome do arquivo** e o **modo de abertura**, e este arquivo ficou
armazenada em uma variável do nosso programa (`arquivo`)

Alguns podem pensar que a funçção `open()` irá abrir o arquivo no sistema operacional, mas não, ela apenas cria uma conexão entre a memória RAM
e o HD/SSD.


Usamos o método `write()` para escrever dentro do arquivo, passando como argumento uma string ou mesmo uma outra variável que aponte para uma string.

Com o `with` no início da expressão estamos indicando que estamos trabalhando **em contexto**, ou seja, o arquivo será automaticamente fechado após o uso. Isso simplesmente nos ajuda a usar com precisão os recursos da máquina.

***
# Criando um arquivo .txt a partir de uma API

Para tornar o uso de arquivos verossímil à realidade vamos dar um exemplo bem casual. Suponha que você precise consultar um CEP e armazenaro bairro, a cidade e a UF.

```python
import requests

mensagem = "\n Olá, digite o cep que desejas armazenar: \n"

cep = input(mensagem)

url = f"http://viacep.com.br/ws/{cep}/json/"

retorno = requests.get(url)

conteudo = retorno.json()

bairro = conteudo['bairro']
localidade = conteudo['localidade']
uf = conteudo['uf']

endereco = f"{bairro} \t {localidade} \t {uf} "
with open('enderecos.txt', 'a') as arquivo:
    arquivo.write(endereco)
    arquivo.write('\n')
```

Com o módulo requests fazemos uma requisição à URL da API ViaCep, e passamos através de uma `f-string`, a variável contendo o número do CEP em formato string.

Recebemos dessa requisição um objeto `<class 'requests.models.Response'>`, que contém justamente o código da resposta. Se recebermos `<Response [200]>` , perfeito, podemos prosseguir.

O próximo passo é transformar esse `requests.models` em um dicionário no python utilizando o método `json()`. A partir de agora podemos manipular o conteúdo propriamente dito da nossa requisição, pois agora estamos trabalhando com um objeto de tipo ` <class 'dict'>`.

A cada vez que executarmos este código e passarmos um cep válido, ficará salvo em um arquivo chamado 'enderecos.txt' as informações que selecionamos.

![image](https://user-images.githubusercontent.com/72423464/169721114-ffcd93dd-03db-4859-a0cd-a98870a6f870.png)

## Observação

A proposta desse código era apenas para explorar um pouco da combinação do módulo requests (que deve ser instalado via pip) e a manipulação de arquivos, usando métodos diretamente do Python, como o open(), write(), readlines() entre outros.

Há muito a se fazer com respeito da tratativa de exceções. A primeira e mais óbvia seria que dentro do input apenas fosem aceitos apenas números e que o tamanho dessa string fosse igual a 8.


# Referências e links úteis

- https://pypi.org/project/requests/
- https://viacep.com.br


