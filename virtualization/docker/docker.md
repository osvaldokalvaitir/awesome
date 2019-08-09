# Docker

Possibilita o empacotamento de uma aplicação ou ambiente inteiro dentro de um container, tornando-se portável para qualquer outro host.

## Documentação e Instalação

Clique [aqui](https://www.docker.com/docker-community) para ver a documentação e fazer a instalação do Docker Community, que é a versão gratuita.  

Obs: O Docker no Windows usa o Hyper-V e isso pode dar conflito se na máquina é usado algum emulador (ex. Genymotion), então, poderá ser usado o Docker Toolbox que é um pouco mais lento e antigo.

## Configuração

Depois de instalado o Docker, é necessário efetuar o login no aplicativo.

## Comandos

### Container

Criar um container e executar:

```
docker run --name <nome_container> -p <0000>:<0000> -d -t <nome_imagem>
```
Onde:

- `<nome_container>` - nome do container. Ex: `database`
- `<0000>` - porta do container. Ex: `5432`
- `<nome_imagem>` - nome da imagem. Ex: `postgres`

Obs: Existem mais parâmetros para configurar o nome do banco de dados, usuário e senha que se encontram na documentação.  

Exibir todos os containers em execução:

```
docker ps
```

Exibir todos os containers existentes:

```
docker ps -a
```

Executar um container (ao executar este comando, quando o Docker é reiniciado, o container também é reiniciado):

```
docker start <id/nome_container>
```

Parar um container:

```
docker stop <id/nome_container>
```

Remover um container:

```
docker rm <id/nome_container>
```

Logs do container:

```
docker logs <id/nome_container>

```

Exibir informações de uso de hardware do container:

```
docker stats <id/nome_container>
```

Exibir uma lista de informações do container (ex: IP):

```
docker inspect <id/nome_container>
```

Onde:

- `<id>` - id do container.
- `<nome_container>` - nome do container. Ex: `database`

### Imagem

Exibir todas as imagens:

```
docker images
```

Fazer download de uma imagem do Docker Hub:

```
docker pull <nome_imagem>:<versao>
```

Onde:

- `<nome_imagem>` - nome da imagem.
- `<versao>` - versão da imagem. Obs: se não passar a versão, o padrão é `lastest`.

Remover uma imagem:

```
docker rmi <id/nome_imagem>
```

### Volume

Exibir todos os volumes:

```
docker volume ls
```

Criar um volume:

```
docker volume create <nome_volume>
```

Remover um volume:

```
docker volume rm <VOLUME_NAME>
```