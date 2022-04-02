# ESLint

Utilizado para padronizar código entre desenvolvedores como utilização de pontos e vírgulas, tamanho máximo de caracteres em linhas e todo outro tipo de padronização.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{  
  // Ações de código ao salvar
  "editor.codeActionsOnSave": { "source.fixAll.eslint": true },
}
```