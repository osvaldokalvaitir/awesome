# sequelize-cli

A interface de linha de comando (CLI) do Sequelize.

## Documentação

Clique [aqui](https://github.com/sequelize/cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/sequelize-cli) para fazer a instalação.

Instalar como dependência de desenvolvimento e globalmente:

```
npm install sequelize-cli --save-dev -g | yarn global add sequelize-cli --dev
```

É necessário instalar também o [sequelize](sequelize.md).

## Comandos do CLI

Iniciar o sequelize no projeto, criando as pastas `config`, `models`, `migrations` e `seeders`:

```
npx sequelize init | yarn sequelize init
```

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
