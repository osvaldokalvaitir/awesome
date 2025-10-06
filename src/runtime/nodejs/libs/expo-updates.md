# expo-updates

Biblioteca que permite que aplicativos Expo e React Native recebam atualizações over-the-air (OTA) diretamente dos servidores, permitindo correções de bugs e novos recursos sem passar pela App Store.

## Documentação

Clique [aqui](https://docs.expo.dev/versions/latest/sdk/updates) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/expo-updates) para fazer a instalação.

Instalar a biblioteca:

```
expo install expo-updates
```

Ou com npm:

```
npm install expo-updates
```

## Configuração

Configurar no arquivo app.json ou app.config.js:

```
{
  "expo": {
    "updates": {
      "url": "https://u.expo.dev/[project-id]"
    }
  }
}
```

## Comandos Principais

Verificar atualizações:

```
import * as Updates from 'expo-updates';

await Updates.checkForUpdateAsync();
```

Baixar e aplicar atualizações:

```
await Updates.fetchUpdateAsync();
await Updates.reloadAsync();
```