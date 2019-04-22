# Ubuntu

Ubuntu é um sistema operacional de código aberto, construído a partir do núcleo Linux, baseado no Debian e utiliza GNOME como ambiente de desktop de sua mais recente versão com suporte de longo prazo.

## Documentação e Download

Clique [aqui](https://www.ubuntu.com/download) para ver a documentação e realizar o download.

## Criando Servidor

Depois de contratar um provedor de servidores na nuvem como [DigitalOcean](../server/digitalocean.md), [Amazon Web Services](../server/amazon-web-services.md) ou outro. É possível criar um servidor linux Ubuntu, que depois de criado, é disponibilizado um ip para o acesso nele.

Dentro do Ubuntu, é possível executar todos os comandos abaixo independente do servidor de nuvem contratado.

Para começar acesse o servidor por SSH com usuário `root`.

### Instalação do [Node.js](./nodejs/nodejs.md)

Acesse o site `https://github.com/nodesource/distributions/blob/master/README.md#deb` que é o redirecionamento do site do Node.js.

Em `Installation instructions`, encontre a versão do Node.js que deseja instalar e copie as linhas referentes ao Ubuntu.

Ex:
```
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
sudo apt-get install -y nodejs
```

Execute no terminal uma linha de cada vez.

Depois de concluir a instalação.

Para ver a versão do node:

```
node -v
```

Para ver a versão do npm:

```
npm -v
```

Caso tenha uma versão da npm mais atualizada é possível atualizar com o comando:

```
sudo npm i -g npm
```

Para verificar se atualizou para a mais recente:

```
npm -v
```

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

Logar com o novo usuário:

```
sudo su deploy
```

### Clone do projeto

Ir para a pasta Home do usuário `deploy`:

```
cd ~
```

Listar o conteúdo da pasta atual:

```
ls
```

Para clonar o repositório do GitHub:

```
git clone <nome_do_repositório>
```

Obs: Se for público dá para copiar o caminho com o HTTPS, mas se for privado tem que copiar o SSH.

Ver se o conteúdo foi clonado:

```
ls
```

Para entrar na pasta criada pelo Git:

```
cd <nome_do_repositório>/
```

Ver o conteúdo da pasta:

```
ls
```

### Instalação das dependências do projeto

O projeto não vem com a pasta `node_modules` e o arquivo `env`. Precisaremos fazer a instalação e criar o arquivo de configurações.

Para instalar os módulos:

```
npm install
```

Para ver se a pasta `node_modules` apareceu:

```
ls
```

Antes de criar o arquivo `env`, precisamos instalar o MongoDB.

### Instalação do [MongoDB](./database/mongodb/mongodb.md)

Execute os próximos comando como o root.

Para sair do usuário logado:

```
exit
```

Entre no site [Install MongoDB Community Edition on Ubuntu](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu).

Siga os procedimentos do tópico `Install MongoDB Community Edition using .deb Packages`:

  - Copie o comando do item 1 `Import the public key used by the package management system.` e execute no terminal:
    Ex: `sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4`

  - Copie o comando do item 2 `Create a list file for MongoDB.` e execute no terminal:
    Ex: `echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list`

  - Copie o comando do item 3 `Reload local package database.` e execute no terminal:
    Ex: `sudo apt-get update`

  - Copie o comando do item 4 `Install the MongoDB packages.` e execute no terminal:
    Ex: `sudo apt-get install -y mongodb-org`

Siga os procedimentos do tópico `Run MongoDB Community Edition`:

  - Copie o comando do item 1 `Start MongoDB.` e execute no terminal:
    Ex: `sudo service mongod start`

  - Para ver se o mongodb está funcionando, copie o endereço do item 2 `Verify that MongoDB has started successfully` e acesse no terminal:
    Ex: `cat /var/log/mongodb/mongod.log`

  - Na última linha do arquivo tem que aparecer `waiting for connections on port 27017` que significa que o MongoDB está funcionando.

Agora voltamos para o nosso usuário deploy:

```
sudo su deploy
```

### Criação do arquivo env

Ir para a pasta Home do usuário `deploy`:

```
cd ~
```

Entrar na pasta do projeto:

```
cd <nome_do_repositório>/
```

Listar o conteúdo da pasta atual:

```
ls
```

Para criar o arquivo de configurações `env`:

```
vim .env
```

Coloque todas as variáveis ambientes neste arquivo:

Ex: `DB_URL=mongodb://localhost/<nome_do_banco>`

Obs: Se a porta for 27017 que é a padrão do MongoDB, então, não precisa especificar ela.

Para salvar o arquivo e sair:

```
:wq
```

### Rodar a aplicação

Para rodar a aplicação:

```
node index.js
```

Copie o IP de acesso ao servidor e faça um teste no Insomnia. 

Obs: A aplicação ainda está na porta `3000`.

Pode parecer um erro no terminal do servidor, mas é por causa que no código-fonte ocorre o envio de e-mail, e como não foi configurado o servidor de e-mail, aparecerá um erro.

Pode ser configurado qualquer um dos serviços de e-mail: [SparkPost](../email/sparkpost.md), [Mailgun](../email/mailgun.md), [SendGrid](../email/sendgrid.md) ou outro.

### Instalação do [PM2](./nodejs/libs/pm2.md)

Para instalar o PM2:

```
sudo npm install -g pm2
```

Ir para a pasta Home do usuário `deploy`:

```
cd ~
```

Entrar na pasta do projeto:

```
cd <nome_do_repositório>/
```

Listar o conteúdo da pasta atual:

```
ls
```

Iniciar servidor com o PM2:

```
pm2 start index.js
```

Obs: O PM2 não bloqueia o terminal.

Para visualizar a lista que o PM2 está rodando:

```
pm2 list
```

Para aparecer a tela de monitoramento do PM2:

```
pm2 monit
```

Obs: Os `console.log` apareceram nesta tela.

Para iniciar o PM2 quando o Ubuntu ligar:

```
pm2 startup ubuntu
```

Aparecerá um comando no terminal, copie este comando e execute no terminal.

Para reiniciar o servidor manualmente, primeiro execute o `pm2 list`, veja o nome do arquivo no `App name` e depois para reiniciar:

```
pm2 restart <nome_do_arquivo>
```

Ex: `pm2 restart index`

### Configuração do Proxy do [Nginx](./web-server/nginx.md)

O Node.js só aceita uma aplicação Node.js na porta 80, então usamos o Nginx para fazer o gerenciamento da porta.

Voltar para usuário de root:

```
exit
```

Instalar o Nginx:

```
apt install nginx
```

Talvez seja necessário digitar um `Y` para continuar a instalação.

Para entrar no arquivo de configuração:

```
vim /etc/nginx/sites-available/default
```

Apagar todo o conteúdo deste arquivo:

```
dG
```

Adicionar as seguintes linhas no arquivo:

```
server {
	    listen 80;

	    server_name _;

	    location / {
	             proxy_pass http://locahost:3000;
	             proxy_http_version 1.1;
	             proxy_set_header Upgrade $http_upgrade;
	             proxy_set_header Connection 'upgrade';
	             proxy_set_header Host $host;
	             proxy_cache_bypass $http_upgrade;
	    }
}
```

Obs: Esta é a configuração da DigitalOcean.

Salvar o arquivo e sair:

```
:wq
```

Para verificar se o arquivo de configuração está correto:

```
nginx -t
```

Reinicie o Nginx:

```
sudo service nginx restart
```

Agora, faça um teste no Insomnia usando a porta 80.