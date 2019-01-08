# Visual Studio Code

Editor de código-fonte que inclui suporte para depuração, realce de sintaxe, complementação inteligente de código, snippets, entre outros.

## Documentação e Instalação

Clique [aqui](https://code.visualstudio.com) para ver a documentação e fazer a instalação.

## Fonte

- [Fira Code](fonts/fira-code.md)

## Extensões

- [Color Highlight](extensions/color-highlight.md)
- [DotEnv](extensions/dotenv.md)
- [Dracula Official](extensions/dracula-official.md)
- [EditorConfig for VS Code](extensions/editorconfig-for-vs-code.md)
- [ESLint](extensions/eslint.md)
- [Markdown All in One](extensions/markdown-all-in-one.md)
- [Material Icon Theme](extensions/material-icon-theme.md)
- [Nunjucks](extensions/nunjucks.md)
- [Prettier - Code formatter](extensions/prettier-code-formatter.md)
- [Todo Tree](extensions/todo-tree.md)
- [Todo+](extensions/todo-plus.md)
- [VS Live Share](extensions/vs-live-share.md)
- [VSCode Styled-Components](extensions/vscode-styled-components.md)

## Todas as Configurações

Depois de adicionar a fonte e as extensões, setar as configurações (Settings > Open settings.json):

```
{
  // Aplica linhas verticais para lembrar de quebrar linha em códigos muito grandes
  "editor.rulers": [
    80,
    120
  ],

  // Aplica um sinal visual na esquerda da linha selecionada
  "editor.renderLineHighlight":"gutter",

  // Configura o tamanho fonte
  "editor.fontSize":16,
  "editor.lineHeight":24,

  // Formatar ao salvar
  "editor.formatOnSave": true,

  // Guias auxiliares de navegação
  "breadcrumbs.enabled": true,

  // Formatar JavaScript
  "javascript.format.enable": false,

  // Define se o Html sugere tags Html5
  "html.suggest.html5": true,

  // Aumenta a fonte do terminal
  "terminal.integrated.fontSize":14,


  // Configurações que precisam de fonte e extensões

  // Configura a família da fonte
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures":true,

  // Define o tema do VSCode
  "workbench.colorTheme":"Dracula",

  // Define o tema dos ícones na sidebar
  "workbench.iconTheme":"material-icon-theme",

  // ESLint
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,

  // Define a integração do Prettier com o ESLint
  "prettier.eslintIntegration": true,

  // Inclui html nos arquivos nunjucks
  "emmet.includeLanguages": {
    "nunjucks": "html"
  }
}
```
