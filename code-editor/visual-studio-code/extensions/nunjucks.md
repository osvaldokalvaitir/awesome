# Nunjucks

Utilizado para ter suporte à sintaxe .njk.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=ronnidc.nunjucks) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{
  // Auto complete de javascript em arquivos jsx
  "emmet.syntaxProfiles": {
    "javascript": "jsx"
  },

  // Inclui a linguagem do javascriptreact nos arquivos html do nunjucks
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "nunjucks": "html"
  },
}
```
