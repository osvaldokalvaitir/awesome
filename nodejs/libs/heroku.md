# Heroku CLI

O Heroku CLI é usado para gerenciar aplicativos Heroku a partir da linha de comando. É construído usando oclif.

## Documentação

Clique [aqui](https://github.com/heroku/cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/heroku) para fazer a instalação.

Instalar globalmente:

```
npm install --global heroku | yarn global add heroku
```

## Comandos do CLI

Para fazer o login com as credenciais do site Heroku:

```
heroku login
```

Em projeto criado com [Create React App](../nodejs/libs/create-react-app.md) e usando [Git](../version-control/git.md) tem uma configuração pronta para fazer deploy no Heroku.

Entre no GitHub [Heroku Buildpack for create-react-app](https://github.com/mars/create-react-app-buildpack#user-content-generate-a-react-app) e siga o procedimento do tópico `Create the Heroku app`. Ex: `heroku create <nome_do_app> --buildpack mars/create-react-app`

Obs: Ao executar o comando `git remote`, pode observar que automaticamente ele criou um link com o nome `heroku`.

Para abrir o app no navegador quando terminar a criação:

```
heroku open
```

Para enviar o projeto para o Heroku, depois do commit, dar o push no link do heroku:

```
git push heroku master
```

Para configurar as variáveis ambiente:

```
heroku config:set <nome_da_variavel>=<valor_da_variavel>
```

Ex: `heroku config:set REACT_APP_API_URL=https://api.github.com`