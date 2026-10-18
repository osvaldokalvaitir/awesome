# Git

É um sistema de controle de versões distribuído, usado principalmente no desenvolvimento de software, mas pode ser usado para registrar o histórico de edições de qualquer tipo de arquivo. O Git foi inicialmente projetado e desenvolvido por Linus Torvalds para o desenvolvimento do kernel Linux, mas foi adotado por muitos outros projetos.

## Documentação

Clique [aqui](https://git-scm.com/book/pt-br/v2) para ver a documentação e [aqui](https://rogerdudler.github.io/git-guide) para ver um guia prático.

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

Configuring experimental options 
<sub> Which bleeding -edge features would you like to enable? 
**- [ ] Enable experimental, built-in add -i/-p**  
</sub>

## Comandos

### Autenticação

Depois de instalado o Git, executar os seguintes comandos para fazer a autenticação.

Listar todas as configurações existentes:

```
git config --list | git config -l
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

Escolher interativamente quais trechos de um arquivo vão para o stage:

```
git add -p nome_arquivo
```

Visualizar o status dos arquivos alterados:

```
git status
```

Comitar os arquivos alterados do stage:

```
git commit -m "Descricao do commit"
```

Remover um arquivo do repositório e do disco:

```
git rm nome_arquivo
```

Parar de rastrear um arquivo, mantendo-o no disco (útil para arquivos que deveriam estar no `.gitignore`):

```
git rm --cached nome_arquivo
```

Renomear ou mover um arquivo:

```
git mv nome_antigo nome_novo
```

### Enviando as Alterações

Enviar os arquivos comitados para o repositório remoto:

```
git push origin main
```

Obs: `origin` é o caminho do repositório remoto e o `main` é o nome da branch.

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

Baixar os novos commits e branches do repositório remoto, sem alterar os seus arquivos:

```
git fetch
```

Baixar e remover as referências de branches que já foram apagadas no repositório remoto:

```
git fetch --prune
```

Atualizar o repositório local com os novos commits remotos (equivale a um `fetch` seguido de um `merge`):

```
git pull origin main | git pull
```

Atualizar o repositório local aplicando os seus commits por cima dos commits remotos, evitando commits de merge:

```
git pull --rebase
```

Se tiver algum conflito de arquivo, você terá que resolver esses conflitos manualmente.

### Branches

Visualizar todas as branches:

```
git branch
```

Visualizar todas as branches, incluindo as remotas:

```
git branch -a
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
git checkout --track origin/nome_branch
```

Voltar para a branch anterior:

```
git checkout -
```

Renomear a branch atual:

```
git branch -m novo_nome_branch
```

Para remover uma branch, ir para a branch `main` e executar o comando:

```
git branch -d nome_branch
```

Obs: O `-d` só remove a branch se ela já tiver sido incorporada (merge). Para forçar a remoção, use `-D`.

Remover uma branch do repositório remoto:

```
git push --delete origin nome_branch
```

### Switch

O `git switch` é o comando mais novo e recomendado para trocar de branch. Ele faz a mesma coisa que o `git checkout` faz com branches, mas sem misturar com a função de restaurar arquivos.

Entrar em uma branch existente:

```
git switch nome_branch
```

Criar nova branch e entrar nela:

```
git switch -c nome_branch
```

Entrar em uma branch que está no repositório remoto (cria a branch local rastreando a remota):

```
git switch nome_branch
```

Voltar para a branch anterior:

```
git switch -
```

Descartar as alterações locais e trocar de branch:

```
git switch --discard-changes nome_branch
```

### Merge

Incorporar as alterações de uma branch na branch atual:

```
git merge nome_branch
```

Incorporar sempre criando um commit de merge, mesmo quando é possível avançar a branch diretamente (fast-forward):

```
git merge --no-ff nome_branch
```

Juntar todos os commits da branch em um único conjunto de alterações no stage, para fazer um único commit:

```
git merge --squash nome_branch
```

Cancelar um merge que deu conflito e voltar ao estado anterior:

```
git merge --abort
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

Criar uma tag anotada, com mensagem, autor e data (recomendado para versões):

```
git tag -a v1.0.0 -m "Versão 1.0.0"
```

Entrar na tag:

```
git checkout v1.0.0
```

Publicar as tags no repositório remoto:

```
git push origin main --tags
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

Visualizar o histórico resumido, com um commit por linha:

```
git log --oneline
```

Visualizar o histórico em forma de gráfico, com todas as branches:

```
git log --oneline --graph --all
```

Visualizar o histórico de um arquivo, com as alterações de cada commit:

```
git log -p nome_arquivo
```

Visualizar os detalhes e as alterações de um commit:

```
git show <hash>
```

### Diferenças

Visualizar as alterações que ainda não estão no stage:

```
git diff
```

Visualizar as alterações que já estão no stage:

```
git diff --staged
```

Comparar duas branches:

```
git diff main..nome_branch
```

### Blame

Visualizar quem alterou cada linha de um arquivo, em qual commit e quando:

```
git blame nome_arquivo
```

Visualizar apenas um intervalo de linhas:

```
git blame -L 10,20 nome_arquivo
```

Ignorar alterações de espaços em branco e detectar linhas movidas ou copiadas de outros arquivos:

```
git blame -w -C nome_arquivo
```

Obs: Depois de encontrar o commit, use `git show <hash>` para ver a alteração completa.

### Alterando commits realizados

Para visualizar os últimos commits:

```
git log
```

Se foi realizado commit mas ainda não enviou para o GitHub, é possível realizar os comandos abaixos:  

Remover todas as alterações realizadas:

```
git reset --hard
```

ou 

```
git reset --hard HEAD
```

Devolver os commits realizados para o stagging:

```
git reset --soft <hash>
```

Desfazer os commits mantendo as alterações nos arquivos, mas fora do stage:

```
git reset <hash>
```

Para mudar o último commit, a mensagem do commit ou mudar o snapshot que acabou de salvar, adicionando, alterando e removendo arquivos:

```
git commit --amend
```

Isso abre seu editor de texto, com sua última mensagem de commit nele, pronto para você modificar a mensagem. Quando você salva e fecha o editor, ele salva um novo commit contendo essa mensagem e fazendo esse seu novo commit o mais recente.  

Se você fez o commit e quer alterar o snapshot adicionando ou modificando arquivos, o processo funciona basicamente da mesma maneira. Você adiciona as alterações que deseja na área de stagging editando um arquivo e executando `git add` nele ou `git rm` em um arquivo rastreado, e depois `git commit --amend` pega sua área de stagging atual e faz o snapshot para o novo commit.

Se o commit já foi enviado para o repositório remoto, o mais seguro é desfazê-lo com um novo commit que reverte as alterações, sem reescrever o histórico:

```
git revert <hash>
```

### Restore

O `git restore` é o comando mais novo e recomendado para descartar alterações em arquivos.

Descartar as alterações de um arquivo que ainda não está no stage:

```
git restore nome_arquivo
```

Tirar um arquivo do stage, mantendo as alterações:

```
git restore --staged nome_arquivo
```

Restaurar um arquivo como ele estava em um commit específico:

```
git restore --source <hash> nome_arquivo
```

### Reflog

O reflog guarda o histórico de tudo o que o `HEAD` fez (commits, resets, rebases, trocas de branch), mesmo o que não aparece mais no `git log`. Ele é a forma de recuperar commits perdidos depois de um `reset --hard` ou de um rebase errado.

Visualizar o histórico do `HEAD`:

```
git reflog
```

Voltar para um estado anterior encontrado no reflog:

```
git reset --hard HEAD@{2}
```

### Rebase

O rebase reaplica os commits da sua branch por cima de outra branch, deixando o histórico linear, como se a branch tivesse sido criada a partir do ponto mais recente. Diferente do `merge`, ele reescreve os commits (os hashes mudam).

Atualizar a branch atual com os commits mais recentes da `main`:

```
git switch nome_branch
git rebase main
```

Se tiver algum conflito, resolva os arquivos, adicione no stage e continue o rebase:

```
git add nome_arquivo
git rebase --continue
```

Pular o commit que está com conflito:

```
git rebase --skip
```

Cancelar o rebase e voltar ao estado anterior:

```
git rebase --abort
```

Obs: Nunca faça rebase de commits que já estão em uma branch compartilhada com outras pessoas (ex: `main`), pois isso reescreve o histórico delas.

#### Rebase interativo

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

Outras opções que podem ser usadas no lugar do `pick`:

- `squash` ou `s` - junta o commit com o anterior, permitindo editar a mensagem.
- `fixup` ou `f` - junta o commit com o anterior, descartando a mensagem dele.
- `edit` ou `e` - pausa o rebase nesse commit para alterar os arquivos.
- `drop` ou `d` - remove o commit.

Também é possível mudar a ordem das linhas para reordenar os commits.

Depois de terminado todos os arquivos, execute o comando para subir os commits alterados:

```
git push --force
```

Ou, de forma mais segura, que só sobrescreve se ninguém tiver enviado novos commits para a branch remota:

```
git push --force-with-lease
```

### Cherry-pick

O cherry-pick copia um commit específico de outra branch e aplica na branch atual, criando um novo commit. É útil para levar uma correção para outra branch sem fazer merge de tudo.

Aplicar um commit na branch atual:

```
git cherry-pick <hash>
```

Aplicar vários commits:

```
git cherry-pick <hash1> <hash2>
```

Aplicar um intervalo de commits (do `hash_inicial`, sem incluí-lo, até o `hash_final`):

```
git cherry-pick <hash_inicial>..<hash_final>
```

Aplicar as alterações no stage, sem criar o commit:

```
git cherry-pick -n <hash>
```

Se tiver algum conflito, resolva os arquivos, adicione no stage e continue, ou cancele:

```
git cherry-pick --continue
git cherry-pick --abort
```

### Pull request

Para fazer o pull request entre na branch de desenvolvimento (ex. feature):

```
git checkout feature/courses-page

```

Faça o push de dentro da branch:

```
git push origin feature/courses-page
```

Aparecerá uma nova branch no GitHub, clique em `Compare & pull request` para abrir uma pull request.  

Na tela `Open a pull request` é possível adicionar comentários e visualizar os commits feitos, depois é só clicar em `Create pull request`.

O código ainda não foi incorporado para o main, nesta etapa é possível em `Reviewers`, adicionar usuários para revisar o código.

Para incorporar o pull request para o main, clique no botão `Merge pull request`.

No GitHub, depois que a branch for aceita fazendo o merge, aparecerá um botão chamado `delete branch`, sempre delete a branch para o repositório ficar somente com uma branch.

### Stash

Guardar no stash todos os arquivos alterados:

```
git stash
```

Guardar no stash com uma mensagem para identificar depois:

```
git stash push -m "Descricao do stash"
```

Guardar no stash todos os arquivos alterados incluindo os arquivos novos e os que não estão rastreados:

```
git stash -u | git stash --include-untracked
```

Guardar no stash todos os arquivos alterados incluindo os arquivos ignorados:

```
git stash -a | git stash --all
```

Lista todos os stashes:

```
git stash list
```

Voltar os arquivos alterados do último stash, podendo ocorrer merge se o mesmo arquivo for alterado:

```
git stash pop
```

ou

```
git stash apply
```

Voltar os arquivos alterados de um stash mais antigo, podendo ocorrer merge se o mesmo arquivo for alterado:

```
git stash apply <stash@{2}>
```

Apagar um stash:

```
git stash drop <stash@{2}>
```

Apagar todos os stashes:

```
git stash clear
```

### Worktree

O worktree permite ter várias branches do mesmo repositório abertas ao mesmo tempo, cada uma em uma pasta diferente. É útil para revisar um pull request ou corrigir um bug urgente sem precisar fazer stash do que está em andamento, e para rodar agentes de inteligência artificial em paralelo.

Criar uma pasta com uma branch existente:

```
git worktree add ../nome_pasta nome_branch
```

Criar uma pasta com uma nova branch:

```
git worktree add -b nome_branch ../nome_pasta
```

Listar os worktrees:

```
git worktree list
```

Remover um worktree:

```
git worktree remove ../nome_pasta
```

Limpar as referências de worktrees cujas pastas foram apagadas manualmente:

```
git worktree prune
```

Obs: A mesma branch não pode estar aberta em dois worktrees ao mesmo tempo.

### Bisect

O bisect faz uma busca binária no histórico para encontrar o commit que introduziu um bug.

Iniciar a busca, marcando o commit atual como ruim e um commit antigo como bom:

```
git bisect start
git bisect bad
git bisect good <hash>
```

O Git vai para um commit no meio do caminho. Teste e marque como bom ou ruim, repetindo até ele mostrar o commit que causou o problema:

```
git bisect good
git bisect bad
```

Finalizar e voltar para a branch original:

```
git bisect reset
```

### Limpar arquivos não rastreados

Visualizar quais arquivos não rastreados serão removidos:

```
git clean -n
```

Remover os arquivos e pastas não rastreados:

```
git clean -fd
```

### Duplicar um repositório

Faça um clone com bare do antigo repositório:

```
git clone --bare <https://github.com/usuario/antigo_repositorio.git>
```

Entre no repositório clonado:

```
cd <antigo_repositorio.git>
```

Faça um push com mirror no novo repositório:

```
git push --mirror <https://github.com/usuario/novo_repositorio.git>
```

Volte na pasta anterior:

```
cd ..
```

Remova a pasta do antigo repositório:

```
rm -rf <antigo_repositorio.git>
```

## Fluxos de Trabalho

O fluxo de trabalho (branching strategy) define como a equipe cria, nomeia e incorpora as branches. Os mais usados são o Git Flow, o GitHub Flow e o Trunk-Based Development.

### Git Flow

Modelo com branches de longa duração e branches de apoio com papéis bem definidos. Indicado para projetos com versões planejadas (ex: aplicativos mobile, bibliotecas) e que precisam manter mais de uma versão em produção.

- `main` - código em produção. Cada commit é uma versão, marcada com uma tag.
- `develop` - integração das funcionalidades da próxima versão.
- `feature/*` - novas funcionalidades. Saem da `develop` e voltam para a `develop`.
- `release/*` - preparação de uma nova versão (ajustes finais e número da versão). Sai da `develop` e vai para a `main` e para a `develop`.
- `hotfix/*` - correções urgentes em produção. Sai da `main` e vai para a `main` e para a `develop`.

Exemplo de uma feature sem extensão:

```
git switch develop
git switch -c feature/courses-page
git switch develop
git merge --no-ff feature/courses-page
```

Também existe a extensão git-flow, que automatiza a criação e o merge dessas branches:

```
git flow init
git flow feature start courses-page
git flow feature finish courses-page
git flow release start 1.0.0
git flow release finish 1.0.0
git flow hotfix start 1.0.1
git flow hotfix finish 1.0.1
```

Clique [aqui](https://nvie.com/posts/a-successful-git-branching-model) para ver o artigo original do Git Flow e [aqui](https://github.com/petervanderdoes/gitflow-avh) para fazer a instalação da extensão.

### GitHub Flow

Versão simplificada, com apenas a `main` e branches curtas. Cada alteração é feita em uma branch, enviada em um pull request, revisada e incorporada na `main`, que está sempre pronta para o deploy.

Clique [aqui](https://docs.github.com/pt/get-started/using-github/github-flow) para ver a documentação.

### Trunk-Based Development

Todos os desenvolvedores integram o código em uma única branch principal (o trunk, normalmente a `main`) várias vezes ao dia, diretamente ou por branches de vida muito curta (horas ou poucos dias). A `main` precisa estar sempre estável, por isso o fluxo depende de testes automatizados e CI/CD.

- Branches pequenas e curtas, com pull requests rápidos de revisar.
- Funcionalidades incompletas ficam escondidas com feature flags (ex: [ConfigCat](../feature-flags/configcat.md)) em vez de ficarem em branches longas.
- Manter a branch atualizada com `git pull --rebase` ou `git rebase main` para evitar conflitos grandes.
- As versões são geradas a partir da `main` com tags ou, quando necessário, com branches de release.

Indicado para times com integração e entrega contínuas, pois reduz conflitos de merge e acelera o feedback.

Clique [aqui](https://trunkbaseddevelopment.com) para ver a documentação.

## Boas práticas

A linguagem dos commits e das branchs devem ser escolhidas pela equipe (ex: português ou inglês) e este padrão deve ser mantido em todo o projeto.  

Sempre é bom fazer uma branch quando for alterar o código na branch main.  

Sempre que estiver trabalhando em equipe é bom fazer um pull request, pois se precisar voltar atrás é só excluir o pull request do que os vários commits realizados.

No nome do commit sempre é bom pensar "se eu usar este commit, ele", aí vem a mensagem que dever ser colocada no commit como "Altera o retorno da variável" ou "Adiciona a página de cursos".  

É uma boa prática usar um fluxo de trabalho, como os da seção [Fluxos de Trabalho](#fluxos-de-trabalho).  

Usando o flow, o nome da branch poderia ser:

```
git checkout -b feature/courses-page
```

Usando o flow, o nome do commit poderia ser:

```
git commit -m "chore: Commit inicial"
```
