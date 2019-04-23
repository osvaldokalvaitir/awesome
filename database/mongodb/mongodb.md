# MongoDB

MongoDB é um software de banco de dados orientado a documentos livre, de código aberto e multiplataforma, escrito na linguagem C++. Classificado como um programa de banco de dados NoSQL, o MongoDB usa documentos semelhantes a JSON com esquemas.

## Documentação e Instalação

Clique [aqui](https://docs.mongodb.com/manual/administration/install-community) para ver a documentação e fazer a instalação de acordo com seu sistema operacional.

## Instalação

- **Ubuntu**

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