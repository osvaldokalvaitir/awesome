# Visual Studio Code

Editor de código-fonte que inclui suporte para depuração, realce de sintaxe, complementação inteligente de código, snippets, entre outros.

## Documentação e Instalação

Clique [aqui](https://code.visualstudio.com) para ver a documentação e fazer a instalação.

## Fonte

- [Fira Code](visual-studio-code/fonts/fira-code.md)

## Extensões

- [Color Highlight](visual-studio-code/extensions/color-highlight.md)
- [DotEnv](visual-studio-code/extensions/dotenv.md)
- [Dracula Official](visual-studio-code/extensions/dracula-official.md)
- [EditorConfig for VS Code](visual-studio-code/extensions/editorconfig-for-vs-code.md)
- [ESLint](visual-studio-code/extensions/eslint.md)
- [Markdown All in One](visual-studio-code/extensions/markdown-all-in-one.md)
- [Material Icon Theme](visual-studio-code/extensions/material-icon-theme.md)
- [Nunjucks](visual-studio-code/extensions/nunjucks.md)
- [Prettier - Code formatter](visual-studio-code/extensions/prettier-code-formatter.md)

## Todas as Configurações

Depois de adicionar a fonte e as extensões, setar as configurações (Settings > Open settings.json):

```
{
  // Define o tema do VSCode
  "workbench.colorTheme":"Dracula",

  // Configura tamanho e família da fonte
  "editor.fontSize":16,
  "editor.lineHeight":24,
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures":true,

  // Aplica linhas verticais para lembrar de quebrar linha em códigos muito grandes
  "editor.rulers": [
    80,
    120
  ],

  // Aplica um sinal visual na esquerda da linha selecionada
  "editor.renderLineHighlight":"gutter",

  // Aumenta a fonte do terminal
  "terminal.integrated.fontSize":14,

  // Define o tema dos ícones na sidebar
  "workbench.iconTheme":"material-icon-theme",

  // Configura o Prettier e o ESLint
  "prettier.eslintIntegration": true,
  "editor.formatOnSave": true
}
```
