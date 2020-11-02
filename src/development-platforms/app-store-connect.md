# App Store Connect

O App Store Connect para iOS ajuda os desenvolvedores a gerenciar seus aplicativos que estão disponíveis na App Store. Os desenvolvedores podem usar o App Store Connect para monitorar suas últimas tendências, receber notificações de comentários de usuários e responder imediatamente a comentários de clientes do iPhone, do iPad e do iPod touch.

## Acesso ao Serviço

Clique [aqui](https://appstoreconnect.apple.com) para acessar o serviço.

## Documentação

Clique [aqui](https://developer.apple.com/app-store-connect) para ver a documentação.

## Criar App

Para criar um app no App Store Connect, siga os seguintes procedimentos:

- Acesse o site do App Store Connect

- Crie uma conta

- No `Dashboard`, clique em `+` e `Novo app`

- Na janela `Novo app`:

  - Em `Plataformas`, selecione `iOS`

  - Em `Nome`, digite um nome para a aplicação

  - Em `Idioma principal`, selecione `Português (Brasil)`

  - Em `ID do pacote`, selecione o pacote desejado

  - Em `SKU`, pode colocar o que quiser. Ex: `<nome_app_minusculo>`

  - Em `Acesso do usuário`, pode deixar em `Acesso total`

  - Clique em `Criar`

- Depois de criar, na página `Informações do app`:

  - Na seção `Informações que podem ser traduzidas`:

    - Em `URL da Política de privacidade`, coloque o link da política de privacidade

    - Em `Subtítulo`, digite o subtítulo da aplicação

  - Na seção `Informações gerais`:

    - Em `Categoria`, selecione a categoria desejada

  - Clique em `Salvar`

- Clique no item de menu `Preços e disponibilidade`

- Na página `Preços e disponibilidade`:

  - Em `Tabela de preços`, coloque o preço do aplicativo. Ex: `BR 0 (Grátis)`

  - Clique em `Salvar`

- Clique no item de menu `1.0 Preparar para envio`:

- Na página `App para iOS 1.0`:

  - Na seção `Informações da versão`:

    - Na guia `iPhone Tela de 5,5"`:

      - Clique em `Escolher arquivo` e selecione algumas fotos do aplicativo

    - O `iPhone Tela de 5,5"` é o único obrigatório, mas o correto é adicionar fotos para todos os dispositivos

    - Em `Texto promocional`, digite um texto promocional

    - Em `Descrição`, digite uma descrição

    - Em `Palavras-chave`, digite palavras-chave (tags) separados por vírgulas

    - Em `URL de suporte`, digite um link de suporte

    - Em `URL de marketing`, digite um link de marketing

  - Na seção `Informações gerais do app`:

    - Em `Ícone para App Store`, clique em `Escolher arquivo` e selecione um ícone para a aplicação de 1024 x 1024 pixels

    - Na subseção `Informações de contato do representante comercial`, complete com todos os dados necessários: Nome, Sobrenome, Endereço, Bairro, Cidade, Estado, Cep, País, Telefone (com +55) e E-mail

  - Na seção `Informações para a equipe de revisão dos apps`:

    - Na subseção `Informações para iniciar sessão`:
    
      - Em `Necessário iniciar sessão`, marque se a aplicação necessitar de login e coloque o nome de usuário e senha, senão desmarque a opção 

    - Na subseção `Informações de contato`, complete com todos os dados necessários (pois a equipe pode ligar caso tenha alguma dúvida com a revisão): Nome, Sobrenome, Telefone (com +55) e E-mail

    - Em `Notas`, coloque o máximo de detalhes possível

  - Na seção `Liberação da versão`, deixe ativada a opção `Liberar automaticamente esta versão`

  - Clique em `Salvar`.
  
- É necessário enviar pelo XCode, a primeira versão do aplicativo para o App Store Connect, clique [aqui](../ide/xcode.md) - Siga `Configurações > Enviar app para a App Store Connect` para enviar o aplicativo

- Demorará alguns minutos para a aplicação aparecer na App Store Connect

- Clique no item de menu `1.0 Preparar para envio`:

- Na página `App para iOS 1.0`:

  - Na seção `Compilação`:

    - Clique em `Selecione uma compilação antes de enviar seu app`

    - Na janela `Adicionar compilação`:

      - Selecione a compilação `1.0(1)`

      - Clique em `Concluído`

  - Clique em `Salvar`

  - Depois de tudo certo, clique em `Enviar para revisão`.

Depois disso, a compilação irá para o time de desenvolvimento da Apple, se voltar o aplicativo, eles vão mostrar os motivos que foi rejeitado, corrija os erros e envie novamente.  

Quando faz um `git push` para a App Store Connect, aparecerá no menu `App para iOS`, uma nova versão do aplicativo, tendo que clicar na versão e no botão `Enviar para revisão`, pois, não é automático como na Google Play.  

É possível usar o recurso `TestFlight`, configurando os grupos que vão ser os testers da sua aplicação.  