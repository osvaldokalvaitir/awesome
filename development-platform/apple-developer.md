# Apple Developer

É uma plataforma de desenvolvimento da Apple. Ele foi projetado para disponibilizar recursos para ajudar os desenvolvedores de software a criar softwares para as plataformas macOS, tvOS, watchOS e iOS.

## Documentação e Acesso ao Serviço

Clique [aqui](https://developer.apple.com) para ver a documentação e acessar o serviço.

## Adicionar App

Para adicionar um app no Apple Developer, siga os seguintes procedimentos:

- Acesse o site do Apple Developer

- Crie uma conta

- No `Dashboard`, clique no item de menu `Overview` e `Certificates, Identifiers & Profiles` (obs: No meu caso, não apareceu a opção, mas pode ser que seja por eu estar no Windows)

- Na seção de menu `Identifiers` e clique em `App IDs`, clique no botão `+` para registrar um App ID:

  - Na seção `App ID Description`, no campo `Name`, dê um nome para a aplicação

  - Na seção `App ID Sufix`, no item `Explicit App ID` e no campo `Bundle ID`, dê um nome ao pacote (ex: `com.<nome_empresa>.<nome_aplicação>`)

  - Na seção `Services`, pode configurar quais opções vão estar habilitadas na aplicação

  - Clique em `Continue`

  - Clique em `Register`

  - Clique em `Done`.

## Gerar Certificado

Para gerar um certificado no Apple Developer, siga os seguintes procedimentos:

- No `Dashboard`, clique no item de menu `Overview` e `Certificates, Identifiers & Profiles` (obs: No meu caso, não apareceu a opção, mas pode ser que seja por eu estar no Windows)

- Na seção de menu `Certificates` e clique em `Production`, clique no botão `+` para adicionar um certificado:

  - Na página `Select Type`:

    - Na seção `Production`, selecione a opção `App Store and Ad Hoc`

    - Clique em `Continue`

  - Na página `Request`, clique novamente em `Continue`

  - Na página `Generate`:

    - É necessário, gerar o certificado, para isso clique [aqui](../password/keychain-access.md) e siga `Gerar certificado`

    - Em `Upload CSR file.`, clique em `Choose File...` e selecione o certificado gerado

    - Clique em `Continue`

  - Na página `Download`:

    - Clique em `Donwload` para realizar o download do certificado

    - Clique em `Done`.

Para exportar o certificado, siga os seguintes procedimentos:

- Localize o certificado gerado

- Clique em cima do certificado e `Export <nome_certificado>`

- Selecione a pasta que deseja salvar (Ex: `Apple`)

- Renomeie o certificado para `Producao`

- Clique em `Save`

- Aparecerá uma janela de senha, crie uma senha e repita ela (Ex: `123456`)

- Aparecerá uma janela pedindo a senha do computador, digite-a e clique em `Always Allow`.

## Criar Perfil de Provisionamento

Para criar um perfil de provisionamento no Apple Developer para `Development`, `AdHoc` e `Production`, siga os seguintes procedimentos:

- No `Dashboard`, clique no item de menu `Overview` e `Certificates, Identifiers & Profiles` (obs: No meu caso, não apareceu a opção, mas pode ser que seja por eu estar no Windows)

- Na seção de menu `Provisioning Profiles` e clique em `All`, clique no botão `+` para criar um perfil:

### Perfil Development

- Na página `Select Type`:

  - Na seção `Development`, selecione a opção `iOS App Development`

  - Clique em `Continue`

- Na página `Configure`:

  - Em `App ID`, selecione o app desejado

  - Clique em `Continue`

  - Em `Select certificates`:
    
    - Clique em `Select All`, para selecionar o certificado

    - Clique em `Continue`

  - Em `Select devices`:

    - Clique em `Select All`, para selecionar os dispositivos

    - Clique em `Continue`

- Na página `Generate`:

  - Na seção `Name this profile and generate`, em `Profile Name`, digite o nome do perfil (Ex: `Development`)

  - Clique em `Continue`

- Na página `Download`:

  - Clique no botão `Download`

- Coloque o perfil de provisionamento (certificado) na pasta que deseja salvar (Ex: `Apple`).

### Perfil AdHoc

- Na página `Select Type`:

  - Na seção `Distribution`, selecione a opção `Ad Hoc`

  - Clique em `Continue`

- Na página `Configure`:

  - Em `App ID`, selecione o app desejado

  - Clique em `Continue`

  - Em `Select certificates`:
    
    - Selecione o último certificado gerado de distribuição

    - Clique em `Continue`

  - Em `Select devices`:

    - Clique em `Select All`, para selecionar os dispositivos

    - Clique em `Continue`

- Na página `Generate`:

  - Na seção `Name this profile and generate`, em `Profile Name`, digite o nome do perfil (Ex: `AdHoc`)

  - Clique em `Continue`

- Na página `Download`:

  - Clique no botão `Download`

- Coloque o perfil de provisionamento (certificado) na pasta que deseja salvar (Ex: `Apple`).

### Perfil Production

- Na página `Select Type`:

  - Na seção `Distribution`, selecione a opção `App Store`

  - Clique em `Continue`

- Na página `Configure`:

  - Em `App ID`, selecione o app desejado

  - Clique em `Continue`

  - Em `Select certificates`:
    
    - Selecione o último certificado gerado de distribuição

    - Clique em `Continue`

- Na página `Generate`:

  - Na seção `Name this profile and generate`, em `Profile Name`, digite o nome do perfil (Ex: `Production`)

  - Clique em `Continue`

- Na página `Download`:

  - Clique no botão `Download`

- Coloque o perfil de provisionamento (certificado) na pasta que deseja salvar (Ex: `Apple`).