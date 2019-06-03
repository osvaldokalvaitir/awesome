# Play Console

Publique seus apps e jogos com o Google Play Console e expanda seus negócios no Google Play. Aproveite os recursos que ajudarão você a melhorar a qualidade do seu app, engajar seu público, gerar receita e muito mais.

## Documentação e Acesso ao Serviço

Clique [aqui](https://play.google.com/apps/publish) para ver a documentação e acessar o serviço.

## Criar App

Para criar um app no Play Console, siga os seguintes procedimentos:

- Acesse o site do Play Console

- Crie uma conta, é necessário pagar uma taxa de registro

- Com a opção `Todas as aplicações` do menu selecionada, clique em `Criar aplicação`

- Na janela `Criar aplicação`:

  - Em `Título`, digite um título para a aplicação

  - Clique em `Criar`

- Clique na opção de menu `Lançamento de aplicações`

- Na página `Lançamentos de aplicações`:

  - Na seção `Faixa de produção`, em `Produção`, clique em `Gerir`

    - Na página `Produção`, clique em `Criar Lançamento`

    - Na página `Novo lançamento para produção`:

      - Em `Permitir que a Google gira e proteja a sua chave de assinatura de aplicações`, clique em `Continuar` ou `Optar por não receber`

      - Em `Android App Bundles e APKs a adicionar`, clique no botão `Procurar ficheiros` e selecione a APK

      - Em `Nome do lançamento`, já vem preenchido automático

      - Em `Quais são as novidades desta versão?`, coloque as novidades da versão

      - Clique em `Guardar`

- Clique na opção de menu `Ficha da loja`

- Na página `Ficha da loja`:

  - Em `Breve descrição`, coloque uma breve descrição

  - Em `Descrição completa`, coloque uma descrição completa

  - Na seção `Detalhes do produto`:

    - Na guia `Telemóvel`, clique em `Procurar ficheiros` e selecione algumas fotos do aplicativo

    - Em `Ícone de alta resolução`, adicine um ícone de 512x512 pixels

    - Em `Gráfico de funcionalidade`, adicione um banner de 1024 x 500 pixels

  - Na seção `Categorização`:

    - Em `Tipo de aplicação`, selecione o tipo de aplicação

    - Em `Categoria`, seleciona a categoria

  - Na seção `Detalhes de contacto`:

    - Em `Website`, digite o site

    - Em `Email`, digite o e-mail

  - Na seção `Política de privacidade`:

    - Em `Política de privacidade`, digite o endereço da política de privacidade

  - Clique em `Guardar rascunho`

- Clique na opção de menu `Classificação de conteúdo`

- Na página `Classificação de conteúdo`:

  - Na tela de introdução, clique em `Continuar`

  - No questionário de classificação de conteúdo:

    - Em `Endereço de email`, digite o e-mail

    - Em `Confirmar endereço de email`, confirme o e-mail

    - Em `Selecionar a categoria da aplicação`, selecione a categoria

    - Dependendo da escolha da categoria, irá aparecer mais algumas perguntas para serem respondidas

    - Clique em `Guardar questionário`

    - Clique em `Calcular a classificação`

  - Na tela de classificação calculada, clique em `Aplicar a classificação`

- Clique na opção de menu `Preços e distribuição`

- Na página `Preços e distribuição`:

  - Selecione se a aplicação é `Paga` ou `Gratuito`

  - Em `Disponibilidade da aplicação`, procure por `Brasil` e clique em `Disponível`

  - Em `Dirigida principalmente a crianças`, selecione se a aplicação é para crianças

  - Em `Contém anúncios`, selecione se a aplicação contém anúncios

  - Na seção `Consentimento`:

    - Em `Diretrizes de conteúdo`, cheque a opção de diretrizes

    - Em `Leis de exportação dos EUA`, cheque a opção de leis
  
  - Clique em `Guardar rascunho`

- Clique na opção de menu `Lançamento de aplicações`

- Na página `Lançamentos de aplicações`:

  - Na seção `Faixa de produção`, clique em `Editar edição`

    - Na página `Novo lançamento para produção`:

      - Clique me `Rever`

    - Na página `Confirmar implementação para produção: <Nome do lançamento>`

    - Clique em `Iniciar implementação para produção`

    - Aparecerá uma janela de confirmação, clique em `Confirmar`

- Depois de concluído, a aplicação é lançada na Google Play

- Quando faz um `git push` para a Google Play, automaticamente a nova versão é lançada na Google Play, diferente da App Store Connect que é manual.

## Conceder Acesso à API

Para conceder acesso à API do Play Console, siga os seguintes procedimentos:

- Clique na opção de menu `Definições`

- Clique na opção do submenu `Acesso à API`

- Na janela `Acesso à API`:

  - Na seção `Contas de serviço`, clique em `Criar conta de serviço`

  - Na janela `Criar conta de serviço`, clique no link do item 1 `Console da API do Google`

- Abrirá uma página, em `Contas de serviço`, clique em `Criar conta de serviço`

- Na página `Criar conta de serviço`:

  - No item 1 `Detalhes da conta de serviço`:

    - Em `Nome da conta de serviço`, digite um nome da conta de serviço. Ex: `AppCenter<Nome Aplicação>`

    - Em `Descrição da conta de serviço`, digite uma descrição

    - Clique em `Criar`

  - No item 2 `Permissões da conta de serviço (opcional)`

    - Em `Selecionar um papel`, selecione `Projeto` e `Proprietário`

    - Clique em `Continuar`

  - No item 3 `Conceda aos usuários acesso a essa conta de serviço (opcional)`

    - Em `Criar chave (opcional)`, clique em `Criar chave`

    - Na janela `Criar chave (opcional)`

      - Clique em `Tipo de chave`, selecione `JSON`

      - Clique em `Criar`

      - Aparecerá uma janela `Chave privada salva no seu computador`, clique em `Fechar`

      - Começará o download do arquivo json automaticamente

- Volte na janela `Criar conta de serviço`, onde foi clicado no link do item 1

  - Na janela `Criar conta de serviço`, clique em `Concluído`

- Na janela `Acesso à API`:

  - Na seção `Contas de serviço`, aparecerá o serviço, clique em `Conceder acesso`

  - Abrirá a janela `Adicionar um novo utilizador`, clique em `Adicionar utilizador`  