# Code Spell Checker

Um corretor ortográfico básico que funciona bem com o código camelCase.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{
  // Configurações do Code Spell Checker
  "cSpell.enableFiletypes": [
    "!asciidoc",
    "!c",
    "!cpp",
    "!csharp",
    "!go",
    "!handlebars",
    "!haskell",
    "!jade",
    "!java",
    "!latex",
    "!php",
    "!pug",
    "!python",
    "!restructuredtext",
    "!rust",
    "!scala",
    "!scss"
  ],
}
```