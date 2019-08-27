# Node.js

Interpretador de código JavaScript com o código aberto, focado em migrar o Javascript do lado do cliente para servidores.

## Instalação

- **Linux e Mac (Unix) usando cURL/Wget e NVM**

  Acesse o site `https://github.com/nvm-sh/nvm` e siga `Installation and Update > Install & Update script`, realizando os seguintes procedimentos:

  Para instalar o NVM pelo cURL:

  ```
  curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
  ```

  ou

  Para instalar o NVM pelo Wget (já vem por padrão no sistema Unix):

  ```
  wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash
  ```

  É necessário adicionar algumas linhas no arquivo de configuração do terminal, para encontrar este arquivo depende do terminal, mas normalmente ele se encontra em alguma das pastas abaixo: ~/.bash_profile, ~/.zshrc, ~/.profile, ou ~/.bashrc.

  Para abrir o arquivo:

  ```
  vim ~/.zshrc
  ```

  Adicionar as linhas abaixo em qualquer lugar do arquivo:

  ```
  export NVM_DIR="${XDG_CONFIG_HOME/:-$HOME/.}nvm"
  [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
  ```

  Dê um `source` no arquivo para o terminal ler as alterações do arquivo:

  ```
  source ~/.zshrc
  ```

  Verifique o help do NPM:

  ```
  nvm -h
  ```

  Para instalar o Node.js:

  ```
  nvm install <versao_nodejs>
  ```

  Para configurar como padrão esta versão do Node.js:

  ```
  nvm alias default <versao_nodejs>
  ```

  Onde:

  - `<versao_nodejs>` - versão do Node.js. Ex: `10.15.3`

- **Linux usando cURL (_DESCONTINUADO_)**

  Acesse o site `https://github.com/nodesource/distributions/blob/master/README.md#deb` que é o redirecionamento do site do Node.js.

  Em `Installation instructions`, encontre a versão do Node.js que deseja instalar e copie as linhas referentes ao Ubuntu ou Debian.

  Para instalar o Node.js no Ubuntu por exemplo, executar no cURL os seguintes comandos, uma linha de cada vez:

  ```
  curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
  sudo apt-get install -y nodejs
  ```

  `Caso você não esteja em distribuições Debian/Ubuntu, siga os passos para instalação de acordo com seu sistema: https://nodejs.org/en/download/package-manager`

- **OS X usando Homebrew (_DESCONTINUADO_)**

  Para instalar o Node.js, executar no Homebrew o seguinte comando:

  ```
  brew install node
  ```

- **Windows usando Chocolatey**

  Para instalar o Node.js, executar no Chocolatey o seguinte comando:

  ```
  cinst nodejs
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

Executar o projeto para desenvolvimento (incluindo Nodemon):

```
npm dev | yarn dev
```

## Execução de Projeto para Produção no Node.js

Executar o projeto para produção:

```
npm start | yarn start
```

## Execução de Testes de Projeto no Node.js

Executar testes no projeto:

```
npm test | yarn test
```
