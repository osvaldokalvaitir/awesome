# PM2

O PM2 é um gerenciador de processos de produção para aplicativos Node.js com um balanceador de carga integrado.

## Documentação

Clique [aqui](https://github.com/Unitech/pm2) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/pm2) para fazer a instalação.

Instalar globalmente:

```
npm install --global pm2 | yarn global add pm2
```

## Comandos

Iniciar servidor com o PM2:

- Projeto Node.js:

  ```
  pm2 start <nome_arquivo>
  ```

  Ex: `pm2 start index.js`

- Projeto ReactJS com a biblioteca [Serve](serve.md):

  ```
  pm2 serve <nome_pasta>
  ```

  Ex: `pm2 serve build`

Obs: O PM2 não bloqueia o terminal.

Para visualizar a lista que o PM2 está rodando:

```
pm2 list
```

Para aparecer a tela de monitoramento do PM2:

```
pm2 monit
```

Obs: Os `console.log` apareceram nesta tela.

Para algumas ações é necessário o `app_name` e para isso execute `pm2 list` e veja o nome do arquivo.

Para reiniciar o servidor:

```
pm2 restart <app_name|id>
```

Ex: `pm2 restart index`

Para parar o servidor:

```
pm2 stop <app_name|id>
```

Ex: `pm2 stop index`

O PM2 pode gerar e configurar um script de inicialização para manter o PM2 e seus processos ativos em todas as reinicializações do servidor.

Para gerar script de inicialização:

```
pm2 startup
```

Ex: `pm2 startup ubuntu`

Aparecerá um comando no terminal, copie este comando e execute no terminal.

Para remover o script de inicialização:

```
pm2 unstartup
```
