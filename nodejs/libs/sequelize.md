# Sequelize

Sequelize é um ORM do Node.js baseado em promessas para Postgres, MySQL, SQLite e Microsoft SQL Server. Possui suporte a transações sólidas, relações, replicação de leitura e muito mais.

## Documentação

Clique [aqui](https://github.com/sequelize/sequelize) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/sequelize) para fazer a instalação.

Depois de realizar a instalação pelo comando abaixo:

```
npm install --save sequelize | yarn add sequelize
```

É necessário instalar a interface de linha de comando (opcional instalar globalmente):

```
npm install sequelize-cli --save-dev -g | yarn global add sequelize-cli -D
```

## Comandos

Criar migration:

```
npx sequelize migration:create --name=create-nome_da_tabela
```

Criar migrations pendentes no banco de dados:

```
npx sequelize db:migrate
```

Desfazer o último comando de migration:

```
npx sequelize:migration:undo
```
