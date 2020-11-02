# sequelize-cli

A interface de linha de comando (CLI) do Sequelize.

## Documentação

Clique [aqui](https://github.com/sequelize/cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/sequelize-cli) para fazer a instalação.

Instalar como dependência de desenvolvimento e globalmente:

```
npm install --global sequelize-cli --save-dev | yarn global add sequelize-cli --dev
```

É necessário instalar também o [sequelize](sequelize.md).

## Comandos do CLI

Iniciar o sequelize no projeto, criando as pastas `config`, `models`, `migrations` e `seeders`:

```
npx sequelize init | yarn sequelize init
```

Criar migration:

```
npx sequelize migration:create --name=<create-nome_tabela> | yarn sequelize migration:create --name=<create-nome_tabela>
```

Onde:

- `<create-nome_tabela>` - nome da migration. Ex: `create-users`

Criar migrations pendentes no banco de dados:

```
npx sequelize db:migrate | yarn sequelize db:migrate
```

Desfazer a última migration:

```
npx sequelize db:migrate:undo | yarn sequelize db:migrate:undo
```

Desfazer todas as migrations:

```
npx sequelize db:migrate:undo:all | yarn sequelize db:migrate:undo:all
```

Criar seed:

```
npx sequelize seed:generate --name=<create-nome_tabela> | yarn sequelize seed:generate --name=<create-nome_tabela>
```

ou

```
npx sequelize seed:create --name=<create-nome_tabela> | yarn sequelize seed:create --name=<create-nome_tabela>
```

Onde:

- `<create-nome_tabela>` - nome da seed. Ex: `create-users`

Criar seed especificado no banco de dados:

```
npx sequelize db:seed | yarn sequelize db:seed
```

Criar todos os seeds no banco de dados:

```
npx sequelize db:seed:all | yarn sequelize db:seed:all
```

Desfazer o último seed, deletando os dados da tabela:

```
npx sequelize db:seed:undo | yarn sequelize db:seed:undo
```

Desfazer todos os seeds, deletando os dados da tabela:

```
npx sequelize db:seed:undo:all | yarn sequelize db:seed:undo:all
```