# react-native-cli

A interface de linha de comando (CLI) do React Native. O React Native é distribuído como dois pacotes npm, `react-native-cli` e `react-native`. O primeiro é um pacote leve que deve ser instalado globalmente (`npm install react-native-cli --global`), enquanto o segundo contém o código real do framework React Native e é instalado localmente em seu projeto quando você executa `react-native init`. Como o `react-native init` chama o `npm install react-native`, simplesmente vincular seu clone do github local ao npm não é suficiente para testar mudanças locais.

## Documentação

Clique [aqui](https://github.com/facebook/react-native) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-native-cli) para fazer a instalação.

Instalar globalmente:

```
npm install --global react-native-cli | yarn global add react-native-cli
```

Obs: Prefira usar o npm para instalar, porque pode ocorrer que o yarn não consiga registrar o Path, com isso é necessário entrar [aqui](https://yarnpkg.com/lang/en/docs/cli/global) e seguir `Adding the install location to your PATH`.

## Comandos do CLI

Criação de novo projeto:

```
react-native init <nome_app>
```

Exibição de uma lista de comandos possíveis:

```
react-native -h
```

### Execução de Projeto para Desenvolvimento no React Native

- Quando executar o projeto pela primeira vez ou quando instalar uma biblioteca que contêm código nativo que precise executar o comando `react-native link nome-da-biblioteca` (_DESCONTINUADO_), podemos executar os comandos abaixo.

Executar o projeto no Android:

```
react-native run-android
```

Executar o projeto no iOS:

```
react-native run-ios
```

Ou é possível informar a versão do emulador utilizado passando a propriedade `--simulator`:

```
react-native run-ios --simulator="iPhone XS Max"
```

- Depois nos demais casos, podemos abrir o aplicativo no smartphone e usar o comando:

```
react-native start
```

### Execução de Testes de Projeto no React Native

Executar testes no projeto:

```
npm test | yarn test
```

Executar testes e mostrar um relatório detalhado:

```
npm test --coverage | yarn test --coverage
```

Obs: Nos testes executados não apareceu nenhum arquivo no Coverage Report, aparece se eu executar o comando:

```
npm test --coverage --watchAll | yarn test --coverage --watchAll
```

### Geração da Build do Projeto no React Native para a Google Play

Antes de gerar a build do projeto para enviar a Google Play, é necessário alterar a versão do app no arquivo `build.gradle` dentro da pasta `android\app`.

O arquivo contém o seguinte bloco que deve ser alterado de acordo com a versão:

```
  defaultConfig {
    ...
    versionCode 1
    versionName "1.0"
  }
```

Depois de alterado, para gerar build do projeto, entre na pasta `android`:

```
cd android
```

Execute o comando abaixo:

```
gradlew bundleRelease
```

O arquivo de extensão AAB aparecerá na pasta `android\app\build\outputs\bundle\release`.

Antes de fazer o upload da versão compilada para a Play Store, certifique-se de testá-la completamente. Primeiro desinstale qualquer versão anterior do aplicativo que você já instalou. Instale-o no dispositivo usando:

```
react-native run-android --variant=release
```

### Vincular bibliotecas que contêm código nativo (_DESCONTINUADO_)

Algumas bibliotecas contêm códigos nativos e depois serem instaladas, observando que o sinalizador `--save` ou `--save-dev` é muito importante nesta etapa, pois o React Native ligará as bibliotecas com base nas `dependencies` e `devDependencies` no seu arquivo package.json. É necessário executar os comandos abaixo.

Para vincular a biblioteca instalada com dependências nativas:

```
react-native link nome-da-biblioteca
```

## Erros

# Android/iOS

Lista de erros comuns enfrentados no Android/iOS:

## The development server returned response error code: 500

Geralmente esse erro acontece quando você tenta importar um arquivo JS que não possui `export default` ou não possui nenhum componente dentro dele.

Primeiramente cheque todos arquivos e importações recentes que você fez para garantir que todos possuem import/exports e seus devidos componentes.

Caso isso não resolva, feche a janela do terminal `Metro Bundler` que abre automaticamente com o `run-ios/run-android` e na pasta do seu projeto execute:

```
react-native start --reset-cache
```

Esse comando irá limpar o cache do React Native provavelmente resolvendo o erro.

# Android

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

Mas, se o detalhe desse erro, for esse abaixo:

```
* Where:
Settings file 'C:\...\project\android\settings.gradle' line: 3

* What went wrong:
Could not compile settings file 'C:\...\project\android\settings.gradle'.
> startup failed:
  settings file 'C:\...\project\android\settings.gradle': 3: unexpected char: '\' @ line 3, column 133.
     s\react-native-gesture-handler\android')
```

Esse erro está ocorrendo devido a um erro no React Native, depois de instalar algumas bibliotecas, executar o `react-native link` (_DESCONTINUADO_) e depois executar o Android.

Ocorre o erro nas bibliotecas:

- [react-native-gesture-handler](react-native-gesture-handler.md)
- [react-native-vector-icons](react-native-vector-icons.md)

Para resolver, acesse o arquivo `settings.gradle` da pasta `android` e substitua as `\` por `/` no caminho das bibliotecas:

Linhas com os erros:

```
project(':react-native-gesture-handler').projectDir = new File(rootProject.projectDir, '..\node_modules\react-native-gesture-handler\android')
...
project(':react-native-vector-icons').projectDir = new File(rootProject.projectDir, '..\node_modules\react-native-vector-icons\android')
```

Linhas corrigidas:

```
project(':react-native-gesture-handler').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-gesture-handler/android')
...
project(':react-native-vector-icons').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-vector-icons/android')
```

Clique [aqui](https://stackoverflow.com/questions/54504742/getting-error-gradlew-bat-installdebug-after-installing-react-navigation-and-ges) para mais detalhes sobre o erro.

# iOS

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
