# Intl.js

Implementação de compatibilidade da API de internacionalização do ECMAScript (ECMA-402) para JavaScript.

## Documentação

Clique [aqui](https://github.com/andyearnshaw/Intl.js) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/intl) para fazer a instalação.

## Erro

Ao usar algumas bibliotecas que utilizam internacionalização, ocorreu o erro `Can't find variable: intl`, não encontrando a variável `Intl`. Isso foi resolvido instalando esta biblioteca e colocando no topo do app (pode ser embaixo da importação do React), o seguinte código:

```
import React from 'react';

import 'intl';
import 'intl/locale-data/jsonp/pt-BR';
```

Clique [aqui](https://stackoverflow.com/questions/41736735/react-native-and-intl-polyfill-required-on-android-device/41935101#41935101) para mais detalhes sobre o erro.