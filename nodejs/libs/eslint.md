# ESLint

Ferramenta para identificar e relatar padrões em JavaScript. Se o projeto for em Node é recomendado a utilização do guia de estilo `Standard` e se for em React o guia de estilo do [AirBnB](https://www.npmjs.com/package/eslint-config-airbnb-base).

## Documentação

Clique [aqui](https://github.com/eslint/eslint) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/eslint) para fazer a instalação.

Instalar como dependência de desenvolvimento:

```
npm install eslint --save-dev | yarn add eslint --dev
```

É necessário setar um arquivo de configuração com o comando:

```
npx eslint --init | yarn eslint --init
```

## Erro

Se o projeto for criado com [create-react-app](create-react-app.md), não usar esta biblioteca de instalação. Instalar a lib [eslint-config-airbnb](eslint-config-airbnb.md) e suas dependências.
