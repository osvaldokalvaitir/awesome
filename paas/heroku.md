# Heroku

O Heroku é uma plataforma como serviço na nuvem que suporta várias linguagens de programação.  

*Obs: A versão gratuita não é indicada para produção, é indicado a versão paga para a produção.*

## Documentação e Acesso ao Serviço

Clique [aqui](https://www.heroku.com) para ver a documentação e acessar o serviço.

## Criar app

### Projeto Node.js

Para criar um app no Heroku, siga os seguintes procedimentos:

- Antes de enviar o projeto para o Heroku, é necessário criar um arquivo de nome `Procfile` na raíz do projeto com o seguinte código:

  ```
  web: node ./src/index.js
  ```
  ou, se o comando acima estiver em um script, ex: `start`, pode ser usado:
  ```
  web: npm start
  ```
  ou, se quiser usar o yarn, mas precisa verificar se tem o yarn instalado no servidor:
  ```
  web: yarn start
  ```

- Acesse o site do Heroku

- Crie uma conta

- No `Dashboard`, clique em `New` e `Create new app`

- Dê um nome e crie o app

- Na aba `Deploy`:

  - Em `Deployment method`, selecione o `GitHub` e faça o login

  - Em `App connected to GitHub`, digite o repositório para procurar e conecte nele

  - Em `Automatic deploys`, é possível alterar a branch para o deploy

- Na aba `Settings`:

  - Em `Config Vars`, clique em `Reveal Config Vars`

  - Configure as variáveis de ambiente passando chave e valor. Ex: Mongodb, e-mail e outros

  - Configure também a variável de chave `PORT` e valor `80` (verificar se é necessário)

- Na aba `Deploy`:

  - Em `Manual deploy`, clique em `Deploy Branch`

  - Depois de terminar a build, clique no botão `View` que aparecerá e copie a url

  - Em `Automatic deploys`, clique em `Enable Automatic Deploys` (este botão realiza somente o deploy, não realiza a integração contínua).

É possível substituir o nome estranho da url por um domínio próprio, mas tem que ter o plano pago do Heroku, caso tenha, siga os seguintes procedimentos:

- Na aba `Settings`, em `Domains and certificates`, clique em `Add domain`

- Digite o nome do domínio e clique em `Save changes`.

### Projeto ReactJS com Create React App 

#### Deploy com Heroku CLI

Para criar um app no Heroku, siga os seguintes procedimentos:

- Antes de enviar o projeto para o Heroku, é necessário criar um arquivo de nome `static.json` na raíz do projeto com o seguinte código:

  ```
  {
    "root": "build/",
    "routes": {
      "/**": "index.html"
    }
  }
  ```

- Acesse o site do Heroku

- Crie uma conta

- É necessário ter o Git configurado no projeto. Para instalar o [Git](../version-control/git.md), siga `Instalação`, e depois de instalado, é só dar um `git init` na pasta do projeto

- Instale a biblioteca [Heroku CLI](../nodejs/libs/heroku.md) no projeto, siga `Instalação` e `Comandos do CLI`, para instalar, fazer o login, criar um app no Heroku, abrir o app no navegador, enviar o projeto para o Heroku e configurar variáveis de ambiente

- Uma outra maneira de configurar as variáveis de ambiente, é entrar no site do Heroku e na aba `Settings`:

  - Em `Config Vars`, clique em `Reveal Config Vars`

  - Configure as variáveis de ambiente passando chave e valor.

#### Deploy com GitHub

Para criar um app no Heroku, siga os seguintes procedimentos:

- Acesse o site do Heroku

- Crie uma conta

- No `Dashboard`, clique em `New` e `Create new app`

- Dê um nome e crie o app

- Na aba `Deploy`:

  - Em `Deployment method`, selecione o `GitHub` e faça o login

  - Em `App connected to GitHub`, digite o repositório para procurar e conecte nele

  - Em `Automatic deploys`, é possível alterar a branch para o deploy

- Na aba `Settings`:

  - Em `Config Vars`, clique em `Reveal Config Vars`

  - Configure as variáveis de ambiente passando chave e valor

  - Configure também a variável de chave `PORT` e valor `80` (verificar se é necessário)

  - Em `Buildpacks`, clique em `Add buildpack`

  - Na janela `Add buildpack`:

    - Em `Enter Buildpack URL`, digite `mars/create-react-app`

    - Clique em `Save changes`

    - Obs: Adicionando uma buildpack não precisa colocar o `Procfile` e outras configurações

- Na aba `Deploy`:

  - Em `Manual deploy`, clique em `Deploy Branch`

  - Depois de terminar a build, clique no botão `View` que aparecerá e copie a url

  - Em `Automatic deploys`, clique em `Enable Automatic Deploys` (este botão realiza somente o deploy, não realiza a integração contínua).

É possível substituir o nome estranho da url por um domínio próprio, mas tem que ter o plano pago do Heroku, caso tenha, siga os seguintes procedimentos:

- Na aba `Settings`, em `Domains and certificates`, clique em `Add domain`

- Digite o nome do domínio e clique em `Save changes`.