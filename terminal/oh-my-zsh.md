# Oh My Zsh

Terminal para Unix, funciona melhor no macOS e Linux.

Obs: Uma outra opção seria o terminal [Terminal.app](terminal.app.md).

## Documentação

Clique [aqui](https://ohmyz.sh) para ver a documentação no site.

## Instalação

- **Linux/OS X usando cURL**

Para instalar, acesse o [site](https://ohmyz.sh) e copie o comando que está na aba `Via curl` e execute no terminal. Será necessário informar a senha antes de instalar.

## Configurações

### Tema

#### Instalação

Para instalar o tema [Spaceship ZSH](https://github.com/denysdovhan/spaceship-prompt) entre no github e na seção `Installing`, siga as instruções da guia `oh-my-zsh`.

Clonando o repositório e executando o código do Symlink. Depois abra o arquivo zshrc (ex: `code ~/.zshrc`) e substitua o valor do ZSH_THEME por `ZSH_THEME="spaceship"`, salve e feche o terminal.

#### Configuração

Para adicionar algumas configurações como a ordem do prompt, entre outros, no final do arquivo zshrc (ex: `code ~/.zshrc`), adicione as linhas abaixo:

```
SPACESHIP_PROMPT_ORDER=(
  user          # Username section
  dir           # Current directory section
  host          # Hostname section
  git           # Git section (git_branch + git_status)
  hg            # Mercurial section (hg_branch  + hg_status)
  exec_time     # Execution time
  line_sep      # Line break
  vi_mode       # Vi-mode indicator
  jobs          # Background jobs indicator
  exit_code     # Exit code section
  char          # Prompt character
)

SPACESHIP_PROMPT_ADD_NEWLINE=false
SPACESHIP_CHAR_SYMBOL="❯"
SPACESHIP_CHAR_SUFFIX=" "
```

Salve o arquivo e feche o terminal.
