# pnpm

Gerenciador de pacotes rápido e eficiente em espaço em disco.

## Documentação e Instalação

Clique [aqui](https://pnpm.io) para ver a documentação e fazer a instalação.

## Instalação

- **Linux, Mac e Windows**

  Para instalar o pnpm, executar o seguinte comando:

  ```
  npm install -g pnpm
  ```

  Para verificar se o pnpm está instalado:

  ```
  pnpm -v
  ```

## Comandos

### Básicos

Verificar a versão do pnpm:

```
pnpm -v
```

Para atualizar o pnpm para a versão mais recente:

```
pnpm install -g pnpm
```

Para desinstalar o pnpm:

```
npm uninstall -g pnpm
```

Verificar a versão de um pacote:

```
pnpm show <nome_pacote> version
```

Verificar os pacotes instalados:

```
pnpm list
```

Verificar os pacotes instalados globalmente:

```
pnpm list -g
```

Verificar os pacotes desatualizados:

```
pnpm outdated
```

Verificar os pacotes desatualizados globalmente:

```
pnpm outdated -g
```

Verificar os scripts disponíveis:

```
pnpm run
```

Executar um script:

```
pnpm run <nome_script>
```

Para limpar o cache do pnpm:

```
pnpm cache clear
```

Para verificar o espaço em disco ocupado pelos pacotes:

```
pnpm store status
```

### Instalação de Pacotes

Instalar as dependências do projeto:

```
pnpm install
```

Instalar um pacote:

```
pnpm install <nome_pacote>
```

Instalar um pacote como dependência de desenvolvimento:

```
pnpm install <nome_pacote> --save-dev
```

Instalar um pacote globalmente:

```
pnpm install -g <nome_pacote>
```

### Atualização de Pacotes

Atualizar todos os pacotes:

```
pnpm update
```

Atualizar um pacote:

```
pnpm update <nome_pacote>
```

### Remoção de Pacotes

Remover um pacote:

```
pnpm uninstall <nome_pacote>
```