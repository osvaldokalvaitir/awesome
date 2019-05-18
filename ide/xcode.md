# XCode

Xcode é um ambiente de desenvolvimento integrado e software livre da Apple Inc. para gerenciamento de projetos relacionados com o sistema operacional OS X.

## Documentação e Instalação

Clique [aqui](https://developer.apple.com/xcode) para ver a documentação e fazer a instalação.

Com o XCode instalado, basta executar o seguinte comando na pasta de um projeto React Native para rodar o React Native no simulador de iOS:

```
react-native run-ios
```

Ou é possível informar a versão do emulador utilizado passando a propriedade --simulator:

```
react-native run-ios --simulator="iPhone XS Max"
```

## Configurações de Aplicativos iOS

Para configurar o ícone, nome da aplicação, splashscreen, id do pacote dentro do iOS, execute os seguintes procedimentos:

- No projeto em React Native, clique com o botão direito na pasta `ios` e selecione `Reveal in Finder`

- Encontre o arquivo de extensão `xcodeproj` e abra-o

- Ao clicar no ícone de menu e em `Targets`, em todos os targets abaixo, na seção `Signing`, terá que ativar a opção `Automatically manage signing` e selecionar o `Team` desejado

- Em `Images.xcassets` e em `AppIcon`, coloque todas as imagens referentes ao texto descritivo

- Em `LaunchScreen.xib`, faça a splashscreen como desejado

- Clique no arquivo do `xcodeproj` e aparecerá a guia `General`

- Na guia `General`:

  - Em `Display Name`, dê um nome para a aplicação

  - Em `Bundle Identifier`, dê um nome ao pacote (ex: `com.<nome_empresa>.<nome_aplicação>`)

  - Em `Deployment Info`, nas opções de `Device Orientation`, é possível escolher apenas a opção `Portrait`, desabilitando as demais