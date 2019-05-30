# appcenter-cli

A interface de linha de comando (CLI) do Visual Studio App Center.

## Documentação

Clique [aqui](https://github.com/Microsoft/appcenter-cli) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/appcenter-cli) para fazer a instalação.

Instalar globalmente:

```
npm install --global appcenter-cli | yarn global add appcenter-cli
```

## Comandos do CLI

Para fazer o login:

```
appcenter login
```

Aparecerá uma mensagem de coleta de dados e depois a seguinte pergunta:

<sub> Enable telemetry? **No** </sub>

Abrirá no browser a janela `Authentication succeeded` com um token, copie o token.

<sub> Access code from browser: **Cole o token** </sub>

Exibir a lista de aplicativos:

```
appcenter apps list
```

Exibir as chaves do CodePush:

```
appcenter codepush deployment list -a <nome_organizacao>/<nome_app> -k
```

Gerar release:
```
appcenter codepush release-react -a <nome_organizacao>/<nome_app>
```

Usar parâmetro `-d`, para escolher o ambiente de `Staging` ou `Production`, o padrão é staging