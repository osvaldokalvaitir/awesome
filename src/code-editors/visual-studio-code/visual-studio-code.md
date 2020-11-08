# Visual Studio Code

Editor de código-fonte que inclui suporte para depuração, realce de sintaxe, complementação inteligente de código, snippets, entre outros.

## Documentação e Instalação

Clique [aqui](https://code.visualstudio.com) para ver a documentação e fazer a instalação.

## Fonte

### Instalação

- [Fira Code](../../fonts/fira-code.md)

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

## Todas as Configurações

Depois de adicionar a fonte e as extensões, setar as configurações (Settings > Open settings.json):

```
{
  // Um novo arquivo em branco não é mais aberto na inicialização
  "workbench.startupEditor": "newUntitledFile",

  // Na aba do arquivo aberto, aparece o nome da pasta depois do nome do arquivo
  "workbench.editor.labelFormat": "short",

  // Zoom
  "window.zoomLevel": 0,

  // Habilita recomendações de extensões
  "extensions.ignoreRecommendations": false,

  // Desabilita a compactação de pasta se estiver vazia
  "explorer.compactFolders": false,

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

  // Desabilita os imports automáticos
  "javascript.suggest.autoImports": false,

  // Commitar todas as alterações quando não houver alterações em etapas
  "git.enableSmartCommit": true,

  // Configuração do Typescript
  "typescript.tsserver.log": "verbose",
  "typescript.updateImportsOnFileMove.enabled": "never",

  // Path Intellisense
  "typescript.suggest.paths": false,

  // Associações de arquivos
  "files.associations": {
    ".sequelizerc": "javascript",
    ".stylelintrc": "json",
    ".prettierrc": "json"
  },


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
  "[javascript]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
  "[javascriptreact]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
  "[typescript]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
  "[typescriptreact]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },

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