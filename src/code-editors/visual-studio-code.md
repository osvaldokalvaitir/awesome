# Visual Studio Code

Editor de código-fonte que inclui suporte para depuração, realce de sintaxe, complementação inteligente de código, snippets, entre outros.

## Documentação e Instalação

Clique [aqui](https://code.visualstudio.com) para ver a documentação e fazer a instalação.

## Fonte

### Instalação

- [Fira Code](../../fonts/fira-code.md)
- [JetBrains Mono](../../fonts/jetbrains-mono.md)
- [JetBrainsMono Nerd Font](../../fonts/jetbrainsmono-nerd-font.md)

### Configuração de fonte do editor

Depois de instalar a fonte, setar as configurações (Settings > Open settings.json):

```
{
  // Configura o tamanho e a família da fonte
  "editor.fontSize": 14,
  "editor.lineHeight": 1.8,
  "editor.fontFamily": "JetBrains Mono",
  "editor.fontLigatures": true,
}
```

ou

```
{
  // Configura o tamanho e a família da fonte
  "editor.fontSize":18,
  "editor.lineHeight":24,
  "editor.fontFamily":"Fira Code",
  "editor.fontLigatures": true,
}
```

### Configuração de fonte do terminal

Depois de instalar a fonte, setar as configurações (Settings > Open settings.json):

```
{
  // Configura o tamanho e a família da fonte do terminal
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "JetBrainsMono Nerd Font",
}
```

## Todas as Configurações

Depois de adicionar a fonte e as extensões, setar as configurações (Settings > Open settings.json):

```
{
  // Um novo arquivo em branco não é mais aberto na inicialização
  "workbench.startupEditor": "newUntitledFile",

  // Na aba do arquivo aberto, aparece o nome da pasta depois do nome do arquivo
  "workbench.editor.labelFormat": "short",

  // Visibilidade da barra de menu
  "window.menuBarVisibility": "toggle",

  // Zoom
  "window.zoomLevel": 0,

  // Habilita recomendações de extensões
  "extensions.ignoreRecommendations": true,

  // Agrupa arquivos relacionados
  "explorer.fileNesting.enabled": true,

  // Desabilita a compactação de pasta se estiver vazia
  "explorer.compactFolders": false,

  // Desabilita a confirmação ao arrastar-e-soltar
  "explorer.confirmDragAndDrop": false,

  // Desabilita a confirmação ao deletar
  "explorer.confirmDelete": false,

  // Controla se o explorador deve renderizar pastas em um formato compacto
  "explorer.compactFolders": false,

  // Aplica linhas verticais para lembrar de quebrar linha
  "editor.rulers": [80, 120],

  // Aplica um sinal visual na esquerda da linha selecionada
  "editor.renderLineHighlight":"gutter",

  // Realce semântico desativado para todos os temas de cores
  "editor.semanticHighlighting.enabled": false,

  // Desabilita o hint de documentação
  "editor.parameterHints.enabled": false,

  // Tamanho da tabulação
  "editor.tabSize": 2,

  // Sempre selecione a primeira sugestão
  "editor.suggestSelection": "first",

  // Ações de código ao salvar
  "editor.codeActionsOnSave": { "source.fixAll.eslint": true },

  // Guias auxiliares de navegação
  "breadcrumbs.enabled": true,

  // Configura o tamanho e a família da fonte do terminal
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "JetBrainsMono Nerd Font",

  // Terminal padrão no OSX
  "terminal.integrated.defaultProfile.osx": "/bin/zsh",

  // Terminal padrão no Linux
  "terminal.integrated.defaultProfile.linux": "/bin/zsh",

  // Terminal padrão no Windows
  "terminal.integrated.defaultProfile.windows": "Command Prompt",

  // Auto complete de javascript em arquivos jsx
  "emmet.syntaxProfiles": { "javascript": "jsx" },

  // Inclui a linguagem do javascriptreact
  "emmet.includeLanguages": { "javascript": "javascriptreact" },

  // Habilita imports automáticos
  "javascript.suggest.autoImports": true,
  "typescript.suggest.autoImports": true,

  // Atualiza os imports ao mover o arquivo
  "javascript.updateImportsOnFileMove.enabled": "always",

  // Configurações do Typescript
  "typescript.tsserver.log": "off",
  "typescript.updateImportsOnFileMove.enabled": "never",

  // Sempre abra arquivos não confiáveis ​​em uma janela separada no modo restrito sem avisar
  "security.workspace.trust.untrustedFiles": "newWindow",




  // Configurações que precisam de fonte e extensões

  // Configura o tamanho e a família da fonte
  "editor.fontSize": 14,
  "editor.lineHeight": 1.8,
  "editor.fontFamily": "JetBrains Mono",
  "editor.fontLigatures": true,

  // Associações de arquivos
  "files.associations": {
    ".sequelizerc": "javascript",
    ".stylelintrc": "json",
    ".prettierrc": "json",
    "*.tsx": "typescriptreact",
    ".env.*": "dotenv"
  },  
s
  // Define o tema de cores
  "workbench.colorTheme": "Omni",

  // Define o tema de cores dos produtos
  "workbench.productIconTheme": "fluent-icons",

  // Define o tema dos ícones de arquivos
  "workbench.iconTheme": "material-icon-theme",

  // Configurações do Material Icon Theme
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

  // Configurações do Bracket Pair Colorizer 2
  "editor.bracketPairColorization.enabled": true,
  "editor.guides.bracketPairs":"active",
  "bracket-pair-colorizer-2.depreciation-notice": false,

  // Configurações do Code Spell Checker
  "cSpell.language": "en,pt,pt_BR",
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

  // Configurações do Git
  "git.enableSmartCommit": true,

  // Configurações do GitLens
  "gitlens.codeLens.recentChange.enabled": false,
  "gitlens.codeLens.authors.enabled": false,
  "gitlens.codeLens.enabled": false,

  // Configurações do Live Share
  "liveshare.featureSet": "insiders",
  "liveshare.connectionMode": "relay",

  // Configurações do Prisma
  "[prisma]": { "editor.formatOnSave": true },

  // Configurações do Split HTML Attributes
  "splitHTMLAttributes.closingBracketOnNewLine": true,

  // Configurações do Tabnine
  "tabnine.experimentalAutoImports": true,

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

## Atalhos do teclado

Para ver todos os atalhos, dê um `Ctrl + Shift + P` para abrir a barra de pesquisa e digite `Open Keyboard Shortcuts`.  

Os principais atalhos são:

```
Ctrl + Shift + p
Abre a pesquisa de comandos

Ctrl + p
Abre a pesquisa de arquivos

Ctrl + Shift + l
Seleciona todos com texto igual

Ctrl + D
Seleciona o próximo texto igual

Alt + clica
Posiciona vários cursores em vários lugares para digitar

Alt + Up/Down
Move a linha inteira

Shift + Alt + Up/Down
Copia a linha inteira

Ctrl + X
Recorta a linha inteira

Ctrl + ;
Transforma a linha num comentário

Ctrl + ]
Divide a tela

Ctrl + '
Abre o terminal
```