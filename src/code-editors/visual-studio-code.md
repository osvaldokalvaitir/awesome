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
  // WORKBENCH & WINDOW
  "workbench.startupEditor": "newUntitledFile",
  "workbench.editor.labelFormat": "short",
  "workbench.colorTheme": "Omni",
  "workbench.iconTheme": "material-icon-theme",
  "workbench.productIconTheme": "fluent-icons",
  "window.menuBarVisibility": "toggle",

  // EDITOR - CORE
  "editor.fontSize": 14,
  "editor.lineHeight": 1.8,
  "editor.fontFamily": "JetBrains Mono",
  "editor.fontLigatures": true,
  "editor.tabSize": 2,
  "editor.rulers": [80, 120],
  "editor.renderLineHighlight": "gutter",
  "editor.semanticHighlighting.enabled": false,
  "editor.parameterHints.enabled": false,
  "editor.suggestSelection": "first",
  "editor.inlineSuggest.enabled": true,

  // EDITOR - ACTIONS & FORMATTING
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": "always"
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[prisma]": {
    "editor.formatOnSave": true
  },

  // EDITOR - THEME CUSTOMIZATION
  "editor.tokenColorCustomizations": {
    "[*Light*]": {
      "textMateRules": [
        {
          "scope": "ref.matchtext",
          "settings": {
            "foreground": "#000"
          }
        }
      ]
    },
    "[*Dark*]": {
      "textMateRules": [
        {
          "scope": "ref.matchtext",
          "settings": {
            "foreground": "#fff"
          }
        }
      ]
    },
    "textMateRules": []
  },

  // EXPLORER & FILES
  "explorer.fileNesting.enabled": true,
  "explorer.compactFolders": false,
  "explorer.confirmDragAndDrop": false,
  "explorer.confirmDelete": false,
  "explorer.confirmPasteNative": false,
  "files.eol": "\n",
  "files.associations": {
    ".sequelizerc": "javascript",
    ".stylelintrc": "json",
    ".prettierrc": "json",
    "*.tsx": "typescriptreact",
    ".env.*": "dotenv",
    ".env*": "dotenv"
  },

  // NAVIGATION
  "breadcrumbs.enabled": true,

  // DIFF EDITOR
  "diffEditor.ignoreTrimWhitespace": false,

  // TERMINAL
  "terminal.integrated.fontSize": 14,
  "terminal.integrated.fontFamily": "JetBrainsMono Nerd Font",
  "terminal.integrated.defaultProfile.osx": "/bin/zsh",
  "terminal.integrated.env.osx": {},
  "terminal.integrated.defaultProfile.linux": "/bin/zsh",
  "terminal.integrated.defaultProfile.windows": "Command Prompt",
  "terminal.integrated.env.windows": {},

  // JAVASCRIPT & TYPESCRIPT
  "javascript.suggest.autoImports": true,
  "javascript.updateImportsOnFileMove.enabled": "always",
  "typescript.suggest.autoImports": true,
  "typescript.preferences.preferTypeOnlyAutoImports": true,
  "typescript.updateImportsOnFileMove.enabled": "always",
  "typescript.tsserver.log": "off",

  // EMMET
  "emmet.syntaxProfiles": {
    "javascript": "jsx"
  },
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },

  // SECURITY
  "security.workspace.trust.untrustedFiles": "newWindow",

  // EXTENSIONS
  "extensions.ignoreRecommendations": true,

  // EXTENSION CONFIGURATIONS
  
  // ChatGPT
  "chat.instructionsFilesLocations": {
    ".github/instructions": true,
    "C:\\Users\\Dal\\AppData\\Local\\Temp\\postman-http-request-post-response.instructions.md": true,
    "C:\\Users\\Dal\\AppData\\Local\\Temp\\postman-http-request-pre-request.instructions.md": true
  },

  // Code Spell Checker
  "cSpell.language": "en,pt,pt_BR",
  "cSpell.enabledFileTypes": {
    "asciidoc": false,
    "c": false,
    "cpp": false,
    "csharp": false,
    "go": false,
    "handlebars": false,
    "haskell": false,
    "jade": false,
    "java": false,
    "latex": false,
    "php": false,
    "pug": false,
    "python": false,
    "restructuredtext": false,
    "rust": false,
    "scala": false,
    "scss": false
  },

  // Console Ninja
  "console-ninja.featureSet": "Community",

  // Dotenv
  "dotenv.enableAutocloaking": false,

  // Git
  "git.enableSmartCommit": true,

  // GitHub Copilot
  "github.copilot.enable": {
    "*": true,
    "plaintext": true,
    "markdown": true,
    "scminput": false,
    "yaml": false
  },

  // GitHub Pull Requests
  "githubPullRequests.terminalLinksHandler": "github",
  "githubPullRequests.pullBranch": "never",

  // GitLens
  "gitlens.codeLens.recentChange.enabled": false,
  "gitlens.codeLens.authors.enabled": false,
  "gitlens.codeLens.enabled": false,

  // Live Share
  "liveshare.featureSet": "insiders",
  "liveshare.connectionMode": "relay",

  // Material Icon Theme
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

  // PostgreSQL
  "pgsql.serverGroups": [
    {
      "name": "Servers",
      "id": "662983E8-C524-4252-A887-561F6FD5E995",
      "isDefault": true
    }
  ],
  "pgsql.connections": [
    {
      "id": "24148F4F-573E-4D5C-8AFE-052C4B700F04",
      "groupId": "662983E8-C524-4252-A887-561F6FD5E995",
      "authenticationType": "SqlLogin",
      "connectTimeout": 15,
      "applicationName": "vscode-pgsql",
      "clientEncoding": "utf8",
      "sslmode": "require",
      "password": "",
      "user": "postgres",
      "database": "dbprod01",
      "server": "prismapro-instance-1.cqzjqsedeu8t.sa-east-1.rds.amazonaws.com",
      "profileName": "Prisma Production",
      "port": "5432",
      "displayName": "Prisma Production",
      "savePassword": true,
      "expiresOn": 0
    }
  ],

  // Split HTML Attributes
  "splitHTMLAttributes.closingBracketOnNewLine": true,

  // Tailwind CSS IntelliSense
  "tailwindCSS.experimental.classRegex": [
    ["cva\\(([^)]*)\\)", "[\"'`]([^\"'`]*).*?[\"'`]"]
  ],

  // Todo Tree
  "todo-tree.general.tags": [
    "BUG",
    "HACK",
    "FIXME",
    "TODO",
    "XXX",
    "[ ]",
    "[x]"
  ],
  "todo-tree.regex.regex": "(//|#|<!--|;|/\\*|^|^\\s*(-|\\d+.))\\s*($TAGS)"
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