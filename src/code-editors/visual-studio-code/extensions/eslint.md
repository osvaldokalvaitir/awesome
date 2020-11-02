# ESLint

Utilizado para padronizar código entre desenvolvedores como utilização de pontos e vírgulas, tamanho máximo de caracteres em linhas e todo outro tipo de padronização.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalado o ESLint, setar as configurações (Settings > Open settings.json):

```
{  
  // Define a configuração do ESLint ao salvar
  "[javascript]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
  "[javascriptreact]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
  "[typescript]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
  "[typescriptreact]": {
    "editor.codeActionsOnSave": {
      "source.fixAll.eslint": true,
    }
  },
}
```