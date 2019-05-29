# OneSignal

Serviço gratuito de entrega de notificações Push.

## Documentação e Acesso ao Serviço

Clique [aqui](https://onesignal.com) para ver a documentação e acessar o serviço.

## Adicionar App

Para adicionar um app no OneSignal, siga os seguintes procedimentos:

- Acesse o site do OneSignal

- Crie uma conta

- No `All Applications`, clique em `Add App`

- Na janela `Add a New App`:

  - Em `App Name`, digite o nome da aplicação

  - Clique em `Add App`

- Na janela `Edit app <nome_aplicação>`:

  - Em `Select Platform`:

    - Selecione `Apple iOS`

    - Clique em `Next`

  - Em `Configure Platform`:

    - É necessário, gerar o certificado, para isso clique [aqui](../password-certificate/the-provisionator.md) e siga `Gerar certificados`

    - Em `Production Certificate .p12 file:`, clique em `Choose File...` e selecione o certificado gerado

    - Em `Production Private Key Password`, digite a senha recebida na geração do certificado

    - Clique em `Save`

  - Em `Select SDK`:

    - Selecione `React Native`

    - Clique em `Next`

  - Em `Install SDK`:

    - Pode clicar no botão fechar `X` da tela

    - Irá aparecer a janela `Leave platform setup?`, clique no botão `Leave Setup`

- No `Dashboard`, clique em `Settings`

- Em `Native App Platforms`, clique em `Google Android`

- Na janela `Configure Platform`:

  - Em `Configure Platform`:

    - É necessário, criar um projeto no Firebase e ver suas configurações, para isso clique [aqui](../development-platform/firebase.md) e siga `Criar um projeto` e `Configurações de Mensagens`

    - Em `Firebase Server Key`, cole o token da `Chave do servidor` do Firebase

    - Em `Firebase Sender ID`, cole o código do `Código do remetente` do Firebase

    - Clique em `Save`.

## Chave do App

Para ver a chave do app no OneSignal, siga os seguintes procedimentos:

- No `Dashboard`, clique em `Settings`

- Clique em `Keys & IDs`

- O campo `OneSignal App ID`, armazena o valor que deve ser informado na inicialização do OneSignal no React Native.

## Enviar uma Mensagem

Para enviar mensagens de testes no OneSignal, siga os seguintes procedimentos:

- No `Dashboard`, clique em `Messages`

- Clique em `New Push`

- Em `New Message`:

  - No tópico `2 Message`:

    - Em `Title`, digite um título

    - Em `Message`, digite uma mensagem

  - Clique em `Confirm`

- Na janela `Confirm Before Sending`, clique em `Send Message`.
