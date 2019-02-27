# Visual Studio Code

Editor de código-fonte que inclui suporte para depuração, realce de sintaxe, complementação inteligente de código, snippets, entre outros.

## Documentação e Instalação

Clique [aqui](https://code.visualstudio.com) para ver a documentação e fazer a instalação.

## Fonte

### Instalação

- [Fira Code](../../font/fira-code.md)

### Configuração

Depois de instalar a fonte, setar as configurações (Settings > Open settings.json):

```
{
  // Configura a família da fonte
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures":true,
}
```

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
- [Rocketseat React Native](rocketseat-react-native.md)
- [Rocketseat ReactJS](rocketseat-reactjs.md)
- [Todo Tree](extensions/todo-tree.md)
- [Todo+](extensions/todo-plus.md)
- [VS Live Share](extensions/vs-live-share.md)
- [VSCode Icons](extensions/vscode-icons.md)
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

  // Desabilita o hint de documentação
  "editor.parameterHints.enabled": false,

  // Tamanho da tabulação
  "editor.tabSize": 2,

  // Configura o tamanho fonte
  "editor.fontSize":18,
  "editor.lineHeight":24,

  // Formatar ao salvar
  "editor.formatOnSave": true,

  // Guias auxiliares de navegação
  "breadcrumbs.enabled": true,

  // Define se o Html sugere tags Html5
  "html.suggest.html5": true,

  // Aumenta a fonte do terminal
  "terminal.integrated.fontSize":14,

  // Auto complete de javascript em arquivos jsx
  "emmet.syntaxProfiles": {
    "javascript": "jsx"
  },

  // Inclui a linguagem do javascript react e html nos arquivos nunjucks
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "nunjucks": "html"
  },

  // Nunca atualiza os imports ao mover o arquivo
  "javascript.updateImportsOnFileMove.enabled": "never",



  // Configurações que precisam de fonte e extensões

  // Configura a família da fonte
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures": true,

  // Define o tema do VSCode
  "workbench.colorTheme": "Dracula",

  // Define o tema dos ícones na sidebar
  "workbench.iconTheme": "vscode-icons",

  // Define a integração do Prettier com o ESLint
  "prettier.eslintIntegration": true
}
```
