# Biome

A extensão Biome para o Visual Studio Code oferece suporte completo ao Biome, com formatação automática ao salvar, refatoração de código e sugestões rápidas integradas.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=biomejs.biome) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{
  "[javascript][typescript][javascriptreact][typescriptreact][json][jsonc][css][graphql]": {
    "editor.defaultFormatter": "biomejs.biome"
  },
  "editor.formatOnSave": true,
  "editor.formatOnPaste": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.biome": "explicit",
    "source.organizeImports.biome": "explicit"
  }
}
```