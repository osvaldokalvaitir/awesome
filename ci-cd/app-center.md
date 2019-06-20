# App Center

O Visual Studio App Center permite a automação e gerenciamento do ciclo de vida dos seus aplicativos iOS, Android, Windows e macOS. Despache aplicativos com mais frequência, mais qualidade e com uma confiabilidade maior. Conecte seu repositório e, em minutos, automatize seus builds, teste em dispositivos reais na nuvem, distribua aplicativos para testadores beta e monitore o uso real com dados de falhas e de análise. Tudo em um lugar.

## Documentação e Acesso ao Serviço

Clique [aqui](https://appcenter.ms) para ver a documentação e acessar o serviço.

## Adicionar App

Para criar um app no App Center, siga os seguintes procedimentos:

- Acesse o site do App Center

- Crie uma conta

- No `Dashboard`, clique em `Add new app`

- Na janela `Add new app`:

  - Em `App name`, digite um nome para o aplicativo. Ex: (`<nome_app> (Android)`)

  - Em `Icon`, adicione um ícone de até 512px

  - Em `OS`, selecione o sistema operacional desejado `iOS` ou `Android`

  - Em `Platform`, selecione `React Native`

  - Clique em `Add new app`.

Depois de concluído, aparecerá na tela `Overview`, a página `Add App Center’s SDK to your app`, mas este procedimento não é necessário. Somente é necessário se for utilizar alguma ferramenta do App Center como Diagnostics, Analytics ou Push.  

Obs: Se for compilar para iOS e Android, é necessário adicionar um projeto para iOS e outro para Android.

## Usar CodePush

Antes de configurar o Staging e o Release no React Native, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Distribute`

- Clique em `CodePush`

- Clique no botão `Create standard deployments`.

Obs: Realize o mesmo processo para iOS e Android.

As releases geradas pelo CodePush apareceram aqui, mude o combobox para `Staging` ou `Production` para vê-las. É possível ver mais detalhes clicando sobre elas.

## Gerar Build de Staging e Production no Android

Para configurar a build de Staging e Production no Android, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Build`

- Em `Select a service`, selecione `GitHub`

- Faça o login no GitHub, caso necessário

- Selecione o repositório desejado

- É necessário criar uma branch chamada `staging`, clique [aqui](../version-control/git.md) - Siga `Comandos > Branches` para criar uma branch staging no GitHub

- Aparecerá as branches do projeto, no caso, `master` e `staging`

- Para a build de Staging, clique na engrenagem da branch de `staging`

- Para a build de Production, clique na engrenagem da branch de `master`

- Na janela `Build configuration`:

  - Na seção `Build app`:

    - Para a build de Staging, em `Build Variant`, selecione `releaseStaging` (criado no `build.gradle` do projeto Android)

    - Para a build de Production, em `Build Variant`, selecione `release`

    - Em `Build frequency`, pode deixar o padrão `Build this branch on every push`, para dar um build automático a cada push na branch

    - Em `Automatically increment version code`, coloque `On`

    - Em `Run unit tests`, é possível ativar, se tiver algum teste na aplicação

  - Na seção `Sign builds`:

    - Coloque `On` na seção

    - É necessário criar o arquivo Keystore, clique [aqui](../password-certificate/keytool.md) e siga `Gerar Assinatura da APK` para criar o arquivo

    - Em `Keystore`, clique no botão de upload `Keystore file` e carregue o arquivo gerado

    - Em `Keystore password`, digite a senha da keystore. Ex: `123456`

    - Em `Key alias`, digite o nome do alias. Ex: `nome_aplicação`

    - Em `Key password`, digite a senha. Ex: `123456`

  - Na seção `Test on a real device`, é possível que testem a aplicação em dispositivos reais e enviem o feedback.

  - Na seção `Distribute builds`

    - Para a build de Staging:

      - Coloque `On` na seção
  
      - Selecione a opção `Groups`

      - Clique no combobox e selecione `Collaborators`

    - Para a build de Production:

      - Coloque `Off` na seção

  - Na seção `Advanced`, é possível gerar uma badge para colocar no repositório do GitHub

  - Clique em `Save & Build`.

Para a build de Staging, depois de concluído, é enviado um e-mail com o aplicativo para todos os integrantes do grupo selecionado, bastando instalar o aplicativo e realizar os testes, não necessitando da Google Play.  

Para a build de Production, na primeira vez tem que enviar o APK manualmente para a Google Play, então, depois de concluído, clique no combobox `Download` e `Download build` para fazer o download da APK. Clique [aqui](../development-platform/play-console.md) - Siga `Criar App` para criar o app no Play Console.

## Conectar Store no Android

Para configurar a store no Android, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Distribute`

- Clique em `Stores`

- Clique em `Connect to Store`

- Na janela `Connect to Store`:

  - No item `Select store`:

    - Em `Where would you like to distribute your app?`, clique em `Google Play`

  - No item `Authenticate`:

    - É necessário conceder o acesso da API Play Console ao App Center, clique [aqui](../development-platform/play-console.md) - Siga `Conceder Acesso à API` para dar acesso

    - Em `Upload the Google Dev Console API credentials`, clique em `Security token` e selecione o arquivo json gerado

    - Clique em `Connect`

  - No item `Assign app`:

    - Em `Select your app on Google Play` e `App Package Name`, digite o nome do pacote

    - Clique em `Assign`.

## Build automática na Google Play

Para configurar a build automática na Google Play, siga os seguintes procedimentos:

- Para a build de Production, siga `Conectar Store no Android`

- Clique em `Build`

- Em `Select a service`, selecione `GitHub`

- Clique na engrenagem da branch de `master`

- Na janela `Build configuration`:

  - Na seção `Distribute builds`

    - Coloque `On` na seção

    - Selecione a opção `Store`

    - Clique em `Select destination` e `Production`

    - Em `Release notes (optional)`, coloque uma nota de novas funcionalidades genérica

  - Clique em `Save`.

Se quiser utilizar os recursos de `Alpha` e `Beta` da Google Play, basta fazer as branches com os nomes dos recursos e em `Distribute builds` selecionar o recurso desejado.  

**É muito importante, que toda vez que gerar uma nova build tanto para o `staging` como para o `master`, gerar o CodePush junto para aquele `staging` ou para aquele `master` com seu código atual.**

## Gerar Build de Staging e Production no iOS

Para configurar a build de Staging e Production no iOS, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Para a build de Production, siga `Conectar Store no iOS`

- Clique em `Build`

- Em `Select a service`, selecione `GitHub`

- Faça o login no GitHub, caso necessário

- Selecione o repositório desejado

- É necessário criar uma branch chamada `staging`, clique [aqui](../version-control/git.md) - Siga `Comandos > Branches` para criar uma branch staging no GitHub

- Aparecerá as branches do projeto, no caso, `master` e `staging`

- Para a build de Staging, clique na engrenagem da branch de `staging`

- Para a build de Production, clique na engrenagem da branch de `master`

- Na janela `Build configuration`:

  - Na seção `Build app`:

    - É necessário configurar o staging no XCode, clique [aqui](../ide/xcode.md) e siga `Configurações de Projeto > Deployment` para configurar o staging

    - Para a build de Staging, em `Shared Scheme`, selecione `<nome_aplicacao>-staging`

    - Para a build de Production, em `Shared Scheme`, selecione `<nome_aplicacao>`

    - Em `Build frequency`, pode deixar o padrão `Build this branch on every push`, para dar um build automático a cada push na branch

    - Em `Automatically increment version code`, coloque `On`

    - Em `Run unit tests`, é possível ativar, se tiver algum teste na aplicação

  - Na seção `Sign builds`:

    - Coloque `On` na seção

    - É necessário criar os perfis de provisionamento, clique [aqui](../development-platform/apple-developer.md) e siga `Criar Perfil de Provisionamento` para criar os perfis Development, AdHoc e Production

    - Para a build de Staging, clique no botão de upload `Provisioning Profile` e selecione o perfil de provisionamento AdHoc

    - Para a build de Production, clique no botão de upload `Provisioning Profile` e selecione o perfil de provisionamento Production

    - Clique no botão de upload `Certificate`, selecione o perfil de provisionamento Production e digite a senha do certificado. Ex: `123456`

  - Na seção `Test on a real device`, é possível que testem a aplicação em dispositivos reais e enviem o feedback.

  - Na seção `Distribute builds`

    - Coloque `On` na seção

    - Para a build de Staging:
  
      - Selecione a opção `Groups`

      - Clique no combobox e selecione `Collaborators`

    - Para a build de Production:

      - Selecione a opção `Store`

      - Clique em `Select destination` e `Production`

      - Em `Release notes (optional)`, coloque uma nota de novas funcionalidades genérica

  - Na seção `Advanced`, é possível gerar uma badge para colocar no repositório do GitHub

  - Para a build de Staging, clique em `Save & Build`

  - Para a build de Production, clique em `Save`.

Para a build de Staging, depois de concluído, é enviado um e-mail com o aplicativo para todos os integrantes do grupo selecionado, bastando instalar o aplicativo e realizar os testes, não necessitando da App Store. É necessário instalar o aplicativo pelo Safari, no Google Chrome este processo não funciona.  

Para a build de Production, se quiser utilizar os recursos de `Alpha` e `Beta` da Google Play, basta fazer as branches com os nomes dos recursos e em `Distribute builds` selecionar o recurso desejado.  

Se estiver usando o recurso do `TestFlight`, poderá fazer uma branch com o mesmo nome e também em `Distribute builds > Store`, selecionar `TestFlight`, com esse recurso é automático o envio da app para os testers.  

## Conectar Store no iOS

Para configurar a store no iOS, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Distribute`

- Clique em `Stores`

- Clique em `Connect to Store`

- Na janela `Connect to Store`:

  - No item `Select store`:

    - Em `Where would you like to distribute your app?`, clique em `App Store Connect`

  - No item `Authenticate`:

    - Em `Select Apple Developer Account`, se não aparecer a conta, clique em `New Account` para fazer o login

    - Clique em `Connect`
        
  - No item `Assign app`:

    - Em `Select your app on App Store Connect`, selecione a aplicação

    - Clique em `Assign`.