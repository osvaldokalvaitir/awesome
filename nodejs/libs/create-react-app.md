# Create React App

Cria aplicativos ReactJS sem configuração de compilação.

## Documentação

Clique [aqui](https://github.com/facebook/create-react-app) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/create-react-app) para fazer a instalação.

Instalar globalmente:

```
npm install --global create-react-app | yarn global add create-react-app
```

Criação de novo projeto:

```
npx create-react-app nome_app | yarn create react-app nome_app
```

## Execução de Projeto para Desenvolvimento no ReactJS

Executar o projeto para desenvolvimento (incluindo internamente o Nodemon):

```
npm start | yarn start
```

## Construção e Execução de Projeto para Produção no ReactJS

Construir e executar o projeto para produção:

```
npm run build | yarn run build
```

## Execução de Testes de Projeto no ReactJS

Executar testes no projeto:

```
npm test | yarn test
```

Executar testes e mostrar um relatório detalhado:

```
npm test --coverage | yarn test --coverage
```

Obs: Nos testes executados não apareceu nenhum arquivo no Coverage Report, aparece se eu executar o comando:

```
npm test --coverage --watchAll | yarn test --coverage --watchAll
```