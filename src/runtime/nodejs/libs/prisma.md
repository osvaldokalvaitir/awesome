# Prisma

Ferramentas de banco de dados inclui ORM, migrations e interface de administração para Postgres, MySQL & MongoDB.

## Documentação

Clique [aqui](https://github.com/prisma/prisma) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/prisma) para fazer a instalação.

Instalar como dependência de desenvolvimento:

```
npm install prisma --save-dev
```

## Comandos do CLI

Configura um arquivo prisma/schema.prisma no diretório atual, passando o provedor de banco de dados como argumento:

```
npx prisma init --datasource-provider sqlite
```

Executar as migrations:

```
npx prisma migrate dev
```

Executar o Prisma Studio:

```
npx prisma studio
```

Enviar as migrations para o banco de dados que está na url (no PlanetScale tem que usar o `push` e não o `migrate`):

```
npx prisma db push
```

Introspecta o banco de dados e gera um modelo de dados a partir dele:

```
npx prisma introspect
```