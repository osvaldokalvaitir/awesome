# Ghost-CLI

Ferramenta CLI para instalar e atualizar o Ghost.

## Documentação

Clique [aqui](https://github.com/TryGhost/Ghost-CLI) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/ghost-cli) para fazer a instalação.

Instalar globalmente:

```
npm install --global ghost-cli | yarn global add ghost-cli
```

## Comandos do CLI

Instalação para produção com configuração linux, incluindo Nginx, SSL e Systemd:

```
ghost install
```

Instalação para configuração local, útil para desenvolvimento/teste de temas:

```
ghost install local
```

Depois de instalar, para acessar o painel de admnistração, sendo que o primeiro acesso cria o administrador:

```
localhost:2368/ghost
```

Iniciar servidor:

```
ghost start
```

Parar servidor:

```
ghost stop
```

Reiniciar servidor:

```
ghost restart
```

Atualizar o Ghost, com servidor parado:

```
ghost update
```