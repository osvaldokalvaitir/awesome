# ESLint

Ferramenta para identificar e relatar padrões em JavaScript. Se o projeto for em Node é recomendado a utilização do guia de estilo 'Standard' e se for em React o guia de estilo do [AirBnB](https://www.npmjs.com/package/eslint-config-airbnb-base).

## Documentação

Clique [aqui](https://github.com/eslint/eslint) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/eslint) para fazer a instalação.

Depois de realizar a instalação pelo comando abaixo:

```
npm install eslint --save-dev | yarn add eslint -D
```

É necessário setar um arquivo de configuração com o comando:

```
npx eslint --init
```

Só é possível instalar o ESLint com o NPM, então depois que terminar a instalação e configuração, delete o arquivo 'package-lock.json' e execute o comando abaixo para instalar as dependências com o yarn:

```
yarn
```
