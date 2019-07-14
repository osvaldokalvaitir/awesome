# Git

É um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. O Git foi inicialmente projetado e desenvolvido por Linus Torvalds para o desenvolvimento do kernel Linux, mas foi adotado por muitos outros projetos.

## Documentação

Clique [aqui](https://git-scm.com/book/pt-br/v2) para ver a documentação e [aqui](rogerdudler.github.io/git-guide) para ver um guia prático.

## Instalação

Clique [aqui](https://git-scm.com) para fazer a instalação.

Para instalar execute o arquivo de instalação e use as seguintes configurações:

Choosing the default editor used by Git  
<sub> Which editor would you like git to use? **Use Visual Studio Code as Git's default editor** </sub>

Adjusting your PATH environment  
<sub> How would you like to use Git from the command line? **Git from the command line and also from 3rd-party software** </sub>

Choosing HTTPS transport backend  
<sub> Which SSL/TLS library would you like Git to use for HTTPS connections? **Use the Open SSL library** </sub>

Configuring the line ending conversions  
<sub> How should Git treat line endings in text files? **Checkout Windows-style, commit Unix-style line endings** </sub>

Configuring the terminal emulator to use with Git Bash  
<sub> Which terminal emulator do you to use with your Git Bash? **Use Windows' default console window** </sub>

Configuring extra options  
<sub> Which features would you like to enable?  
**- [x] Enable file system caching**  
**- [x] Enable Git Credential Manager**  
**- [ ] Enable symbolic links**  
</sub>

## Comandos

### Autenticação

Depois de instalado o Git, executar os seguintes comandos para fazer a autenticação.

Listar todas as configurações existentes:

```
git config --list | git config --l
```

Configurar o nome:

```
git config --global user.name "Nome Completo"
```

Configurar o email:

```
git config --global user.email joao@exemplo.com
```

A primeira vez que comitar, irá pedir e-mail e senha do GitHub para autenticar.

### Repositórios

Criar um novo repositório:

```
git init
```

Clonar um repositório:

```
git clone /caminho/do/repositorio
```

Clonar um repositório alterando seu nome:

```
git clone /caminho/do/repositorio novo-nome-repositorio
```

### Adicionar e Comitar

Adicionar um arquivo alterado no stage:

```
git add nome_arquivo
```

Adicionar todos os arquivos alterados no stage:

```
git add . | git add *
```

Visualizar o status dos arquivos alterados:

```
git status
```

Comitar os arquivos alterados do stage:

```
git commit -m "Descricao do commit"
```

### Enviando as Alterações

Enviar os arquivos comitados para o repositório remoto:

```
git push origin master
```

Obs: `origin` é o caminho do repositório remoto e o `master` é o nome da branch.

Se você não clonou um repositório existente e deseja conectar seu repositório à um repositório remoto, é necessário incluí-lo:

```
git remote add origin /caminho/do/repositorio
```

Agora você pode realizar o `push` enviando as alterações para o servidor remoto selecionado.

Obs: Pode acontecer que um usuário tenha enviado algum commit para o repositório remoto e você ao realizar um `push` ocorrerá um erro, neste caso é necessário executar um `pull` antes de realizar um `push`.

### Link do repositório

Visualizar todos os links remotos:

```
git remote
```

Visualizar todos os links remotos com o caminho:

```
git remote -v
```

### Atualizar o repositório local

Atualizar o repositório local com os novos commits remotos:

```
git pull origin master | git pull
```

Se tiver algum conflito de arquivo, você terá que resolver esses conflitos manualmente.

### Branches

Visualizar todas as branches:

```
git branch
```

Criar nova branch:

```
git branch nome_branch
```

Criar nova branch e entrar nela:

```
git checkout -b nome_branch
```

Criar a branch no repositório remoto:

```
git push --set-upstream origin nome_branch
```

Puxar uma branch que está no repositório remoto:

```
git checkout nome_branch
```

Executando push da branch para o repositório remoto:

```
git push origin nome_branch
```

Puxar uma branch criada por outro usuário e que esteja no repositório remoto:

```
git checkout –track origin/nome_branch
```

Voltar para a branch anterior:

```
git checkout -
```

Para remover uma branch, ir para a branch `master` e executar o comando:

```
git checkout -D nome_branch
```

Remover uma branch do repositório remoto:

```
git push --delete origin nome_branch
```

### Tags

As tags não ficam dentro de nenhuma branch.

Listar as tags existentes:

```
git tag
```

Criar uma tag:

```
git tag v1.0.0
```

Entrar na tag:

```
git checkout v1.0.0
```

Publicar as tags no repositório remoto:

```
git push origin master --tags
```

Apagar tag localmente:

```
git tag -d v1.0.0
```

Apagar tag no repositório remoto:

```
git push origin :refs/tags/versao-tag
```

### Logs

Visualizar o histórico do repositório:

```
git log
```

### Rebase

Para alterar o texto dos commits usando o rebase:

```
git rebase -i HEAD~<numero_commits>
```

Onde:

- `<numero_commits>` - número de commits que será exibido na lista do seu editor de texto padrão para editá-los. Ex: `3` aparecerá os 3 últimos commits.

A lista será semelhante à seguinte:

```
pick e499d89 Delete CNAME
pick 0c39034 Better README
pick f7fde4a Change the commit message but push the same commit.
```

Substitua `pick` por `reword` antes de cada mensagem de commit que você deseja alterar.

```
pick e499d89 Delete CNAME
reword 0c39034 Better README
reword f7fde4a Change the commit message but push the same commit.
```

Salve e feche o arquivo.  

Em cada arquivo de commit, digite a nova mensagem de commit, salve o arquivo e feche-o.  

Depois de terminado todos os arquivos, execute o comando para subir os commits alterados:

```
git push --force
```