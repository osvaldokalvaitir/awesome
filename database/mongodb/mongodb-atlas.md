# MongoDB Atlas

Serviço gratuito para hospedar banco de dados MongoDB na nuvem.

## Documentação e Acesso ao Serviço

Clique [aqui](https://www.mongodb.com/cloud/atlas) para ver a documentação e acessar o serviço.

## Criar Cluster

Para criar um cluster no MongoDB Atlas, siga os seguintes procedimentos:

- Acesse o site do MongoDB Atlas

- Crie uma conta

- No `Dashboard`, clique no item de menu `Clusters`

- Na página `Cluster`, clique em `Build a New Cluster`

- Na página `Create New Cluster`:

  - Na seção `Cloud Provider & Region`, deixe o padrão que é gratuito `aws` e `N. Virginia`

  - Clique em `Create Cluster`

- Depois de concluído o servidor, não precisa criar um database, se ele não tiver ele cria automaticamente

- No `Dashboard`, clique no item de menu `Database Access`

- Na página `Database Access`, clique em `Add New User`

- Na janela `Add New User`:

  - Em `Enter username`, digite um usuário

  - Em `Enter password`, digite uma senha

  - Em `User Privileges`, deixe o padrão `Read and write to any database`

  - Clique em `Add User`

- No `Dashboard`, clique no item de menu `Network Access`

- Na página `Network Access`, na guia `IP Whitelist`, clique em `Add IP Address`

- Na janela `Add Whitelist Entry`:

  - Clique em `Allow Access from anywhere`, para preencher automaticamente o campo `Whitelist Entry`

  - Clique em `Confirm`

- No `Dashboard`, clique no item de menu `Clusters`

- Na página `Cluster`, clique em `Connect`

- Na janela `Connect to <nome_cluster>`:

  - Na guia `Choose a connection method`:

    - Selecione `Connect Your Application`

  - Na guia `Connect`:

    - Em `1 Choose your driver version`, selecione `Node.js`

    - Em `2 Add your connection string into your application code`, clique em `Copy`

    - Clique em `Close`

- Com o caminho do banco de dados copiado, só adicionar na aplicação.