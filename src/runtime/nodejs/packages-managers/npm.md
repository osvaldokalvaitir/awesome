# npm

npm é um gerenciador de pacotes para a linguagem de programação JavaScript. npm, Inc. é uma subsidiária do GitHub, uma corporação multinacional americana que fornece hospedagem para desenvolvimento de software e controle de versão com o uso do Git.

## Documentação e Instalação

Clique [aqui](https://www.npmjs.com) para ver a documentação e fazer a instalação.

## Comandos

### Básicos

Verificar a versão do npm:

```
npm -v
```

Para atualizar a npm para a versão mais recente:

```
npm install npm -g
```

Verificar a versão de um pacote:

```
npm show <nome_pacote> version
```

Verificar os pacotes instalados:

```
npm list
```

Verificar os pacotes instalados globalmente:

```
npm list -g
```

Verificar os pacotes desatualizados:

```
npm outdated
```

Verificar os pacotes desatualizados globalmente:

```
npm outdated -g
```

Verificar os scripts disponíveis:

```
npm run
```

Executar um script:

```
npm run <nome_script>
```

### Instalação de Pacotes

Instalar as dependências do projeto:

```
npm install
```

Instalar um pacote:

```
npm install <nome_pacote>
```

Instalar um pacote como dependência de desenvolvimento:

```
npm install <nome_pacote> --save-dev
```

Instalar um pacote globalmente:

```
npm install -g <nome_pacote>
```

### Atualização de Pacotes

Atualizar todos os pacotes:

```
npm update
```

Atualizar um pacote:

```
npm update <nome_pacote>
```

### Remoção de Pacotes

Remover um pacote:

```
npm uninstall <nome_pacote>
```