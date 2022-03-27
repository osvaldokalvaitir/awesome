# Insomnia

Cliente REST utilizado para testar as requisições REST ao servidor.

## Documentação e Instalação

Clique [aqui](https://insomnia.rest) para ver a documentação e fazer a instalação.

## Configuração de Variável

Para configurar os ambientes de desenvolvimento e produção com uma base URL, siga os seguintes procedimentos:

- Clique no menu `No Environment` e no item `Manage Environments`

- Em `Sub Environments`, clique no botão `+` da frente e `Environment`

- Coloque o nome de `Development` e escolha uma cor. Ex: `roxo`.

- Faça o mesmo procedimento e coloque o nome de `Production` e escolha uma cor. Ex: `verde`

- No json de cada um desses ambientes, adicione a variável `url` com o seguinte código:

```
{
  "url": "<ip_servidor>:<porta>"
}
```

Onde:

`<ip_servidor>` - IP do servidor que receberá as requisições. Ex: `http://localhost`
`<porta>` - porta do servidor. Ex: `3000`.

- Clique em `Done`

Agora, quando for realizar alguma requisição, a variável poderá ser utilizada digitando o nome dela e aparecerá ela no menu, ou digite `{{ nome_variavel }}`.


## Criar botão do Insomnia

Clique [aqui](https://insomnia.rest/create-run-button) para gerar o botão do Insomnia e adicionar no GitHub.