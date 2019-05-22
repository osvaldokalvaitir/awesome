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
  "base_url": "<ip_do_computador>:<porta>"
}
```

Onde:

`<ip_do_computador>` - IP do computador. Ex: `http://localhost`  
`porta` - porta do computador. Ex: `3000`  
  
- Clique em `Done`.

Agora, quando for realizar alguma requisição, a variável poderá ser utilizada digitando o nome dela.
