# Todo Tree

Essa extensão procura rapidamente por tags de comentários como TODO e FIXME, e as exibe em uma árvore no menu lateral.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{
  // Configurações do Todo Tree
  "todo-tree.general.tags": [
    "BUG",
    "HACK",
    "FIXME",
    "TODO",
    "XXX",
    "[ ]",
    "[x]"
  ],
  "todo-tree.regex.regex": "(//|#|<!--|;|/\\*|^|^\\s*(-|\\d+.))\\s*($TAGS)",
}
```
