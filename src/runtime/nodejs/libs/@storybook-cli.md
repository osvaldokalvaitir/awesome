# Storybook CLI

O Storybook CLI (Interface de Linha de Comando) é a maneira mais fácil de adicionar o Storybook ao seu projeto.

## Documentação

Clique [aqui](https://github.com/storybookjs/storybook) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/@storybook/cli) para fazer a instalação.

## Comandos do CLI

Iniciar o Storybook no projeto (instalar):

```
npx -p @storybook/cli sb init
```

Ou

Iniciar o Storybook com o Vite (antes é necessário instalar o [Vite](vite.md)):

```
npx storybook init --builder @storybook/builder-vite --type react
```

Rodar o Storybook:

```
npm run storybook
```