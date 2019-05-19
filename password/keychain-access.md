# Keychain Access

Keychain Access é o sistema de gerenciamento de senha no macOS, desenvolvido pela Apple. Um Keychain pode conter vários tipos de dados: senhas, chaves privadas, certificados e notas seguras.

## Documentação

Clique [aqui](https://support.apple.com/pt-br/guide/keychain-access/welcome/mac) para ver a documentação.

## Acesso ao Aplicativo

O aplicativo de gerenciamento de senha está presente de forma nativa no macOS.

## Gerar certificado

Para gerar um certificado no Keychain Access, siga os seguintes procedimentos:

- Abra o aplicativo

- Clique no menu `Keychain Access`

- Clique no sub-menu `Certificate Assistant`

- Clique em `Request a Certificate From a Certificate Authority...`

- Na janela `Certificate Assistant`:

  - Em `User Email Address`, digite o e-mail desejado

  - Em `Request is`, selecione a opção `Saved to disk`

  - Clique em `Continue`

  - Crie uma pasta com o nome `Apple` e renomeie o certificado para `CSR.certSigningRequest` e clique em `Save`

  - Clique em `Done`.