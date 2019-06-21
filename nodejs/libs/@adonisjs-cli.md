# AdonisJs Cli

A interface de linha de comando (CLI) do AdonisJs. Adonis cli é construído sobre Adonis ace e ajuda você a desenvolver novos projetos Adonisjs.

## Documentação

Clique [aqui](https://github.com/adonisjs/adonis-cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/@adonisjs/cli) para fazer a instalação.

Instalar globalmente:

```
npm install --global @adonisjs/cli | yarn global add @adonisjs/cli
```

## Execução de API para Desenvolvimento

Executar a API para desenvolvimento:

```
adonis serve --dev
```

Obs: O parâmetro `--dev` ativa o Nodemon.

## Execução de API para Produção

Executar a API para produção:

```
adonis serve
```

## Execução de Ouvinte de Fila

Executar o ouvinte [Adonis Kue Provider](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/adonis-kue.md), é necessário tê-lo instalado antes:

```
adonis kue:listen
```

## Comandos do CLI

Exibir uma lista de comandos possíveis:

```
adonis
```

Criar projeto:

```
adonis new nome_app tipo_app
```

Exemplo de criação de projeto que tem somente os recursos de uma api:

```
adonis new NomeProjeto --api-only
```

O parâmetro `-h` depois de comandos, mostra as opções disponíveis do comando:

```
adonis new -h
```

Executar a API do Adonis:

```
adonis serve --dev
```

Obs: O parâmetro `--dev` ativa o Nodemon para o desenvolvimento e em produção não será necessário colocar este parâmetro.

Criar migrations pendentes no banco de dados:

```
adonis migration:run
```

Desfazer as migrations:

```
adonis migration:rollback
```

Criar controller:

```
adonis make:controller NomeController
```

Selecione a opção: `For HTTP requests`.

Exibir a lista de rotas:

```
adonis route:list
```

Criar model:

```
adonis make:model NomeModel -m -c
```

Onde: `-m` cria a migration e `-c` cria o controller do model

Criar validator:

```
adonis make:validator NomeValidator
```

Criar ehandler:

```
adonis make:ehandler
```

Criar hook:

```
adonis make:hook NomeHook
```

Instalando a biblioteca [Adonis Kue Provider](https://github.com/osvaldokalvaitir/projects-settings/blob/master/nodejs/libs/adonis-kue.md), aparecem dois novos comandos que podem ser utilizados:

Criar job:

```
adonis make:job NomeJob
```

Executar ouvinte:

```
adonis kue:listen
```
