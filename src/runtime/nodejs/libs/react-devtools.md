# react-devtools

Se você precisar depurar uma página do React em algum lugar diferente do Chrome no desktop (um navegador para dispositivos móveis, uma visualização da Web incorporada, Safari, etc.), o pacote react-devtools é para você! Também é útil se seu aplicativo estiver dentro de um iframe. Ele funciona tanto com o React DOM quanto com o React Native.

## Documentação

Clique [aqui](https://github.com/facebook/react-devtools) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-devtools) para fazer a instalação.

Instalar como dependência de desenvolvimento:

```
npm install react-devtools --save-dev | yarn add react-devtools --dev
```

## Execução do react-devtools

Para usar o react-devtools, no seu arquivo `index.js` ou em qualquer lugar antes de exibir o primeiro componente da aplicação defina o seguinte trecho de código:

```
if (__DEV__) {
  require('react-devtools');
}
```

Obs: A variável global `__DEV__` no React Native indica quando você está em ambiente de desenvolvimento.  

No package.json adicione o script:

```
"scripts": {
  "react-devtool": "react-devtools"
},
```

Para executar o script:

```
npm run react-devtool | yarn run react-devtool
```
