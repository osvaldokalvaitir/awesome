# JSON Server

Obtenha uma API REST completa e falsa com codificação zero em menos de 30 segundos.

## Documentação

Clique [aqui](https://github.com/typicode/json-server) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/json-server) para fazer a instalação.

Instalar globalmente:

```
npm install --global json-server | yarn global add json-server
```

## Erro

Ocorreu um erro ao tentar instalar com o yarn, mas foi resolvido instalando com o npm.

## Execução de API

Executar a API:

```
json-server <nome_arquivo>
```

Onde:

- `<nome_arquivo>` - arquivo que contém o json. Ex: `server.json`

### Exemplo para ReactJS

```
json-server <nome_arquivo> -p <porta> -w -d <tempo_delay>
```

Onde:

- `<nome_arquivo>` - arquivo que contém o json. Ex: `server.json`
- `-p <porta>` - porta, como a porta padrão é `3000` a mesma do ReactJS, então, alterar para uma outra. Ex: `3001`
- `-w` - watch, que significa que ao alterar o arquivo, não precisa reiniciar o servidor
- `-d <tempo_delay>` - tempo de delay, valor em milissegundos. Ex: `500`.

### Exemplo para React Native com emulação via USB

```
json-server <nome_arquivo> -H <ip_computador>
```

Onde:

- `<nome_arquivo>` - arquivo que contém o json. Ex: `server.json`
- `-H <ip_computador>` - IP do computador, como o padrão é `localhost` e no React Native com emulação via USB não funciona com o IP local, então é necessário alterar o IP. Ex: `192.168.0.102`.
