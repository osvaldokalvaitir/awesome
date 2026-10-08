# pgvector/pgvector

Imagem do PostgreSQL com a extensão pgvector para o ambiente Docker. Permite armazenar vetores e fazer buscas por similaridade, muito usado em aplicações com inteligência artificial.

## Configurações

Nome da imagem: `pgvector/pgvector:pg17`
Porta: `5432`
Usuário: `postgres`
Senha: `docker`

Ex: `docker run --name <nome_container> -e "POSTGRES_DB=database" -e "POSTGRES_USER=postgres" -e "POSTGRES_PASSWORD=docker" -p 5432:5432 -d pgvector/pgvector:pg17`

Após criar o container, habilite a extensão no banco de dados:

```
CREATE EXTENSION vector;
```

## Documentação e Instalação

Clique [aqui](https://hub.docker.com/r/pgvector/pgvector) para ver a documentação e fazer a instalação.
