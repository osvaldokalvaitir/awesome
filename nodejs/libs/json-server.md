# JSON Server

Obtenha uma API REST completa e falsa com codificação zero em menos de 30 segundos.

## Documentação

Clique [aqui](https://github.com/typicode/json-server) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/json-server) para fazer a instalação.

Instalar globalmente:

```
npm install -g json-server | yarn global add json-server
```

Obs: Ocorreu um erro ao tentar instalar com o yarn, mas foi resolvido instalando com o npm.

## Execução de API no JSON Server

Executar a API do JSON Server:

```
json-server server.json -p 3001 -w -d 500
```

Onde:

- `server.json` - arquivo que contém o json
- `-p 3001` - porta, como a porta padrão é 3000 a mesma do React, então alterar para 3001
- `-w` - watch, que significa que ao alterar o arquivo, não precisa reiniciar o servidor
- `-d 500` - tempo de delay
