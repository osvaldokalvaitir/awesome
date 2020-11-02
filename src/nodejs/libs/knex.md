# knex.js

Um query builder para PostgreSQL, MySQL e SQLite3, projetado para ser flexível, portátil e divertido de usar.

## Documentação

Clique [aqui](https://github.com/knex/knex) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/knex) para fazer a instalação.

## Comandos do CLI

É necessário criar um arquivo de configuração de nome `knexfile` para rodar alguns comandos.

Criar migrations pendentes no banco de dados:

```
npx knex --knexfile knexfile.ts migrate:latest | yarn knex --knexfile knexfile.ts migrate:latest
```

Criar seed:

```
npx knex --knexfile knexfile.ts seed:run | yarn knex --knexfile knexfile.ts seed:run
```