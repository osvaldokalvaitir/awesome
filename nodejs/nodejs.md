# Node.js

Interpretador de código JavaScript com o código aberto, focado em migrar o Javascript do lado do cliente para servidores.

## Instalação

- **Linux usando cURL**

  Acesse o site `https://github.com/nodesource/distributions/blob/master/README.md#deb` que é o redirecionamento do site do Node.js.

  Em `Installation instructions`, encontre a versão do Node.js que deseja instalar e copie as linhas referentes ao Ubuntu ou Debian.

  Para instalar o Node.js no Ubuntu por exemplo, executar no cURL os seguintes comandos, uma linha de cada vez:

  ```
  curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
  sudo apt-get install -y nodejs
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

Verifique se o Node.js está instalado executando:

```
node -v
```

Verifique a versão do NPM executando:

```
npm -v
```

Para atualizar a NPM para a versão mais recente:

```
[sudo] npm install npm -g
```

## Documentação e Instalação

Clique [aqui](https://nodejs.org) para ver a documentação e outras opções de instalação.

## Instalação de Projeto

Depois de instalado o Node.js/Yarn, abra o prompt de comando e dentro da pasta do projeto execute os comandos abaixo.

Instalar as dependências do projeto:

```
npm install | yarn
```

## Execução de Projeto para Desenvolvimento no Node.js

Executar o projeto para desenvolvimento (incluindo Nodemon ou webpack-dev-server):

```
npm dev | yarn dev
```

## Execução de Projeto para Produção no Node.js

Executar o projeto para produção:

```
npm start | yarn start
```

## Execução de Testes de Projeto no Node.js

Executar testes no projeto localmente:

```
npm test | yarn test
```