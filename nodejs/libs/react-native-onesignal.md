# react-native-onesignal

Biblioteca do React Native para o OneSignal que é um serviço de notificação por push gratuito para aplicativos móveis.

## Documentação

Clique [aqui](https://github.com/geektimecoil/react-native-onesignal) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-native-onesignal) para fazer a instalação.

Depois da instalação é necessário executar o comando `react-native link` (_DESCONTINUADO_):

```
react-native link react-native-onesignal
```

Depois de linkar o componente, é necessário realizar algumas configurações que podem ser encontradas [aqui](https://documentation.onesignal.com/docs/react-native-sdk-setup) na documentação, para Android em `Android Specific Instructions` e para iOS em `iOS Installation`.

Para compilar no Android, é necessário fazer uma configuração nos arquivos:
  -  `AndroidManifest.xml` em `android > app > src > main > AndroidManifest.xml`
  -  `build.gradle` em `android > app > build.gradle`

Para compilar no iOS, é necessário fazer uma configuração que se encontram-se [aqui](https://github.com/osvaldokalvaitir/projects-settings/blob/master/ide/xcode.md) e siga `Notificações Push`