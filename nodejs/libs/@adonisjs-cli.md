# AdonisJs Cli

A interface de linha de comando (CLI) do AdonisJs. Adonis cli é construído sobre Adonis ace e ajuda você a desenvolver novos projetos Adonisjs.

## Documentação

Clique [aqui](https://github.com/adonisjs/adonis-cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/@adonisjs/cli) para fazer a instalação.

Instalar globalmente:

```
npm install -g @adonisjs/cli | yarn global add @adonisjs/cli
```

## Comandos do CLI

Criação de novo projeto:

```
adonis new nome_app tipo_app
```

Exibição de uma lista de comandos possíveis:

```
adonis
```

O parâmetro `-h` depois de comandos, mostra as opções disponíveis do comando:

```
adonis new -h
```

Iniciar servidor:

```
adonis serve --dev
```

Obs: O parâmetro `--dev` ativa o Nodemon para o desenvolvimento e em produção não será necessário colocar este parâmetro.

Criar as migrations no banco de dados:

```
adonis migration:run
```

Desfazer as migrations:

```
adonis migration:rollback
```

Criar um controller:

```
adonis make:controller nome_controller
```

Selecione a opção: `For HTTP requests`.

Exibir a lista de rotas:

```
adonis route:list
```
