# Insomnia

Cliente REST utilizado para testar as requisições REST ao servidor.

## Documentação e Instalação

Clique [aqui](https://insomnia.rest) para ver a documentação e fazer a instalação.

## Configuração de Variável

Para configurar uma variável URL de base, siga os seguintes procedimentos:

- Clique no menu `No Environment` e no item `Manage Environments`

- Em `Base Environment`, adicione a variável com o seguinte código:

```
{
  "base_url": "<ip_servidor>:<porta>"
}
```

Onde:

`<ip_servidor>` - IP do servidor que receberá as requisições. Ex: `http://localhost`
`<porta>` - porta do servidor. Ex: `3000`.

- Clique em `Done`

Agora, quando for realizar alguma requisição, a variável poderá ser utilizada digitando o nome dela.
