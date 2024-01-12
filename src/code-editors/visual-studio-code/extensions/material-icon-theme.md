# Material Icon Theme

Utilizado para exibir os ícones de acordo com a linguagem utilizada na barra lateral.

Obs: Uma outra opção seria a extensão [VSCode Icons](vscode-icons.md).

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{
  // Define o tema dos ícones de arquivos
  "workbench.iconTheme": "material-icon-theme",

  "material-icon-theme.folders.associations": {
    "infra": "app",
    "entities": "class",
    "domain": "class",
    "schemas": "class",
    "typeorm": "database",
    "repositories": "mappings",
    "http": "container",
    "migrations": "tools",
    "modules": "components",
    "implementations": "core",
    "dtos": "typescript",
    "fakes": "mock",
    "websockets": "pipe",
    "protos": "pipe",
    "grpc": "pipe",
    "providers": "include",
    "subscribers": "messages",
    "useCases": "controller",
    "kafka": "scripts",
    "mappers": "meta",
    "_shared": "shared",
    "eslint-config": "tools",
    "kube": "kubernetes"
  },
  "material-icon-theme.files.associations": {
    "ormconfig.json": "database",
    "tsconfig.json": "tune",
    "*.proto": "3d",
    "*.webpack.js": "webpack"
  },
  "material-icon-theme.languages.associations": {
    "dotenv": "tune"
  },
  "material-icon-theme.activeIconPack": "nest",
}
```