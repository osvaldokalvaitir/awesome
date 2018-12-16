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

## Comando do CLI

Criação de novo projeto:

```
react-native init nome_app
```

### Execução de Projeto no React Native

Executar o projeto no Android:

```
react-native run-android
```

Executar o projeto no iOS:

```
react-native run-ios
```