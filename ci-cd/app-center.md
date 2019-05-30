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

  - Clique em `Add new app`

Depois de concluído, aparecerá na tela `Overview`, a página `Add App Center’s SDK to your app`, mas este procedimento não é necessário. Somente é necessário se for utilizar alguma ferramenta do App Center como Diagnostics, Analytics ou Push.  

Obs: Se for compilar para iOS e Android, é necessário adicionar um projeto para iOS e outro para Android.

## Usar CodePush

Antes de configurar o Staging e o Release no React Native, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Distribute`

- Clique em `CodePush`

- Clique no botão `Create standard deployments`

Obs: Realize o mesmo processo para iOS e Android.

As releases geradas pelo CodePush apareceram aqui, mude o combobox para `Staging` ou `Production` para vê-las. É possível ver mais detalhes clicando sobre elas.

## Gerar Build de Staging no Android

Para configurar a build de Staging no Android, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Build`

- Em `Select a service`, selecione `GitHub`

- Faça o login no GitHub se for necessário

- Selecione o repositório desejado

- É necessário criar uma branch chamada `staging`, clique [aqui](../version-control/git.md) - Siga `Comandos > Branches` para criar uma branch staging no GitHub

- Aparecerá as branches do projeto, no caso, `master` e `staging`

- Clique na engrenagem da branch de `staging`

- Na janela `Build configuration`:

  - Na seção `Build app`:

    - Em `Build Variant`, selecione `releaseStaging` (criado no `build.gradle` do projeto Android)

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

    - Coloque `On` na seção

    - Selecione a opção `Groups`

    - Clique no combobox e selecione `Collaborators`

  - Na seção `Advanced`, é possível gerar uma badge para colocar no repositório do GitHub

  - Clique em `Save & Build`

Depois de concluído, é enviado um e-mail com o aplicativo para todos os integrantes do grupo selecionado, bastando instalar o aplicativo e realizar os testes, não necessitando da Google Play.

## Gerar Build de Staging no iOS

Para configurar a build de Staging no iOS, siga os seguintes procedimentos:

- Acesse o app criado no App Center

- Clique em `Build`

- Em `Select a service`, selecione `GitHub`

- Faça o login no GitHub se for necessário

- Selecione o repositório desejado

- É necessário criar uma branch chamada `staging`, clique [aqui](../version-control/git.md) - Siga `Comandos > Branches` para criar uma branch staging no GitHub

- Aparecerá as branches do projeto, no caso, `master` e `staging`

- Clique na engrenagem da branch de `staging`

- Na janela `Build configuration`:

  - Na seção `Build app`:

    - É necessário configurar o staging no XCode, clique [aqui](../ide/xcode.md) e siga `Configurações de Projeto > Deployment` para configurar o staging

    - Em `Shared Scheme`, selecione `<nome_aplicacao>-staging`

    - Em `Build frequency`, pode deixar o padrão `Build this branch on every push`, para dar um build automático a cada push na branch

    - Em `Automatically increment version code`, coloque `On`

    - Em `Run unit tests`, é possível ativar, se tiver algum teste na aplicação

  - Na seção `Sign builds`:

    - Coloque `On` na seção

    - É necessário criar os perfis de provisionamento, clique [aqui](../development-platform/apple-developer.md) e siga `Criar Perfil de Provisionamento` para criar os perfis Development, AdHoc e Production

    - Clique no botão de upload `Provisioning Profile` e selecione o perfil de provisionamento AdHoc

    - Clique no botão de upload `Certificate`, selecione o perfil de provisionamento Production e digite a senha do certificado. Ex: `123456`

  - Na seção `Test on a real device`, é possível que testem a aplicação em dispositivos reais e enviem o feedback.

  - Na seção `Distribute builds`

    - Coloque `On` na seção

    - Selecione a opção `Groups`

    - Clique no combobox e selecione `Collaborators`

  - Na seção `Advanced`, é possível gerar uma badge para colocar no repositório do GitHub

  - Clique em `Save & Build`

Depois de concluído, é enviado um e-mail com o aplicativo para todos os integrantes do grupo selecionado, bastando instalar o aplicativo e realizar os testes, não necessitando da App Store.

Obs: É necessário instalar o aplicativo pelo Safari, no Google Chrome este processo não funciona.