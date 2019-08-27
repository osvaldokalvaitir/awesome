# Mapbox Maps SDK for React Native

Um componente oficial do React Native para criar mapas com o [Mapbox Maps SDK for iOS](https://docs.mapbox.com/ios/maps/overview) e [Mapbox Maps SDK for Android](https://docs.mapbox.com/android/maps/overview).

Obs: Uma outra opção seria a biblioteca [react-native-maps](react-native-maps.md).

## Documentação

Clique [aqui](https://github.com/mapbox/react-native-mapbox-gl) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/@mapbox/react-native-mapbox-gl) para fazer a instalação.

## Configuração

Com essa biblioteca, diferente da maioria não vamos fazer o link automático para Android e iOS, vamos fazer manualmente, pois a biblioteca apresenta alguns problemas um pouco complexos para resolver quando é feito o link através do comando `react-native link` (_DESCONTINUADO_).

Para configurar corretamente a biblioteca para funcionar no Android e iOS, siga o passo a passo para cada plataforma logo abaixo:

### Android

Vamos começar a configuração para Android no arquivo `android/build.gradle`, nesse arquivo procure o objeto `allprojects`, e dentro dele por `repositories`, dentro de `repositories` certifique-se de ter o trecho abaixo, e caso não tenha, adicione.

```
maven {
  url "$rootDir/../node_modules/react-native/android"
}
maven { url "https://jitpack.io" }
maven {
  url 'https://maven.google.com/'
  name 'Google'
}
```

Agora vamos para o arquivo `android/app/build.gradle`, nele desça até perto do final e procure o objeto `dependencies`, dentro dele terão algumas linhas começando pela palavra `compile`, dentro desse objeto, adicione o seguinte trecho:

```
compile project(':mapbox-react-native-mapbox-gl') {
  compile ('com.squareup.okhttp3:okhttp:3.6.0') {
    force = true
  }
}
```

Abra agora o arquivo `android/settings.gradle`, e nele adicione no final, as linhas:

```
include ':mapbox-react-native-mapbox-gl'
project(':mapbox-react-native-mapbox-gl').projectDir = new File(rootProject.projectDir, '../node_modules/@mapbox/react-native-mapbox-gl/android/rctmgl')
```

O próximo passo é verificar a versão do SDK do projeto, e para isso se estiver utilizando a versão `0.56` do React Native basta voltar no arquivo `android/build.gradle`, e nele procurar pelo objeto `ext`, nele verifique se as versões são iguais ou superiores à:

```
buildToolsVersion = "26.0.3"
minSdkVersion = 16
compileSdkVersion = 26
targetSdkVersion = 26
supportLibVersion = "26.1.0"
```

Caso esteja em uma versão inferior do React Native verifique se no arquivo `android/app/build.gradle` as configurações são essas, ou superiores:

```
compileSdkVersion 26
buildToolsVersion "26.0.1"
targetSdkVersion 26
compile "com.android.support:appcompat-v7:26.0.1"
```

Para utilizar o Mapbox você precisa ter o SDK 26 ou superior instalado, caso não tenha você pode utilizar SDK Tools do Android Studio para conseguí-lo, siga este tutorial [aqui](https://developer.android.com/studio/intro/update?hl=pt-br).

E agora pra finalizar, vamos fazer algumas modificações no arquivo `android/app/src/main/java/com/<nome_projeto>/MainApplication.java`, a primeira delas é adicionar a importação do Mapbox logo abaixo da importação do SoLoader, ficando assim:

```
...
import com.facebook.soloader.SoLoader;
import com.mapbox.rctmgl.RCTMGLPackage;
...
```

Feito isso falta apenas instanciar a classe do Mapbox e para isso procure o método `getPackages`, e dentro dele, logo abaixo da linha `new MainReactPackage()` adicione o seguinte código:

```
new RCTMGLPackage()
```

Obs.: Não se esqueça de adicionar uma vírgula (,) no final da linha do MainReactPackage.

E assim finalizamos a configuração para o Android, agora só configurar para o iOS, mas antes de prosseguir faça o teste de rodar a aplicação no Emulador do Android para verificar se não ocorre nenhum erro na compilação.

### iOS

Para instalar o MapBox no iOS vamos utilizar o `CocoaPods` que é uma ferramenta para controlar dependências de projetos em iOS. Para instalar o CocoaPods vou utilizar o `HomeBrew`:

```
brew install cocoapods
```

Agora vamos inicializar o CocoaPods na pasta `ios` do nosso projeto React Native, para isso, acesse essa pasta do seu projeto pelo terminal e rode o seguinte comando:

```
pod init
```

Isso criará um arquivo chamado `Podfile` na raiz da pasta `ios` e agora dentro desse arquivo você deve adicionar as seguintes linhas logo abaixo do trecho `target 'NomeDoSeuApp' do`:

```
# Flexbox Layout Manager Used By React Natve
pod 'yoga', :path => '../node_modules/react-native/ReactCommon/yoga/Yoga.podspec'

# React Native
pod 'React', path: '../node_modules/react-native', subspecs: [
  # Comment out any unneeded subspecs to reduce bundle size.
  'Core',
  'DevSupport',
  'RCTActionSheet',
  'RCTAnimation',
  'RCTBlob',
  'RCTCameraRoll',
  'RCTGeolocation',
  'RCTImage',
  'RCTNetwork',
  'RCTPushNotification',
  'RCTSettings',
  'RCTTest',
  'RCTText',
  'RCTVibration',
  'RCTWebSocket',
  'RCTLinkingIOS'
]

# Mapbox
pod 'react-native-mapbox-gl', :path => '../node_modules/@mapbox/react-native-mapbox-gl'
```

Ainda dentro desse mesmo bloco, remova o seguinte trecho de código:

```
target 'NomeDoSeuApp-tvOSTests' do
  inherit! :search_paths
  # Pods for testing
end
```

Agora, volte ao terminal e execute o comando `pod install`. Esse comando levará um tempo e para testar o funcionamento, rode o projeto no Simulador do iOS para garantir que não estão ocorrendo erros no processo de compilação.
