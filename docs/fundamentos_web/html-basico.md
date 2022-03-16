### Organização em Tags
```html 
<!DOCTYPE>
    <html>
        <head>
        </head>
        <body>
            <h1> Aqui temos um títutlo H1</h1>
            <p> E aqui temos um parágrafo.</p>
        </body>
    </html>
```
O documento HTML por padrão sempre começa com a tag **< !DOCTYPE >**.

A tag **< html >** identifica o formato do documento e contém todas as outras tags do documento. 

A **< head >** é a tag que guarda metadados. Seu conteúdo não é exibido, a não ser no título do documento, que será exibido na aba pelo navegador.

O **< body >** é o local onde tudo o que for sendo inserido será exibido na tela principal do navegador. 
Dentro do body colocamos todas as outras tags que irão compor o documento como: main, header, navbar, aside, forms, footer.    

### Recursos do HTML
 - Uma linguagem fácil e simples, pode ser facilmente entendida e rapidamente praticada.
 - Fácil de fazer documentos impactantes, devido a suass tags semânticas.
 - É uma linguagem de marcação, logo, ela proporciona um design flexível.
 - Facilita nossa vida ao nos permitir criar qualquer tipo de link dentro da página.
 - Não depende de plataforma: roda no Windows, Mac, Linux, qualquer smartphone.
 - É um grande mundo multimídia: é possível colocar gráficos, vídeos e sons!

### Novos Recursos do HTML 5 
- **Novos elementos semânticos!**
- **Forms 2.0** - Novos atributos e melhorias para a tag **< input >**.
- **WebSocket** - Uma nova geração bidirecional de comunicação para tecnologias web.
- **Canvas** - Permite desenho bidimensional utilizando JavaScript.
- **Audio e Vídeo** - Agora isso já vem nativo no HTML, não precisa de terceiros.
- **Server-Sent Events** - Permite toda a indústria de streaming.
- **Geolocalização** - Os visitantes podem decidir compartilhar a geolocalização com a aplicação web.
- **Drag and drop** - Arrastar e jogar, função que permite um jeito interativo de manipular arquivos.
- **Microdata** - Permite que o autor customize seus próprio elementos semântico, relação entre item <-> propriedades. 

### Encodando caracteres

Os autores do documento devem informar o metadado de charset no início do documento:

```html
<!DOCTYPE html>
<html lang="pt-BR"> <!-- define o idioma do documento -->
    <head>
        <meta charset="UTF-8"> <!-- define o tipo de letra do documento -->
        <title>Título</title>
    </head>
```

### Linkando arquivo CSS
Para fazer ligação com um arquivo CSS, ainda dentro da tag **< head >** abra uma tag **< link >**:

```html
<html>   
    <title>Título</title>
        <link rel="stylesheet" href="style.css"> <!--linkando CSS -->
</html>
```

### Fazendo conexão com um arquivo javaScript

Mediante a tag **< script >**. 

```html
<html>
    <script src = "js/meuscript.js"> </script>
</html>
```

Com essas informações você já tem seu documento HTML pronto para uso.


### Saiba mais: 

- [W3 Schools](https://www.w3schools.com)
- [MDN Web Docs](https://developer.mozilla.org/pt-BR/)
- [Principais Tags](https://diegomariano.com/tags-html/)
- [O que é a Web Semântica ](https://pt.wikipedia.org/wiki/Web_sem%C3%A2ntica)