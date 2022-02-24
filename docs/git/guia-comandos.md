# Guia de Comandos

### Como verificar a versão do Git?
```bash
git --version

# o comando retornará a versão do Git instalada na sua máquina.
```

### Como pedir ajuda ao Git?
```bash
git --help

# este comando irá abrir o manual geral do Git.
```

### Escolher o nome que você quer anexar às suas transações de commmit:
```bash
git config --global user.config [digite-seu-nome]
```

### Escolher e-mail que você quer anexar aos seus commits:
```bash
git config --global user.config [exemplo@email.com]
```
### Ativar colorização da linha de comandos :
```bash
git config --global color.ui auto
```
### Criar um novo repositório local:
```bash
git init [project-name]

# craindo um novo repositório em seu diretório local
```

### Fazer o download de um projeto e toda história de versões:
```bash
git clone [url] 

# esse comando baixa todo um repositório com git já inicializado em seu diretório corrente.
# normalmente clonamos um repositório para podermos estudar ou mesmo fazermos alterações.
```

### Listar todos arquivos novos ou modificações  a serem comitadas (status):
```bash
git status

# Boas Práticas: antes de comitar verifique o status do seu git 
```

### Mostrar diferenças entre arquivos que ainda não foram adicionados:
```bash
git diff 
```

### "Capturar" o arquivo em preparação para o versionamento: 
```bash
git add [nome-do-arquivo.html] [outro-arquivo.py] 

# esse comando está adicionando seus arquivos para a área de staging, ou seja, estão sendo preparados para serem comitados.
```
__ou para adicionar todos:__
```bash
git add .  

# o carcter "." representa todos arquivos
```

### Mostrar as diferenças entre arquivos que estão na área de staging e os arquivos da última versão:
```bash
git diff --staged 

# com esse comando enxergamos as modificações que já foram adicionados (comando add) e estão na staging area, ou seja, é a última verificação antes do commit. 
```
### Tirar arquivos da área de staging preservando seu conteúdo:
```bash
git reset [algum-arqivo.html] [outro-arquivo.css] [um-script.js] 

# sempre podemos reavaliar se todas as mudanças estão corretas antes de comitarmos. Esse comando permite retirar um arquivo da staging area sem excluí-lo
```
### Grave todas as alterações realizadas  na história da versão (commit) :
```bash
git commit -m ["sua-mensagem-de-commit"]
```
### Liste todas branches do repositório corrente:
```bash
git branch 
```
### Criar uma nova branch:
```bash
git branch [nomme-da-branch]
```
### Trocar para branch específica e atualizar o diretório de trabalho:
```bash
git checkout [nome-da-branch]
```
### Combinar a história de uma branch específica com a branch atual (merge):
```bash
git merge [branch] 
```
### Deletar uma branch específica:
```bash
git branch -d [nome-da-branch] 

# no caso passamos o argumento "-d" de "delete" para o comando git branch
```
### Deletar os arquivos de um diretório de trabalho e apontar a exclusão no próximo commit:
```bash
git rm [nome 

#chamamos o comando rm que vem do inglês "to remove", remover
```

### Listar história da versão de uma branch:
```bash
git log
```

### Mostrar metadados e o conteúdo de um commit específico
```bash
git show [commit] 
```

### Desfazer todos os commits feitos depois do commit: 
```bash
git reset [commit] 
```
### Guardar temporariamente os arquivos modificados:
```bash
git stash 
```

### Fazer upload do local para o remoto:
```bash
git push [alias] [branch] 
```
### Download de toda a versão atualizada do remoto para o local:
```bash
git pull 
```
### Verificar arquivos ocultos
```bash
ls -a 
```
























