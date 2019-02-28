# Spaceship ZSH

Spaceship é um prompt de Zsh minimalista, poderoso e extremamente personalizável. Ele combina tudo o que você precisa para um trabalho conveniente, sem complicações desnecessárias, como uma nave espacial real.

## Documentação

Clique [aqui](https://github.com/denysdovhan/spaceship-prompt) para ver a documentação no site.

## Instalação

Para instalar o Spaceship ZSH entre no [site](https://github.com/denysdovhan/spaceship-prompt) e na seção `Installing`, siga as instruções da guia `oh-my-zsh`.

Clonando o repositório e executando o código do Symlink. Depois abra o arquivo zshrc (ex: `code ~/.zshrc`) e substitua o valor do ZSH_THEME por `ZSH_THEME="spaceship"`, salve e feche o terminal.

## Configuração

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
