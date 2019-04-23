# Buddy

Automação de entrega, simplificada. CI/CD poderoso e fácil de configurar para desenvolvedores e agências digitais.

## Documentação e Acesso ao Serviço

Clique [aqui](https://buddy.works) para ver a documentação e acessar o serviço.

## Criar um projeto

Para criar um projeto no Buddy siga os seguintes procedimentos:

- Acesse o site do Buddy

- Crie uma conta

- No `Dashboard`, em `Projects` clique em `Create new project`

- Em `Select Git hosting provider`, selecione o `GitHub` e faça o login

- Em `Select repository`, selecione o repositório desejado

- Na próxima tela, clique em `Add a new pipeline`

- Em `Add a new pipeline`:

  - Em `Name`, digite um nome para o projeto

  - Em `Trigger Mode`, selecione a opção `On push`

  - Em `Branch or tag that triggers the pipeline`, selecione a branch ou tag desejada

  - Clique em `Add a new pipeline`

- Em `Add a new action to ...` e `actions`, selecione o sevidor (ex: `DigitalOcean`) e faça o login

- Em `Transfer files to ...`:

  - Em `Account`, faça o login no servidor que está o repositório autorizando o Buddy

  - Em `Droplet`, selecione o repositório que está no servidor

  - Em `Login`, digite o nome do usuário

  - Em `Authentication mode`, selecione `Buddy's SSH key`

  - Aparecerá dois comandos que deverão ser executados dentro do usuário informado no `Login` no servidor. Antes de executar, é necessário criar uma pasta na raíz com o nome `.ssh` e dentro dela executar os comandos.

  - Em `Remote path`, coloque o caminho que os arquivos serão enviados (ex: `~/<nome_repositorio>`)

  - Clique em `Test & add this action on success`

Irá aparecer uma tela, informando se a conexão foi realizada com sucesso.

Depois que terminar, na próxima tela, embaixo de `Upload files to...`, clique em `Execute SSH commands on a remote server`

Em `Execute SSH commands on a remote server`:

  - Em `Run SSH Commands`:

    ```
    npm install
    pm2 restart index

    ```

    Obs: Se tivesse usando o Sequelize, poderia rodar as migrations aqui.

  - Em `Hostname & Port`, digite o IP do servidor

  - Em `Login`, digite o nome do usuário, o mesmo colocado anteriormente

  - Em `Authentication mode`, selecione `Buddy's SSH key`. Não precisará mais executar os dois comandos

  - Em `Working directory`, coloque o caminho que os comandos serão executados (ex: `~/<nome_repositorio>`), o mesmo colocado anteriormente

  - Clique em `Test & add this action on success`

Se for fazer algum teste poderá ser feito um passo a mais, clicando na engrenagem que fica em cima de `Upload files to...`, fazendo com que se o código não passou no teste, não seja feito o upload de arquivos.

Ou também, pode ser feito um passo a mais na última engrenagem fazendo com que se deu tudo certo, envie um SMS ou algo do tipo.

Se quiser alterar o domínio, terá que ser feito através do servidor contratado.