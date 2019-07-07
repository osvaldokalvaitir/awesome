# Docker

Possibilita o empacotamento de uma aplicação ou ambiente inteiro dentro de um container, tornando-se portável para qualquer outro host.

## Documentação e Instalação

Clique [aqui](https://www.docker.com/docker-community) para ver a documentação e fazer a instalação do Docker Community, que é a versão gratuita.  

Obs: O Docker no Windows usa o Hyper-V e isso pode dar conflito se na máquina é usado algum emulador (ex. Genymotion), então, poderá ser usado o Docker Toolbox que é um pouco mais lento e antigo.

## Configuração

Depois de instalado o Docker, é necessário efetuar o login no aplicativo.

## Comandos

Criar um container e executar:

```
docker run --name nome_container -p 0000:0000 -d -t nome_imagem
```

Exibir todos os containers em execução:

```
docker ps
```

Exibir todos os containers existentes:

```
docker ps -a
```

Executar um container:

```
docker start nome_container
```

Parar um container:

```
docker stop nome_container
```

Remover um container:

```
docker rm nome_container
```
