# React Native Gesture Handler

API declarativa expondo o toque nativo da plataforma e o sistema de gestos para o React Native.  
Esta biblioteca é instalada junto com a biblioteca [React Navigation](react-navigation.md).

## Documentação

Clique [aqui](https://github.com/kmagiera/react-native-gesture-handler) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-native-gesture-handler) para fazer a instalação.

Depois da instalação é necessário executar o comando `react-native link` (_DESCONTINUADO_):

```
react-native link react-native-gesture-handler
```

Depois de linkar o componente, para compilar no Android é necessário fazer uma configuração no arquivo `MainActivity.java` em `android > app > src > main > java > com > nome_projeto > MainActivity.java` que podem ser encontrados [aqui](https://kmagiera.github.io/react-native-gesture-handler/docs/getting-started.html) na documentação em `Installation > With React Native app (no Expo) > Android`. No iOS não é necessário nenhuma configuração adicional.
