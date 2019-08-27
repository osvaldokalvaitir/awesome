# react-native-file-viewer

Visualizador de arquivos nativo para React Native. Visualize qualquer tipo de arquivo suportado pelo dispositivo móvel.

## Documentação

Clique [aqui](https://github.com/vinzscam/react-native-file-viewer) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/react-native-file-viewer) para fazer a instalação.

Depois da instalação é necessário executar o comando `react-native link` (_DESCONTINUADO_):

```
react-native link react-native-file-viewer
```

Depois de linkar o componente, para compilar no Android é necessário copiar a pasta `xml` de `node_modules > react-native-file-viewer > android > src > main > res > xml` para `android > app > src > main > res`, e também é necessário fazer uma configuração no arquivo `AndroidManifest.xml` em `android > app > src > main > AndroidManifest.xml` que podem ser encontrados [aqui](https://github.com/vinzscam/react-native-file-viewer) na documentação em `Getting started > Manual installation > Android > 4 e 5`. No iOS não é necessário nenhuma configuração adicional.