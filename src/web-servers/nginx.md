# Nginx

Nginx é um servidor HTTP e proxy reverso, bem como um servidor para proxy de email IMAP/POP3. O Nginx é um servidor web rápido, leve, e com inúmeras possibilidades de configuração para melhor performance.

Tudo o que o bom e tradicional Apache faz, ele também fará, porém, muito mais rápido.

No Nginx, todo o caminho operado pela conexão de rede é “non-blocking”. O ponto a destacar, aqui, é que além de ser mais eficiente, ele exige menos recursos.

Tecnicamente falando, ele consome menos memória do que o Apache. Isso acontece devido aos seus diferentes conceitos. O Nginx é baseado no modelo “event-based server”; já o Apache, por sua vez, no “process-based server”.

## Documentação e Download

Clique [aqui](http://nginx.org) para ver a documentação e realizar o download.

## Instalação

- **Linux**

  Para instalar o Nginx, execute o seguinte comando:

  ```
  apt install nginx
  ```

  Talvez seja necessário digitar `Y` para continuar a instalação.

## Setar Arquivo de Configuração

- **Linux**

  Para entrar no arquivo de configuração:

  ```
  vim /etc/nginx/sites-available/default
  ```

  Apagar todo o conteúdo deste arquivo:

  ```
  dG
  ```

  Para dar insert no arquivo:

  ```
  i
  ```

  - Projeto Node.js

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

    Obs: Esta é a configuração da [DigitalOcean](../servers/digitalocean.md), para outros servidores, precisa pesquisar.

  - Projeto ReactJS

    Adicionar as seguintes linhas no arquivo:

    ```
    upstream node {
      server 127.0.0.1:8080;
      keepalive 64;
    }

    server {
      listen 80;
      # server_name domain.com;
      root <caminho_projeto_reactjs>;

      location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header Host $http_host;
        proxy_set_header X-NginX-Proxy true;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection “upgrade”;
        proxy_max_temp_file_size 0;
        proxy_pass http://node/;
        proxy_redirect off;
        proxy_read_timeout 240s;
      }
    }
    ``` 

    Ex: `root /home/deploy/goreact-deploy;`

    Obs: Este arquivo é padrão, só não esquecer de alterar a linha do `root` com o caminho de instalação do projeto ReactJS.

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