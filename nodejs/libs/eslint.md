# ESLint

Ferramenta para identificar e relatar padrões em JavaScript.

## Documentação

Clique [aqui](https://github.com/eslint/eslint) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/eslint) para fazer a instalação.

Instalar como dependência de desenvolvimento:

```
npm install eslint --save-dev | yarn add eslint --dev
```

É necessário setar um arquivo de configuração com o comando:

```
npx eslint --init | yarn eslint --init
```

Se instalar o ESLint com o Yarn, ele criará o arquivo `package-lock.json`, então depois que terminar a instalação e configuração, delete o arquivo e execute o comando abaixo para instalar as dependências com o yarn:

```
yarn
```

### Instalação no projeto Node.js

Para um projeto Node.js as configurações são:

How would you like to use ESLint?
**To check syntax, find problems, and enforce code style**

What type of modules does your project use?
**CommonJS (require/exports)**

Which framework does your project use?
**None of these**

Where does your code run?
**Node**

How would you like to define a style for your project?
**Use a popular style guide**

Which style guide do you want to follow?
**Standard (https://github.com/standard/standard)**

What format do you want your config file to be in?
**JSON**

Would you like to install them now with npm? (Y/n)
**Y**

### Instalação no projeto ReactJS sem Create React

Para um projeto ReactJS sem Create React App as configurações são:

How would you like to use ESLint?
**To check syntax, find problems, and enforce code style**

What type of modules does your project use?
**JavaScript modules (import/export)**

Which framework does your project use?
**React**

Where does your code run? (Press \<space> to select, \<a> to toggle all, \<i> to invert selection)
**Browser**

How would you like to define a style for your project?
**Use a popular style guide**

Which style guide do you want to follow?
**Airbnb (https://github.com/airbnb/javascript)**

What format do you want your config file to be in?
**JSON**

Would you like to install them now with npm? (Y/n)
**Y**

### Instalação no projeto ReactJS com Create React App

Para um projeto ReactJS com Create React App, o ESLint já vem instalado.

Então, precisa instalar somente o [eslint-config-airbnb](eslint-config-airbnb.md) e suas dependências: [eslint-plugin-import](eslint-plugin-import.md), [eslint-plugin-jsx-a11y](eslint-plugin-jsx-a11y.md) e [eslint-plugin-react](eslint-plugin-react.md).

E criar o arquivo .eslintrc manualmente.

### Instalação no projeto React-Native

How would you like to use ESLint?
**To check syntax, find problems, and enforce code style**

What type of modules does your project use?
**JavaScript modules (import/export)**

Which framework does your project use?
**React**

Where does your code run?
**Não selecionar nenhum deles**

How would you like to define a style for your project?
**Use a popular style guide**

Which style guide do you want to follow?
**Airbnb (https://github.com/airbnb/javascript)**

What format do you want your config file to be in?
**JSON**

Would you like to install them now with npm? (Y/n)
**Y**
