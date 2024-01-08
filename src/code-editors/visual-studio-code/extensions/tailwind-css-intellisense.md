# Tailwind CSS IntelliSense

Ferramentas inteligentes Tailwind CSS para VS Code.

## Documentação e Instalação

Clique [aqui](https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss) para ver a documentação e fazer a instalação.

## Configuração

Depois de instalar a extensão, setar as configurações (Settings > Open settings.json):

```
{
  // Configurações do Tailwind CSS IntelliSense
  "tailwindCSS.experimental.classRegex": [
    ["cva\\(([^)]*)\\)", "[\"']([^\"']*).*?[\"'`]"]
  ]
}
```