# Remote Redux DevTools

Use Redux DevTools remotamente para aplicativos React Native com Redux, híbridos, de desktop e de servidor.

## Documentação

Clique [aqui](https://github.com/zalmoxisus/remote-redux-devtools) para ver a documentação.

## Instalação

Antes é necessário instalar o [RemoteDev Server](remotedev-server.md).

Clique [aqui](https://www.npmjs.com/package/remote-redux-devtools) para fazer a instalação.

Instalar como dependência de desenvolvimento:

```
npm install remote-redux-devtools --save-dev | yarn add remote-redux-devtools --dev
```

## Execução do Remote Redux DevTools

Para usar o Remote Redux DevTools, é necessário configurá-lo, para isso, tem duas configurações, caso você não use nenhum dos middlewares: Redux Thunk, Saga ou Logger, use a primeira opção, senão a segunda opção.

Primeira opção:
```
import { createStore } from 'redux';
import devToolsEnhancer from 'remote-redux-devtools';

const store = createStore(reducer, devToolsEnhancer());
```

Segunda opção:
```
import { createStore, applyMiddleware } from 'redux';
import { composeWithDevTools } from 'remote-redux-devtools';

const middleware = [thunk, saga, etc];
const compose = composeWithDevTools({ realtime: true });
const store = createStore(reducer, compose(
  applyMiddleware(...middleware),
));
```

No package.json adicione o script:

```
"scripts": {
  "redux-devtool": "remotedev"
},
```

Para executar o script:

```
npm run redux-devtool | yarn run redux-devtool
```
