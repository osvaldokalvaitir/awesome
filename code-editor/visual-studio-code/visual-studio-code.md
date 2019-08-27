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
  // Configura o tamanho e a família da fonte
  "editor.fontSize":18,
  "editor.lineHeight":24,
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures": true,
}
```

## Extensões

- [Color Highlight](extensions/color-highlight.md)
- [DotEnv](extensions/dotenv.md)
- [Dracula Official](extensions/dracula-official.md)
- [Edge Template Support](extensions/edge-template-support.md)
- [EditorConfig for VS Code](extensions/editorconfig-for-vs-code.md)
- [ESLint](extensions/eslint.md)
- [GitLens - Git supercharged](extensions/gitlens-git-supercharged.md)
- [GraphQL](extensions/graphql.md)
- [Live Server](extensions/live-server.md)
- [Live Share](extensions/live-share.md)
- [Markdown All in One](extensions/markdown-all-in-one.md)
- [Material Icon Theme](extensions/material-icon-theme.md)
- [Nunjucks](extensions/nunjucks.md)
- [Prettier - Code formatter](extensions/prettier-code-formatter.md)
- [Rocketseat React Native](rocketseat-react-native.md)
- [Rocketseat ReactJS](rocketseat-reactjs.md)
- [Todo Tree](extensions/todo-tree.md)
- [Todo+](extensions/todo-plus.md)
- [VSCode Icons](extensions/vscode-icons.md)
- [VSCode Styled-Components](extensions/vscode-styled-components.md)

## Todas as Configurações

Depois de adicionar a fonte e as extensões, setar as configurações (Settings > Open settings.json):

```
{
  // Um novo arquivo em branco não é mais aberto na inicialização
  "workbench.startupEditor": "newUntitledFile",

  // Zoom
  "window.zoomLevel": 0,

  // Habilita recomendações de extensões
  "extensions.ignoreRecommendations": false,

  // Desabilita a confirmação ao arrastar-e-soltar
  "explorer.confirmDragAndDrop": false,

  // Desabilita a confirmação ao deletar
  "explorer.confirmDelete": false,

  // Aplica linhas verticais para lembrar de quebrar linha
  "editor.rulers": [80, 120],
  "editor.formatOnSave": false,

  // Aplica um sinal visual na esquerda da linha selecionada
  "editor.renderLineHighlight":"gutter",

  // Desabilita o hint de documentação
  "editor.parameterHints.enabled": false,

  // Tamanho da tabulação
  "editor.tabSize": 2,

  // Guias auxiliares de navegação
  "breadcrumbs.enabled": true,

  // Aumenta a fonte do terminal
  "terminal.integrated.fontSize":14,

  // Terminal padrão no OSX
  "terminal.integrated.shell.osx": "/bin/zsh",

  // Terminal padrão no Windows
  "terminal.integrated.shell.windows": "C:\\Windows\\System32\\cmd.exe",

  // Auto complete de javascript em arquivos jsx
  "emmet.syntaxProfiles": {
    "javascript": "jsx"
  },

  // Inclui a linguagem do javascriptreact nos arquivos html do nunjucks
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "nunjucks": "html"
  },

  // Nunca atualiza os imports ao mover o arquivo
  "javascript.updateImportsOnFileMove.enabled": "never",

  // Commitar todas as alterações quando não houver alterações em etapas
  "git.enableSmartCommit": true,

  // Configuração do Typescript
  "typescript.tsserver.log": "verbose",
  "typescript.updateImportsOnFileMove.enabled": "never",



  // Configurações que precisam de fonte e extensões

  // Configura o tamanho e a família da fonte
  "editor.fontSize":18,
  "editor.lineHeight":24,
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures": true,

  // Define o tema do VSCode
  "workbench.colorTheme": "Dracula",

  // Define o tema dos ícones na sidebar
  "workbench.iconTheme": "material-icon-theme",

  // Define a integração do Prettier com o ESLint (_DESCONTINUADO_)
  "prettier.eslintIntegration": true,

  // Define a configuração do ESLint ao salvar
  "eslint.autoFixOnSave": true,
  "eslint.validate": [
    {
      "language": "javascript",
      "autoFix": true
    },
    {
      "language": "javascriptreact",
      "autoFix": true
    },
    {
      "language": "typescript",
      "autoFix": true
    },
    {
      "language": "typescriptreact",
      "autoFix": true
    },
  ],  

  // Configurações do GitLens
  "gitlens.codeLens.recentChange.enabled": false,
  "gitlens.codeLens.authors.enabled": false,
  "gitlens.codeLens.enabled": false,

  // Configuração do Live Share
  "liveshare.featureSet": "insiders",
}
```

## Atalhos do teclado

Para ver todos os atalhos, dê um `Ctrl + Shift + P` para abrir a barra de pesquisa e digite `Open Keyboard Shortcuts`.  

Os principais atalhos são:

```
Ctrl + D
Seleciona o próximo texto igual

Alt + clica
Posiciona vários cursores em vários lugares para digitar

Alt + Up/Down
Move a linha inteira

Ctrl + ;
Transforma a linha num comentário

Shift + Alt + Up/Down
Copia a linha inteira

Ctrl + X
Recorta a linha inteira

Ctrl + Shift + '
Abre o terminal
```