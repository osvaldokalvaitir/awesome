# Node.js

Interpretador de código JavaScript com o código aberto, focado em migrar o Javascript do lado do cliente para servidores.

## Instalação

- **Linux usando cURL**

  Para instalar o Node.js, executar no cURL os seguintes comandos:

  ```
  curl -sL https://deb.nodesource.com/setup_10.x | sudo bash -
  sudo apt install nodejs
  ```

  `Caso você não esteja em distribuições Debian/Ubuntu, siga os passos para instalação de acordo com seu sistema: https://nodejs.org/en/download/package-manager`

- **OS X usando Homebrew**

  Para instalar o Node.js, executar no Homebrew o seguinte comando:

  ```
  brew install node
  ```

- **Windows usando Chocolatey**

  Para instalar o Node.js, executar no Chocolatey o seguinte comando:

  ```
  choco install -y nodejs.install
  ```

## Documentação e Instalação

Clique [aqui](https://nodejs.org) para ver a documentação e outras opções de instalação.

## Instalação de Projeto

Depois de instalado o Node.js/Yarn, abra o prompt de comando e dentro da pasta do projeto execute os comandos abaixo.

Instalar as dependências do projeto:

```
npm install | yarn
```

## Execução de Projeto no Node.js

Executar o projeto Node.js localmente:

```
npm start | yarn start
```

## Execução de Projeto para Desenvolvimento no Node.js

Executar o projeto para desenvolvimento (incluindo Nodemon) Node.js localmente:

```
npm dev | yarn dev
```

## Execução de Testes de Projeto no Node.js

Executar testes no projeto Node.js localmente:

```
npm test | yarn test
```
