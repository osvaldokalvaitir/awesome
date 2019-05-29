# mLab

Serviço de banco de dados em nuvem totalmente gerenciado que hospeda bancos de dados do MongoDB.

*Obs: A versão gratuita não é indicada para produção, é indicado a versão paga para a produção.*

## Documentação e Acesso ao Serviço

Clique [aqui](https://mlab.com) para ver a documentação e acessar o serviço.

## Criar banco de dados

Para criar um banco de dados, siga os seguintes procedimentos:

- Acesse o site do mLab

- Crie uma conta

- No `Dashboard`, clique em `Create new`

- Em `Cloud Provider`, selecione `Amazon Web Services`

- Em `Plan Type`, selecione `SANDBOX`

- Clique em `Continue`

- Em `AWS Region`, selecione `US East (Virginia) (us-east-1)`

- Clique em `Continue`

- Em `Database Name`, digite um nome para o banco de dados

- Clique em `Continue`

- Em `Order Confirmation`, clique em `Submit Order`.

## Criar usuário

Para criar um usuário e senha, siga os seguintes procedimentos:

- Na guia `Users`, clique em `Add database user`

- Digite um usuário, uma senha, a confirmação de senha e clique em `Create`.

O usuário e a senha criados são utilizados para substituir as variáveis `<dbuser>` e `<dbpassword>` no link do banco de dados.
