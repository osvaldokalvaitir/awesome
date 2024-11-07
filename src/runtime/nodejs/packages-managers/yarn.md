# Yarn

Gerenciamento de dependências rápido, confiável e seguro.

## Documentação e Instalação

Clique [aqui](https://yarnpkg.com) para ver a documentação e outras opções de instalação.

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

## Comandos

### Básicos

Verificar a versão do Yarn:

```
yarn -v
```

Para atualizar o Yarn para a versão mais recente:

```
yarn set version latest
```

Para desinstalar o Yarn:

```
npm uninstall -g yarn
```

Verificar a versão de um pacote:

```
yarn info <nome_pacote> version
```

Verificar os pacotes instalados:

```
yarn list
```

Verificar os pacotes instalados globalmente:

```
yarn list -g
```

Verificar os pacotes desatualizados:

```
yarn outdated
```

Verificar os pacotes desatualizados globalmente:

```
yarn outdated -g
```

Verificar os scripts disponíveis:

```
yarn run
```

Executar um script:

```
yarn run <nome_script>
```

### Instalação de Pacotes

Instalar as dependências do projeto:

```
yarn install
```

Instalar um pacote:

```
yarn add <nome_pacote>
```

Instalar um pacote como dependência de desenvolvimento:

```
yarn add <nome_pacote> --dev
```

Instalar um pacote globalmente:

```
yarn global add <nome_pacote>
```

### Atualização de Pacotes

Atualizar todos os pacotes:

```
yarn upgrade
```

Atualizar um pacote:

```
yarn upgrade <nome_pacote>
```

### Remoção de Pacotes

Remover um pacote:

```
yarn remove <nome_pacote>
```