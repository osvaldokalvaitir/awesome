# Ubuntu

Ubuntu é um sistema operacional de código aberto, construído a partir do núcleo Linux, baseado no Debian e utiliza GNOME como ambiente de desktop de sua mais recente versão com suporte de longo prazo.

## Documentação e Download

Clique [aqui](https://www.ubuntu.com/download) para ver a documentação e realizar o download.

## Criando Servidor

Depois de contratar um provedor de servidores na nuvem como [DigitalOcean](../server/digitalocean.md), [Amazon Web Services](../server/amazon-web-services.md) ou outro. É possível criar um servidor linux Ubuntu, que depois de criado, é disponibilizado um ip para o acesso nele.

Dentro do Ubuntu, é possível executar todos os comandos abaixo independente do servidor de nuvem contratado.

Para começar acesse o servidor por SSH com usuário `root`.

### Instalação do Node.js

Clique [aqui](./nodejs/nodejs.md) e siga Instalação e Linux usando cURL.

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

Para instalar as dependências:

```
npm install
```

Para ver se a pasta `node_modules` apareceu:

```
ls
```

Antes de criar o arquivo `env`, precisamos instalar o MongoDB.

### Instalação do MongoDB

Execute os próximos comando como o root.

Para sair do usuário logado:

```
exit
```

Clique [aqui](./database/mongodb/mongodb.md) e siga Instalação e Ubuntu.

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

O PM2 pode gerar e configurar um script de inicialização para manter o PM2 e seus processos ativos em todas as reinicializações do servidor.

Para gerar script de inicialização:

```
pm2 startup
```

Ex: `pm2 startup ubuntu`

Aparecerá um comando no terminal, copie este comando e execute no terminal.

Para algumas ações é necessário o `app_name` e para isso execute `pm2 list` e veja o nome do arquivo.

Para reiniciar o servidor:

```
pm2 restart <app_name|id>
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

## Configurando CI com Buddy

Para fazer a Integração Contínua pode ser usado várias ferramentas como o [CodeShip](./ci-cd/codeship.md), [CircleCI](./ci-cd/circleci.md) e [Travis CI](./ci-cd/travis-ci.md).

Neste caso, será usado o Buddy que atende de uma maneira bem simples.

Clique [aqui](./ci-cd/buddy.md) e siga Criar um projeto.

Quando chegar na parte de selecionar `Buddy's SSH key`, irá aparecer dois comandos que deverão ser executados dentro do usuário que foi criado (ex: `deploy`).

Logar novamente com o novo usuário:

```
sudo su deploy
```

Ir para a pasta Home do usuário `deploy`:

```
cd ~
```

Listar o conteúdo da pasta atual:

```
ls
```

Ir para a pasta raíz do usuário `deploy`:

```
cd /home/deploy/
```

Criar pasta `.ssh`:

```
mkdir .ssh
```

Executar os dois comandos.