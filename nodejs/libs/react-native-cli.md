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

- Quando aparecer uma tela vermelha de erro ao executar o projeto, às vezes, é necessário limpar a cache do projeto, usando o comando:

```
react-native start --reset-cache
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
