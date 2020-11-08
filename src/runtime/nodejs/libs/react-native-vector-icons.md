# React Native Vector Icons

Pacote de fontes personalizáveis incluindo as famosas FontAwesome, MaterialIcons e Ionicons.

## Documentação

Clique [aqui](https://github.com/oblador/react-native-vector-icons) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-native-vector-icons) para fazer a instalação.

Depois da instalação é necessário executar o comando `react-native link` (_DESCONTINUADO_):

```
react-native link react-native-vector-icons
```

## Erro

Ao instalar a biblioteca sem executar `react-native link`, aparece caracteres estranhos ao invés dos ícones. Isso foi resolvido adicionando o seguinte código no arquivo `android/app/build.gradle`, NÃO confundir com `android/build.gradle` (pode ser embaixo do apply):

```
apply from: "../../node_modules/react-native/react.gradle"

apply from: "../../node_modules/react-native-vector-icons/fonts.gradle"
```

Clique [aqui](https://github.com/oblador/react-native-vector-icons#option-with-gradle-recommended) para mais detalhes sobre o procedimento.
