# Android Studio

Android Studio é um ambiente de desenvolvimento integrado para desenvolver para a plataforma Android.

## Instalação e Configuração

Acessar o site `https://developer.android.com/studio` e clicar no botão `Download Android Studio`. Para instalar basta dar `Next` até o final.  

Para configurar o SDK, clique em `Configure > SDK Manager`, na aba `SDK Platforms` escolha a versão mais recente e na aba `SDK Tools` selecione as opções:  

```
Android SDK Build-Tools
Android Emulator
Android SDK Platform-Tools
Android SDK Tools <versão>
Intel x86 Emulator Accelerator (HAXM installer)
```

Depois, para configurar o emulador, clique em `Configure > AVD Manager`. Clique em `Create Virtual Device...`.  

Na janela que abrir, em `Select Hardware`, na aba `Phone` selecione o modelo mais atual que tenha Play Store, dê um `Next`. Em `System Image`, selecione a api mais atual que você quer usar e se tiver o botão `download` do lado, clique para fazer o download, depois clique em `Next`. Em `Android Virtual Device (AVD)`, no `AVD Name`, digite um nome para o emulador, deixe a `Startup orientation` como `Portrait` e o `Device Frame` como `Enable Device Frame` e clique em `Finish`.  

Para rodar o emulador, só dar um `Play` no emulador desejado.  

Com o emulador aberto você pode realizar o run do React Native para Android através da pasta do seu projeto.  

```
react-native run-android
```

## Documentação e Instalação

Clique [aqui](https://developer.android.com/studio) para ver a documentação e fazer a instalação.