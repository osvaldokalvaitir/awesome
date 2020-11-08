# Commitizen

O utilitário de linha de comando commitizen.

## Documentação

Clique [aqui](https://github.com/commitizen/cz-cli) para ver a documentação.

## Instalação

Antes é necessário instalar o [ESLint](eslint.md).

Clique [aqui](https://www.npmjs.com/package/commitizen) para fazer a instalação.

Instalar como dependência de desenvolvimento:

```
npm install commitizen --save-dev | yarn add commitizen --dev
```

## Comandos do CLI

Depois de instalar, inicialize seu projeto para usar o adaptador cz-conventional-changelog:  

```
npm commitizen init cz-conventional-changelog --save-dev --save-exact
```

ou:

```
yarn commitizen init cz-conventional-changelog --yarn --dev --exact
```