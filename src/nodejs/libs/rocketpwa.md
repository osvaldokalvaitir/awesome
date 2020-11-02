# RocketPWA

Um conjunto de ferramentas criado para desenvolvedores de PWA. No Windows este pacote requer: `.NET Framework 2.0 SDK` e `Visual Studio 2005`.

## Documentação

Clique [aqui](https://github.com/rocketseat/rocketpwa) para ver a documentação.

## Instalação

Clique [aqui](https://www.npmjs.com/package/rocketpwa) para fazer a instalação.

Instalar globalmente:

```
npm install --global rocketpwa | yarn global add rocketpwa
```

## Comandos do CLI

Para gerar ícones de todos os tamanhos:

```
rocketpwa --icon icon.png
```

Colocar o parâmetro `-r` para gerar os ícones com cantos arredondados.  

Para gerar splash screens:

```
rocketpwa --splash splash.png
```

Por padrão, o rocketpwa tentará encontrar a melhor correspondência para posicionar a splash screen em diferentes tamanhos de tela, mas às vezes você pode encontrar problemas de corte.  

Para contornar isso, você pode adicionar um simples `--fill` como parâmetro para definir a cor do plano de fundo de fallback para splash screens:

```
rocketpwa --splash splash.png --fill "#7159C1"
```