# Primeiro Contato com Git

## Pré-requisitos para se aprender Git básico
Embora Git seja de fato um programa muito simples, fácil e divertido de usar ele requer alguns conceitos básicos anteriores. Se você já tiver alguma experiência com
o Terminal de Comandos, tudo será muito mais fácil. Se você ainda não utiliza o Terminal de Comandos pense em começar a usar pois ele irá te ajudar em diversas 
funções. O recomendado é saber o básico dos comandos de navegação no terminal, como criar um diretório, como criar um arquivo, com listar diretórios e arquivos, entre 
outros.
- [Usando Terminal de Comandos no Windows](https://blog.cod3r.com.br/terminal-no-windows/)
- [Usando Terminal no MacOS](https://recoverit.wondershare.com.br/mac-tips/how-to-open-terminal-and-use-terminal-on-mac.html)
- [Guia de Comandos no Terminal - Linux](https://www.hostinger.com.br/tutoriais/comandos-linux) 


## Instalando o Git em sua máquina. 
- [Instalação para Windows](https://dicasdeprogramacao.com.br/como-instalar-o-git-no-windows/)
- [Instalando em MacOS](https://br.atsit.in/archives/30539) 
- [Instalando em sistemas Linux](https://git-scm.com/book/pt-br/v2/Come%C3%A7ando-Instalando-o-Git) 


## :sparkles: Verificando a versão instalada
1. Inicie um terminal de comandos ou git bash
2. Certifique-se de que o git está istalado com o comando:
```bash
git --version
```
3. Se você recebeu confirmação da versão, continue.

## :sparkles: Configurando GitHub localmente
Inicie o Terminal e digite o seguinte comando para adicionar seu nome de usuário Github:
```bash
git config--global user.name "seu_github_username"
```

Em seguida, adicione seu e-mail usando este comando:
```bash
git config--global user.email "seu_email@github.com"
```

## Iniciando um repositório 
Navegue pelo terminal de comandos até o diretório em que deseja iniciar o repositório. 
Certifique-se que está no diretório correto com o comando pwd (print working directory):
```bash
pwd
```
e digite o comando que incia o Git no seu diretório corrente:
```bash
git init
```
ou, caso o repositório já exista no GitHub, você poderá clonar:
```bash
git clone
```


## :sparkles: Adicionando Arquivos e Preparando o Commit: 
Agora que você já trabalhou no seu código é hora de adicioná-lo para a versão corrente. 
Para aicionar arquivos use o comando:
```bash
git add
```

## :sparkles: Analisando o Status antes do Commit:
O Git permite que você veja as mudanças adicionadas antes de comitá-las, ou seja, transferí-las para a versão corrente. 
Com o comando: 
```bash
git status
```
Você receberá um texto em inglês mais ou menos assim: 

![image](https://user-images.githubusercontent.com/72423464/155199941-05ae18c1-364d-4315-8409-8f3a1af8d2df.png)

Por mais que inglês não seja seu forte observe a informação e tente compreender o **relatório de status do Git**. 
Aos poucos se tornará natural analisar o status fornecido pelo Git. Observe as informações em destaque, elas se referem a sua branch atual, 
e depois apontam arquivos que ainda não foram adicionados para o commit.

## :sparkles: Comitando:

Com tudo conferido você já pode mandar suas alterações para a versão mais recente do código, e isso se chama __fazer commit__.
Commit é uma palavra em inglês que no caso poderia ser traduzida para entregar, enviar.
Para dar um commit é muito simples:
```bash
git commit -m "sua mensagem de commit" 
```

Usa-se o comando commit com a tag "-m" para escrevermos uma mensagem. A mensagem de commit deverá ser clara e limpa, no começo o mais comum é 
"primeiro commit", "atualizando arquivo ", etc.

## :sparkles: Adicionando um repositório remoto:
Com o commit, atualizamos apenas a versão do código que está em nossa máquina. Agora enviaremos ao repositório no GitHUb: 
Se o repositório foi inicializado no diretório local precisamos dar o seguinte comando: 

```bash
git remote add origin [url-do-seu-repositorio-do-github]
```
Esse passo é para você dizer ao git qual é o seu endereço do diretório. Perceba que a URL que você deve inserir termina com ".git"
Você acha nessa parte do github:
![image](https://user-images.githubusercontent.com/72423464/155206018-56727358-d41d-414a-af8c-7b61295e08f8.png)


Escolha o método HTTPS se ainda não tiver consigurado o SSH.

## :sparkles: Levantando as modificações feitas para o repositório remoto (push)
```bash
git push -u origin [nome-da-branch]

```
Se tudo der certo você deverá acessar seu repositório do GitHub e ele já estará atualizado com as últimas modificações. Verifique!
Em caso de alguma mensagem de erro no terminal, procure interpretar o contexto.
O comando git push é essencial para levantar seus arquivos para o repositório remoto.
A branch incialmente pode ser chamada de main ou master, sempre verifique no git status qual é sua branch (essa é a informação da primeira linha).

## :sparkles: Atualizando o repositório remoto com o atual (pull):
para você atualizar o seu diretório com o repositório remoto dê o comando
```bash
git pull
```
Verifique se no diretório da sua máqiuna constam todos os arquivos que constam no github. 

Para aprender mais sobre os comandos git e o github confira a documentação do GitHub:
https://docs.github.com/pt




