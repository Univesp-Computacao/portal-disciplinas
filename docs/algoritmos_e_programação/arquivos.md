Manipulação de Arquivos


A manipulação de arquivos sempre foi um tema central na computação, pois afinal,
não é muito útil ter que executar repetidas funções com a função de manter um histórico de resultados. 

A manipulação de arquivos é um recurso poderoso que se não bem usado prejudicará
não apenas a sua aplicação mas o sistema operacional de quem a usa. 

Mas por que manipular arquivos é tão especial? Porque permite de maneira simples
a persistência dos dados, ou seja, estamos transferindo o que o Python armazena na RAM para um HD/SSD.

Como no simples exemplo abaixo: 
```python

linha = []
for i in range(1, 4):
    coluna = []
    for j in range(1, 4):
        coluna.append(j)
    with open("matriz.txt", 'w') as arquivo:
        arquivo.write(str(coluna))

```

Sem precisar importar nenhum módulo específico utilizamos a função open() que retorna um objeto de manipulação de arquivos.

Dentro da função `open()`, passamos apenas dois parâmetros: o **nome do arquivo** e o **modo de abertura**, e este arquivo ficou
armazenada em uma variável do nosso programa (`arquivo`)

Alguns podem pensar que a funçção `open()` irá abrir o arquivo no sistema operacional, mas não, ela apenas cria uma conexão entre a memória RAM
e o HD/SSD.

Usamos o método `write()` para escrever dentro do arquivo, passando como argumento uma string ou mesmo uma outra variável que aponte para uma string.


