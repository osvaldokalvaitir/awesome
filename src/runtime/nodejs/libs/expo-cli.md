# Expo CLI

Ferramentas para criar aplicativos no Expo.

## Documentação

Clique [aqui](https://github.com/expo/expo-cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/expo-cli) para fazer a instalação.

Instalar globalmente:

```
npm install --global expo-cli | yarn global add expo-cli
```

Atualmente, não é mais necessário instalar a biblioteca do expo, pois é possível executar os comandos pelo npx.

## Comandos do CLI

Criação de novo projeto com expo local:

```
expo init <nome_app>
```

Ou pelo npx:

```
npx expo init <nome_app>
```

Aparecerá o menu abaixo:

<sub> Choose a template: **blank** </sub>

<sub> Please enter a few initial configuration values: **digite o nome do projeto** </sub>  
 
<sub> Use Yarn to install dependencies? **Yes** </sub>

Ou para criar direto um projeto com Managed Workflow:

```
npx create-expo-app <nome_app>
```

Instalação de bibliotecas pelo expo local:

```
expo install <nome_biblioteca>
```

Ou pelo npx:

```
npx expo install <nome_biblioteca>
```

Exibição de uma lista de comandos possíveis:

```
expo -h
```

### Execução de Projeto para Desenvolvimento no React Native no Emulador Android e iOS

- Para executar o projeto do Expo no emulador no Android e iOS, podemos executar o comando abaixo.

```
expo start
```

Ou pelo npx:

```
npx expo start
```

Abrirá o `Metro Bundler` na aba no navegador.  

Para executar o projeto no emulador do Android, clique em `Run on Android device/emulator`.  

Obs: No Android, precisa aceitar uma permissão antes de instalar.

Para executar o projeto no emulador do iOS, clique em `Run on iOS simulator`.