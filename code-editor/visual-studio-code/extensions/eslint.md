# ESLint

Utilizado para padronizar código entre desenvolvedores como utilização de pontos e vírgulas, tamanho máximo de caracteres em linhas e todo outro tipo de padronização.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalado o ESLint, setar as configurações (Settings > Open settings.json):

```
{  
  // Define a configuração do ESLint ao salvar
  "eslint.autoFixOnSave": true,
  "eslint.validate": [
    {
      "language": "javascript",
      "autoFix": true
    },
    {
      "language": "javascriptreact",
      "autoFix": true
    },
    {
      "language": "typescript",
      "autoFix": true
    },
    {
      "language": "typescriptreact",
      "autoFix": true
    },
  ],  
}
```