# Yarn

Gerenciamento de dependências rápido, confiável e seguro.

## Instalação

- **Linux usando APT**

  É necessário adicionar os repositórios na lista de busca do apt:

  ```
  curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
  echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
  ```

  Para atualizar:

  ```
  sudo apt-get update && sudo apt-get install yarn
  ```

  Para instalar o Yarn sem o Node.js, executar os seguintes comandos:

  ```
  sudo apt-get install --no-install-recommends yarn
  ```

- **Linux usando cURL (_DESCONTINUADO_)**

  Para instalar o Yarn, executar no cURL os seguintes comandos:

  ```
  curl -o- -L https://yarnpkg.com/install.sh | bash
  ```

- **OS X usando Homebrew**

  Para instalar o Yarn sem o Node.js, executar no Homebrew o seguinte comando:

  ```
  brew install yarn --without-node
  ```

- **Windows usando Chocolatey**

  Para instalar o Yarn, executar no Chocolatey o seguinte comando:

  ```
  choco install yarn
  ```

  Antes de instalar, irá aparecer a seguinte mensagem:

  ```
  Do you want to run the script?([Y]es/[N]o/[P]rint):
  ```

  Digite o `Y` para iniciar a instalação.

Verifique se o Yarn está instalado executando:

```
yarn -v
```  

## Documentação e Instalação

Clique [aqui](https://yarnpkg.com) para ver a documentação e outras opções de instalação.