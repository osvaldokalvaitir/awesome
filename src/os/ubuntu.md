# Ubuntu

Ubuntu é um sistema operacional de código aberto, construído a partir do núcleo Linux, baseado no Debian e utiliza GNOME como ambiente de desktop de sua mais recente versão com suporte de longo prazo.

## Documentação e Download

Clique [aqui](https://www.ubuntu.com/download) para ver a documentação e realizar o download.

## Criar Servidor

Depois de contratar um provedor de servidores na nuvem como [DigitalOcean](../server/digitalocean.md), [Amazon Web Services](../server/amazon-web-services.md) ou outro. É possível criar um servidor Ubuntu ou qualquer outra distribuição Linux, que depois de criado, é disponibilizado um IP para o acesso nele.

Dentro do Ubuntu, é possível executar todos os comandos abaixo independente do servidor de nuvem contratado.

Para começar acesse o servidor por SSH com usuário `root`.

### Atualização do Ubuntu

Para atualizar o Ubuntu execute os comandos:

```
apt-get update
```

e

```
apt-get upgrade
```

### Instalação do Node.js

Clique [aqui](../nodejs/nodejs.md) e siga `Instalação > Linux usando cURL`.

### Instalação do PM2

Clique [aqui](../nodejs/libs/pm2.md) e siga `Instalação`.

### Instalação do MongoDB (Projeto Node.js)

Clique [aqui](../database/mongodb/mongodb.md) e siga `Instalação > Ubuntu`.

### Instalação do Serve (Projeto ReactJS)

Clique [aqui](../nodejs/libs/serve.md) e siga `Instalação`.

### Criação de usuário

Não é o ideal fazer a parte de deploy com usuário root, então, vamos adicionar um novo usuário chamado `deploy`:

```
adduser deploy
```

Adicione uma senha quando pedir e os demais campos pode deixar vazio. Confirme que as informações estão corretas para continuar.

Adicionar o novo usuário ao sudo para que ele tenha permissões de administrador:

```
usermod -aG sudo deploy
```

Para logar com o usuário `deploy`:

```
sudo su deploy
```

Para sair do usuário logado:

```
exit
```

### Clone do projeto

Logado com o usuário `deploy`, ir para a pasta Home:

```
cd ~
```

Listar o conteúdo da pasta atual:

```
ls
```

Para clonar o repositório do GitHub:

```
git clone <nome_repositório>
```

Obs: Se for público dá para copiar o caminho com o HTTPS, mas se for privado tem que copiar o SSH.

Para entrar na pasta criada pelo Git:

```
cd <nome_repositório>/
```

O projeto não vem com a pasta `node_modules` e o arquivo `env`. É necessário instalar as dependências e se o projeto depender de um arquivo de configurações é necessário criá-lo.

Para instalar as dependências:

```
npm install
```

Para criar o arquivo de configurações `env`:

```
vim .env
```

Coloque todas as variáveis de ambientes neste arquivo:

Ex: `DB_URL=mongodb://localhost/<nome_banco>`

Obs: Se a porta for 27017 que é a padrão do MongoDB, então, não precisa especificar ela.

Para salvar o arquivo e sair:

```
:wq
```

### Rodar a aplicação (Projeto Node.js)

Logado com o usuário `deploy`, rode a aplicação:

```
node index.js
```

Copie o IP de acesso ao servidor e faça um teste no Insomnia.

Obs: A aplicação ainda está na porta `3000`.

Pode parecer um erro no terminal do servidor, mas é por causa que no código-fonte ocorre o envio de e-mail, e como não foi configurado o servidor de e-mail, aparecerá um erro.

Pode ser configurado qualquer um dos serviços de e-mail: [SparkPost](../email/sparkpost.md), [Mailgun](../email/mailgun.md), [SendGrid](../email/sendgrid.md) ou outro.

### Build na aplicação (Projeto ReactJS)

Logado com o usuário `deploy`, dê um build na aplicação:

```
npm run build
```

Depois de iniciar o servidor com o PM2, copie o IP de acesso ao servidor e faça um teste no navegador.

Obs: A aplicação ainda está na porta `8080`.

### Configuração do PM2

Logado com o usuário `deploy` e na pasta do projeto, clique [aqui](../nodejs/libs/pm2.md) e siga `Comandos`, para iniciar o servidor, visualizar a lista que o PM2 está rodando, ver a tela de monitoramento e para gerar o script de inicialização.

### Configuração do Proxy do Nginx

O Node.js só aceita uma aplicação Node.js na porta 80, então usamos o Nginx para fazer o gerenciamento da porta.

Logado com o usuário `root`, clique [aqui](../web-server/nginx.md) e siga `Instalação > Linux` e `Setar Arquivo de Configuração > Linux`.

Agora, faça um teste usando a porta 80 ou sem porta.

### Configurando CI com Buddy

Para fazer a Integração Contínua pode ser usado várias ferramentas como o [CodeShip](../ci-cd/codeship.md), [CircleCI](../ci-cd/circleci.md) e [Travis CI](../ci-cd/travis-ci.md).

Neste caso, será usado o Buddy que atende de uma maneira bem simples.

Clique [aqui](../ci-cd/buddy.md) e siga `Criar um projeto`.

Quando chegar na parte de selecionar `Buddy's SSH key`, irá aparecer dois comandos que deverão ser executados dentro do usuário que foi criado (ex: `deploy`).

Se ocorrer um erro ao executar, siga os procedimentos abaixo para criar uma pasta na raíz com o nome `.ssh`:

- Logado com o usuário `deploy`, ir para a pasta Home:

  ```
  cd ~
  ```

- Ir para a pasta raíz do usuário `deploy`:

  ```
  cd /home/deploy/
  ```

- Criar pasta `.ssh`:

  ```
  mkdir .ssh
  ```

E execute os dois comandos.
