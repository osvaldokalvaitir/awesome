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

## Configurações de Projeto

Para realizar as configurações de projeto em React Native no XCode, clique com o botão direito na pasta `ios` e selecione `Reveal in Finder`.

Encontre o arquivo de extensão `xcodeproj` e abra-o.

### Ícone, Splashscreen e Outros

Para configurar o ícone, nome da aplicação, splashscreen, id do pacote dentro do iOS, siga os seguintes procedimentos:

- Clique no arquivo do XCode

- Clique no ícone de menu

- Em `Targets`, em todos os targets abaixo, na seção `Signing`, terá que ativar a opção `Automatically manage signing` e selecionar o `Team` desejado

- Em `Images.xcassets` e em `AppIcon`, coloque todas as imagens referentes ao texto descritivo

- Em `LaunchScreen.xib`, faça a splashscreen como desejado

- Clique no arquivo do XCode

- Clique na guia `General`

- Na guia `General`:

  - Em `Display Name`, dê um nome para a aplicação

  - Em `Bundle Identifier`, dê um nome ao pacote (ex: `com.<nome_empresa>.<nome_aplicação>`)

  - Em `Deployment Info`, nas opções de `Device Orientation`, é possível escolher apenas a opção `Portrait`, desabilitando as demais

### Notificações Push

Para configurar notificações Push no iOS, siga os seguintes procedimentos:

- Clique no arquivo do XCode 

- Clique na guia `Capabilities`

- Na guia `Capabilities`:

  - Habilite a opção `Push Notifications`

  - Habilite a opção `Background Modes`

- Em `Background Modes` e `Modes` selecione a opção `Remote notifications`.

### Aúdio em Background

Para o aúdio continuar sendo executado em background no iOS, siga os seguintes procedimentos:

- Clique no arquivo do XCode

- Clique na guia `Capabilities`

- Na guia `Capabilities`, habilite a opção `Background Modes`

- Em `Background Modes` e `Modes` selecione a opção `Audio, AirPlay, and Picture in Picture`.

### Deployment

Para configurar o deployment, siga os seguintes procedimentos:

- Clique no arquivo do XCode

- Clique no ícone de menu 

- Em `Targets`, exclua os targets de `tv` para não atrapalhar

- Clique em `Project`

- Em `Project`:

  - Na guia `Info`:

    - Na seção `Configurations`, clique em `Release`

    - Clique no `+` e em `Duplicate "Release" Configuration`

    - Renomeie a configuração para `Staging`

  - Na guia `Build Settings`:

    - Clique em `All` e `Levels`

    - Em `Per-configuration Build Products Path`, clique em `Staging`

    - Na coluna que está o nome do projeto, clique em `build/Staging-iphoneos`

    - Abrirá uma janela com o conteúdo `$(BUILD_DIR)/$(CONFIGURATION)$(EFFECTIVE_PLATFORM_NAME)`, substitua por `$(BUILD_DIR)/Release$(EFFECTIVE_PLATFORM_NAME)` e salve

    - Ao fechar a janela, alterará o conteúdo da coluna para `build/Release-iphoneos`, que ao clicar na coluna de cima `Release` precisa estar com o mesmo conteúdo

    - Clique no `+` do lado de `Levels` e em `Add User-Defined Setting`

    - Aparecerá uma nova opção, renomeie para `CODEPUSH_KEY`

    - Clique em `Combined`

    - É necessário executar um comando para ver as chaves do CodePush, clique [aqui](../nodejs/libs/appcenter-cli.md) e siga `Comandos do CLI` para exibir as chaves no terminal

    - Copie a chave do `Staging` do iOS do terminal para o `Staging` do `CODEPUSH_KEY`

    - Copie a chave do `Production` do iOS do terminal para o `Release` do `CODEPUSH_KEY`

- Clique no arquivo `Info.plist`

- No arquivo `Info.plist`:

  - Na coluna `Key`, em `CodePushDeploymentKey`, substitua `deployment-key-here` por `$(CODEPUSH_KEY)`

- Clique no menu `Product`, no submenu `Scheme` e no item `Manage Schemes...`

- Na janela de gerenciamento:

  - Exclua o projeto de `tv`, dando um clique nele e em `-`

  - Na coluna `Scheme`, clique no projeto desejado

  - Clique na engrenagem e em `Duplicate`

- Na janela de duplicação:

  - No canto superior esquerdo, renomeie o nome `Copy of <nome_projeto>` para `<nome_projeto>-staging`

  - Clique em `Close`

- Na janela de gerenciamento:

  - Com o novo esquema selecionado, clique na caixa de seleção da coluna `Shared`

  - Clique em `Edit...`

- Na janela de edição:

  - No menu `Run`, na guia `Info`, em `Build Configuration`, selecione `Staging`

  - No menu `Archive`, em `Build Configuration`, selecione `Staging`

  - Clique em `Close`

- Clique no arquivo do XCode

- Em `Targets`, selecione o projeto

- Clique na guia `General`

- Na guia `General`:

  - Na seção `Signing`, desative a opção `Automatically manage signing`

  - É necessário criar os perfis de provisionamento, clique [aqui](../development-platform/apple-developer.md) e siga `Criar Perfil de Provisionamento` para criar os perfis

  - Na seção `Signing (Debug)`:
    
    - Em `Provisioning Profile`, clique em `None`
    
    - Clique em `Import Profile...`
    
    - Selecione o perfil criado `Development`

  - Na seção `Signing (Release)`:
    
    - Em `Provisioning Profile`, clique em `None`
    
    - Clique em `Import Profile...`
    
    - Selecione o perfil criado `Production`

  - Na seção `Signing (Staging)`:
    
    - Em `Provisioning Profile`, clique em `None`
    
    - Clique em `Import Profile...`
    
    - Selecione o perfil criado `AdHoc`

### Enviar app para a App Store Connect

Para enviar o app para a App Store Connect, siga os seguintes procedimentos:

- Clique no botão do canto superior esquerdo onde está escrito `<nome_aplicação> > iPhoneXs`

- Selecione a opção `Generic iOS Device`

- Clique no item de menu `Product` e `Archive`

- Será gerado o arquivo `.ipa` que é semelhante ao `apk`, mas ele não é muito manuseável

- Se pedir uma senha, coloque a senha do computador

- Aparecerá uma janela ao terminar, nessa janela clique no botão `Distribute App`

- Na janela que abrir:

  - Na página `Select a method of distribution`:
  
    - Selecione `iOS App Store`

    - Clique em `Next`

  - Na página `Select a destination`:

    - Selecione `Upload`
  
    - Clique em `Next`

  - Na página `App Store distribution options`:
  
    - Deixe as duas opções `Include bicode for iOS content` e `Upload your app's symbols to receive symbolicated reports from Apple` ativadas como está
  
    - Clique em `Next`

  - Na página `Select certificate and iOS App Store profiles`:

    - Em `Distribution certificate`, selecione o certificado de distribuição

    - Em `<nome_aplicacao.app`, selecione o profile de produção. Ex: `Production`

    - Clique em `Next`

  - Na página de `Review <nome_aplicacao>.ipa content`:

    - Clique em `Upload`

  - Depois de concluído o upload, na página `Archive upload complete`:

    - Clique em `Done`

Demorará alguns minutos para a aplicação aparecer na App Store Connect.