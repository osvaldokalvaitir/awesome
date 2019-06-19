# Firebase CLI

A interface de linha de comando (CLI) das ferramentas do Firebase.

## Documentação

Clique [aqui](https://github.com/firebase/firebase-tools) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/firebase-tools) para fazer a instalação.

Instalar globalmente:

```
npm install --global firebase-tools | yarn global add firebase-tools
```

## Comandos do CLI

Para fazer o login:

```
firebase login
```

Aparecerá a seguinte pergunta:

<sub>? Allow Firebase to collect anonymous CLI usage and error reporting information? (Y/n) **n** </sub>

Abrirá no browser a janela para fazer o login com o Google e permitir que o app `Firebase CLI` acesse a conta do Google.

Para iniciar o Firebase:

```
firebase init
```

Aparecerá a seguinte pergunta:

<sub> Are you ready to proceed? (Y/n) **Y** </sub>

<sub> Which Firebase CLI features do you want to set up for this folder? Press Space to select features, then Enter to confirm your choices. **Hosting: Configure and deploy Firebase Hosting sites** </sub>

<sub> Select a default Firebase project for this directory: **Selecione o projeto desejado** </sub>

<sub> What do you want to use as your public directory? (public) **build** </sub>

<sub> Configure as a single-page app (rewrite all urls to /index.html)? (y/N) **N** </sub>

Para fazer o deploy:

```
firebase deploy
```