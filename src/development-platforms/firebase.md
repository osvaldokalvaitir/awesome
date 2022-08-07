# Firebase

O Firebase é uma plataforma de desenvolvimento de aplicativos para dispositivos móveis e Web.

## Documentação e Acesso ao Serviço

Clique [aqui](https://console.firebase.google.com) para ver a documentação e acessar o serviço.

## Criar um projeto

- Acesse o site do Firebase

- Crie uma conta

- Clique em `Adicionar projeto`

- Na página `Criar um projeto`:

  - Em `Vamos começar nomeando o projeto`:
  
    - Digite um nome para o projeto
    
    - Clique em `Continuar`

  - Em `Google Analytics para seu projeto do Firebase`
    
    - Desabilite a opção `Ativar o Google Analytics neste projeto`
    
    - Clique em `Criar projeto`

  - Irá aparecer uma janela, informando o processo, depois de concluído, clique em `Continuar`

## Adicionar ao aplicativo

Para adicionar o Firebase ao aplicativo, siga os seguintes procedimentos:

- Clique na engrenagem do lado de `Visão geral do projeto`

- Clique em `Configurações do projeto`

- Na página `Comece adicionando o Firebase ao seu aplicativo`, clique em `iOS`

- Na página `Adicionar o Firebase ao seu aplicativo da Apple`:

  - Em `Registrar app`:

    - No `ID do pacote Apple`, coloque o nome do pacote. Pode ser encontrado o nome no arquivo `app.json` em `android > package`. Ex: `com.nomeapp`

    - No `Apelido do app`, pode colocar o apelido da plataforma. Ex: `iOS`

    - Não precisa digitar nada no `Código da App Store`

    - Clique em `Registrar app`

  - Em `Fazer o download do arquivo de configuração`:

    - Faça o download do arquivo `GoogleService-Info.plist`

  - Em `Adicionar o SDK do Firebase`:

    - Realize o procedimento, se não for utilizar o Native Firebase Plugin

    - Clique em `Próxima`

  - Em `Adicionar código de inicialização`:

    - Realize o procedimento, se não for utilizar o Native Firebase Plugin

    - Clique em `Próxima`

  - Em `Próximas etapas`:

    - Realize o procedimento, se não for utilizar o Native Firebase Plugin

    - Clique em `Continuar no console`

- Na página `Comece adicionando o Firebase ao seu aplicativo`, clique em `Android`

- Na página `Adicionar o Firebase ao seu app Android`:

  - Em `Registrar app`:

    - No `Nome do pacote do Android`, coloque o nome do pacote. Pode ser encontrado o nome no arquivo `app.json` em `android > package`. Ex: `com.nomeapp`

    - No `Apelido do app`, pode colocar o apelido da plataforma. Ex: `Android`

    - Não precisa digitar nada no `Certificado de assinatura de depuração SHA-1`

    - Clique em `Registrar app`

  - Em `Fazer o download do arquivo de configuração`:

    - Faça o download do arquivo `google-services.json`

  - Em `Adicionar o SDK do Firebase`:

    - Realize o procedimento, se não for utilizar o Native Firebase Plugin

    - Clique em `Próxima`

  - Em `Adicionar código de inicialização`:

    - Realize o procedimento, se não for utilizar o Native Firebase Plugin

    - Clique em `Próxima`

  - Em `Próximas etapas`:

    - Realize o procedimento, se não for utilizar o Native Firebase Plugin

    - Clique em `Continuar no console`

- Obs: Se estiver utilizando o Expo com Bare Workflow, é possível utilizar o [Native Firebase Plugin][https://docs.expo.dev/guides/setup-native-firebase] para evitar as etapas de alteração de código nativo, resumidamente, precisa colocar os arquivos baixados na pasta raiz, indicar sua localização e executar `expo prebuild`.

## Cloud Messaging

Para ver as configurações do projeto referente as mensagens, siga os seguintes procedimentos:

- Clique na engrenagem do lado de `Visão geral do projeto`

- Clique em `Configurações do projeto`

- Clique em `Cloud Messaging`

- Em `Credenciais do projeto`:

  - A `Chave do servidor` é igual a `Firebase Server Key`

  - O `Código do remetente` é igual a `Firebase Sender ID`

## Authentication

Para habilitar a autenticação do Firebase, siga os seguintes procedimentos:

- Clique no item de menu `Criação` e em `Authentication`

- Na página, clique em `Vamos começar`

- Irá redirecionar para a aba `Sign-in method` e aparecerá os tipos de autenticações disponíveis

  - No caso vamos utilizar a opção `E-mail/senha`, então clique nela

  - Na página que aparecer, habilite a opção `E-mail/senha` e clique em `Salvar`

- Na aba `Users`, é possível cadastrar os usuários para testes

## Firestore Database

Para habilitar o banco de dados Firestore, siga os seguintes procedimentos:

- Clique no item de menu `Criação` e em `Firestore Database`

- Na página, clique em `Criar banco de dados`

- Na janela `Criar banco de dados`:

  - Em `Regras seguras para o Cloud Firestore`:

    - Clique na opção `Iniciar no modo de teste`

    - Clique em `Avançar`

  - Em `Defina o local do Cloud Firestore`:

    - Não altere nada e clique em `Ativar`

- Depois de terminado o processo de criação, irá aparecer o banco de dados

Obs: Quando for colocar o projeto em produção, retorne para essa configuração e altere para `Iniciar no modo de produção`.

- Na aba `Dados`, é possível cadastrar os registros para testes