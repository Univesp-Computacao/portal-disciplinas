# Perguntas e Respostas

## O que é Git? 
Git é um software Open Source criado por Linus Torvalds que funciona como um sistema de versionamento distribuído moderno, que facilita a vida de qualquer pessoa durante a criação e manutenção de projetos comerciais e de código-fonte aberto.

## O que é VCS?
Controle de Versão é um sistema que grava mudanças feitas a um ou mais arquivos e que permite seja feito uma rechamada de versões específicas se for preciso.

## O que é CVCS?
Uma das questões mais importantes da programação é que precisamos de mais pessoas colaborando no mesmo código. Para lidar com isso os sistemas de Controle de Versão Centralizadas foram criados. Estes sistemas tẽm um único servidor com todos os arquivos versionados.

## Segurança no Git como funciona?
O mecanismo que o Git usa é para criptografar e descriptografar é o SHA-1 hash.

## O que SHA1?
SHA-1 hash é uma string de 40 caracteres em hexadeciaml (0-9 e a-f) e é calculado com base no conteúdo do arquivo ou diretório do Git.

## Exemplo de SHA1
Um SHA-1 hash é algo como: 24b9da6552252987aa493b52f8696cd6d3b00373

## Quais são os três estados mais importantes do Git?
Seus arquivos podem ficar em trŝ estágios: committed, modified e staged.

## O que é "comitted" ?
Significa que seus dados foram salvos em sua base de dados local.

## O que é "modified" ?
Significa que teve altrações e elas ainda não foram comitadas.

## O que é "staged" ?
Significa que você tem uma marcação das modificações feitas no arquivo e que elas estão prontas para ir para a próxima versão no próximo commit.

## Como instalar o Git? 
https://git-scm.com

## Como obter um repositório Git? 
Você pode iniciar um diretório local e torná-lo um diretório git, ou, você pode clonar um diretório existente.

## Como iniciar um repositório Git? 
```bash
git init
```

## Qual é o comando par escrever uma mensagem de commit?
```bash
git commit -m "escreva sua mensagem de commit"
```

## Qual a linguagem usada no Git?
O git foi desenvolvido utilizando a linguagem C.

## Qual a diferença entre git pull e git fetch?
git pull faz o download de uma determinada branch remota e atualiza o seu repositório local, git fetch, ele puxa os commits de uma determinada branch e armazena em uma nova branch. Para unificar as versões do projetos é usado o git merge.

## Como checar a diferença entre dois arquivos? 
```bash
diff -u novo_arquivo.html velho_arquivo.html
```
## O que são logs no Git?
Mostra uma lista de recentes commits por ID's (números de identificação únicos de cada commit) 

## O que é git diff ?
Um comando que permite comparar dois commits de ID's diferentes, mostrando a diferença entre eles.

## O que é "detached HEAD state" ?
HEAD é para onde o git está apontando o commit. Git permite que você aponte para versões anteriores. 

## Como branches podem ajudar? 
Branches ajudam principalmente a desenvolver e testar novas funcionalidades sem fazer nenhuma alteração no projeto original .

## O que é remote?
Repositórios remotos são versões de seu projeto que estão hospedadas na internet ou em alguma outra rede.

## O que é git push ?
Faz o upload do conteúdo de um diretório local para um repositório remoto.

## O que é git pull ?
Este comando busca e faz o download de um repositório remoto e imediatamente faz o update do repositório local para combinar com o remoto.

## O que é fork no GitHub?
É uma bifurcação de um projeto que você gerencia ou de outro proprietario, mantendo uma conexão com o projeto original.
![img](https://i.postimg.cc/nzVZTVnT/area.png)


## Como adicionar arquivos na área de staging ? 
```bash
git add [nome_do_arquivo.txt]

#ou

git add . 

#o "." significa adicionar tudo
```

## Como ver as mudanças na área de staging depois do git add ?
```bash
git diff --staged
```

## Se você acidentalmente adicionar um arquivo e quiser removê-lo? 
```bash
git reset [nome_do_arquivo.txt]
```

## O que é Squasing Commits ?
Combinação de vários commits em um único.

## O que é "estrelar"(_starring_) um projeto no GitHub?
É um jeito fácil de você encontrar um repositório de seu interesse. O GitHub faz uma lista dos repositórios que você marcou uma estrela, tornando fácil encontrá-lo depois.

## O que é Pull Request?
Diz aos outros sobre as mudanças que você está empurrando para um repositório. Uma vez enviado, as partes interessadas poderão revisar, discutir, planejar, etc.

## O que significam Issues no GitHub ?
É um rastreador, por exemplo, quando seu projeto cresce, você usará Issues para organizar tarefas, resolver bugs, planejar novas funcionalidades.

## GitHub é gratuito?
Sim, embora ofereça planos empresariais em algumas situações.

## Como checar a versão anterior de um código?
```bash
git checkout [commit_id]
```

## Como inicializar um diretório vazio com Git?
```bash
git init [project-name]
```

## O que é Git Bash?
O Git Bash é o aplicativo para Windows que oferece a camada de emulação para a experiência de linha de comando Git usando o bash.
 
## O que é Git Stash?
É Um jeito de salvar o trabalho para mais tarde, quando você ainda não quer adicionar e fazer o commit.

## O que é "merging" ?
É a unificação dos ramos criados no projeto, por exemplo: main e version2, quando usamos o merge ele unifica os dois na branch escolhida, é comum manter a main como a ramificação principal do projeto. 

## Por que conflitos de merge acontecem?
Estes conflitos acontecem quando o mesmo arquivo é modificado na mesma região por duas pessoas diferentes e comittado em sequência. Esses conflitos necessitam da intervenção humana para informar ao git qual será a nova versão.

## O que é Git Head ? 
É uma referência ao objeto do commit. Por padrão a cabeça vem apontada para a Master/Main.

## O que é Git Origin ? 
É o repositório que dá origem a um repositório clonado.

## O que é Git Branch ?
É algo que faz parte da vida diária do desenvolvimento de softwares. Efetivamente, branches são uma imagem instantânea das suas mudanças derivadas de uma ourta versão.

## Quais são as alternativas ao GitHub ?
GitLab, BitBuckett, SourceForge, GitKraken, LaunchPad, etc...

## Um pouco sobre o GitLab
Muito similar ao GitHub, oferece code reviews, time tracking, issue tracking, integrated project, wiki, continuos integration, automated testing and code delivery.

## Um pouco sobre o BitBuckett
Também muito popular, mas gratuito para equipes de até 5 membros. O BitBuckett trabalha com pipelines, pull requets, smart mirroring, issue tracking, flexible deployment models, IP whitelisting e branch permissions, que permite proteger o trabalho.
