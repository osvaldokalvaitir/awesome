# Visual Studio Code

Editor de código-fonte que inclui suporte para depuração, realce de sintaxe, complementação inteligente de código, snippets, entre outros.

## Documentação e Instalação

Clique [aqui](https://code.visualstudio.com) para ver a documentação e fazer a instalação.

## Fonte

- [Fira Code](fira-code.md)

## Extensões

- [Color Highlight](color-highlight.md)
- [DotEnv](dotenv.md)
- [Dracula Official](dracula-official.md)
- [EditorConfig for VS Code](editorconfig-for-vs-code.md)
- [ESLint](eslint.md)
- [Markdown All in One](markdown-all-in-one.md)
- [Material Icon Theme](material-icon-theme.md)
- [Nunjucks](nunjucks.md)
- [Prettier - Code formatter](prettier-code-formatter.md)

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
