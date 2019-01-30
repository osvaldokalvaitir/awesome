# react-native-cli

A interface de linha de comando (CLI) do React Native. O React Native é distribuído como dois pacotes npm, `react-native-cli` e `react-native`. O primeiro é um pacote leve que deve ser instalado globalmente (`npm install -g react-native-cli`), enquanto o segundo contém o código real do framework React Native e é instalado localmente em seu projeto quando você executa `react-native init`. Como o `react-native init` chama o `npm install react-native`, simplesmente vincular seu clone do github local ao npm não é suficiente para testar mudanças locais.

## Documentação

Clique [aqui](https://github.com/facebook/react-native) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-native-cli) para fazer a instalação.

Instalar globalmente:

```
npm install -g react-native-cli | yarn global add react-native-cli
```

## Comandos do CLI

Criação de novo projeto:

```
react-native init nome_app
```

Exibição de uma lista de comandos possíveis:

```
react-native -h
```

### Execução de Projeto no React Native

- Quando executar o projeto pela primeira vez ou quando instalar uma biblioteca que contêm código nativo que precise executar o comando `react-native link nome-da-biblioteca`, podemos executar os comandos abaixo.

Executar o projeto no Android:

```
react-native run-android
```

Executar o projeto no iOS:

```
react-native run-ios
```

- Depois nos demais casos, podemos usar o comando:

```
react-native start
```

### Vincular bibliotecas que contêm código nativo

Algumas bibliotecas contêm códigos nativos e depois serem instaladas, observando que o sinalizador `--save` ou `--save-dev` é muito importante nesta etapa, pois o React Native ligará as libs com base nas `dependencies` e `devDependencies` no seu arquivo package.json. É necessário executar os comandos abaixo.

Para vincular a biblioteca instalada com dependências nativas:

```
react-native link nome-da-biblioteca
```

Para vincular todas as bibliotecas com dependências nativas:

```
react-native link
```

## Erros

### Android/iOS

Lista de erros comuns enfrentados no Android/iOS:

## The development server returned response error code: 500


Geralmente esse erro acontece quando você tenta importar um arquivo JS que não possui `export default` ou não possui nenhum componente dentro dele.

Primeiramente cheque todos arquivos e importações recentes que você fez para garantir que todos possuem import/exports e seus devidos componentes.

Caso isso não resolva, feche a janela do terminal `Metro Bundler` que abre automaticamente com o `run-ios/run-android` e na pasta do seu projeto execute:

```
react-native start --reset-cache
```

Esse comando irá limpar o cache do React Native provavelmente resolvendo o erro.

### Android

Lista de erros comuns enfrentados no Android:

## Unable to load script from assets 'index.android.bundle'. Make sure...

Esse erro geralmente acontece porque o sistema não conseguiu criar o bundle inicial que contém todo o código Javascript da aplicação.

Para resolver comece criando uma pasta `assets` dentro da pasta `android/app/src/main`.

Logo após, execute o comando:

```
react-native bundle --platform android --dev false --entry-file index.js --bundle-output android/app/src/main/assets/index.android.bundle --assets-dest android/app/src/main/res/
```

Agora, feche as abas do terminal e rode `react-native run-android` novamente.

## react-native run-android: FAILURE: Build failed with an exception.

Esse erro pode acontecer por muitos motivos, mas na maioria das vezes é algum cache que precisa ser deletado.

Para resolver execute na pasta do seu projeto:

```
cd android && gradlew clean cd .. && react-native run-android
```

### iOS

Lista de erros comuns enfrentados no iOS:

## :CFBundleIdentifier does not exists

Esse erro geralmente acontece pois o React Native não conseguiu configurar as dependências e bibliotecas de terceiros dentro do iOS.

Para resolver acesse a pasta `node_modules/react-native/scripts` e execute:

```
./ios-install-third-party.sh
```

Assim que finalizar, acesse a pasta `third-party/glog-x-x-x`, preencha `x-x-x` com a versão instalada (você pode utilizar o TAB para completar digitando `glog-` e clicando TAB). Dentro dessa pasta execute:

```
../../ios-configure-glog.sh
```

Depois disso, volte à pasta do seu projeto e rode `react-native run-ios` (Pode ser necessário rodar duas vezes).