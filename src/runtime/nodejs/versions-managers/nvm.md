# NVM

Ficar gerenciando várias versões de algo pode ser chato, mas o NVM (Node Version Manager) deixa tudo bem simples. É um dos gerenciadores de versão de Node.js mais utilizados.

Com o NVM a gente pode ver as versões do Node, escolher quais queremos instalar ou desinstalar e definir qual queremos usar em cada momento ou projeto.

Ele funciona em MacOS e Linux. Caso você precise gerenciar no Windows existe um outro projeto chamado nvm-windows que também é muito bom (recomendado até mesmo por NPM, Google e Microsoft) e os comandos são iguais aos do NVM.

## Instalação

- **macOS e Linux**

  É recomendado desinstalar qualquer versão do Node.js presente em sua máquina antes de instalar o NVM para evitar colisões.

  Para instalar o NVM basta usar o curl ou Wget. Execute no terminal:

  ```
  $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
  ```

  ou

  ```
  $ wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
  ```

  Isso vai executar um script que vai clonar o repositório do NVM e jogar em um diretório chamado `~/.nvm/`, que é onde serão instaladas as várias versões do Node.js que quisermos.
  
  A versão do NVM no momento de escrita é v0.39.7. Para garantir uma versão mais recente, copie esse mesmo comando na [página do repositório do NVM no GitHub](https://github.com/nvm-sh/nvm).

- **macOS usando Homebrew**

  Caso queira instalar usando o Homebrew, basta executar o comando `$ brew install nvm`.

  Depois precisamos criar um diretório para o NVM, lugar onde ele fará as instalações das várias versões do Node.js. Para isso basta executar o comando `$ mkdir ~/.nvm/`.

  Por último é só configurar as variáveis de ambiente. Abra o arquivo `.bash_profile` com o comando vim `~/.bash_profile` e cole o seguinte conteúdo

  ```
  export NVM_DIR=~/.nvm
  source $(brew --prefix nvm)/nvm.sh
  ```

  E então basta executar source `~/.bash_profile`.

- **Windows**

  Como dito anteriormente, o NVM é só para MacOS e Linux. Você pode conseguir utilizá-lo no Windows usando o WSL (Windows Subsystem for Linux) ou pode usar um outro programa que é o `nvm-windows`.

  A proposta do `nvm-windows` é funcionar igual ao NVM. Eles oferecem um instalador que você pode baixar pela [lista de lançamentos do nvm-windows no repositório do GitHub](https://github.com/coreybutler/nvm-windows/releases).

## Comandos do CLI

### Listar versões instaladas

Para ver as versões que estão instaladas em sua máquina:

```
nvm ls
```

### Listar versões disponíveis para instalação

Este comando lista todas as versões disponíveis para baixar e instalar na sua máquina. Esse número de versão será usado no comando para realizar a instalação.

```
nvm ls-remote
```

### Instalar uma versão

Para instalar usamos o comando `install` seguido pelo número da versão que queremos (mostrada no comando anterior, `ls-remote`).

```
nvm install vX.X.X
```

Basta mudar os `X` pelos números da versão que quer baixar como `v.0.11.5` ou `v.12.4.0`.

Para instalar a versão mais recente, utilize `node` no lugar do número da versão:

```
nvm install node
```

A primeira versão que você instalar será usada por padrão sempre que você abrir o terminal. A versão padrão pode ser alterada depois.

### Desinstalar uma versão

O comando `uninstall` é usado para desinstalar uma versão presente em nossa máquina. É utilizado da mesma maneira que o `install`.

```
nvm uninstall vX.X.X
```

### Usar uma versão do Node.js

Sempre que você abrir o terminal, a versão do Node.js usada é sempre a definida como padrão. Para usar outra versão instalada, execute o comando `use` seguido pela versão que você quer.

```
nvm use vX.X.X
```

Para usar a versão mais recente, digite `node` no lugar da versão:

```
nvm use node
```

### Definir nome para uma versão

Para não ter que ficar chamando uma versão pelo seu número, podemos definir um tipo de apelido para cada versão. Para isso usamos o comando `alias` e passamos o nome do apelido e a versão que queremos apelidar.

```
nvm alias meunome vX.X.X
```

Com isso você poderá chamar a versão `vX.X.X` por `meunome`, como em:

```
nvm use meunome
```

### Remover um nome de versão

Se você não quiser mais aquele apelido que você deu para uma versão, basta executar o comando `unalias` seguido pelo apelido que você quer esquecer.

```
nvm unalias meunome
```

### Definir uma versão padrão

Para definir a versão que será usada sempre que você abrir o terminal, use o comando `alias` passando `default` como nome e em seguida a versão que você quer que seja a principal.

```
nvm alias default vX.X.X
```

Para que a versão padrão seja a versão instalada mais recente, basta escrever node no lugar do número da versão:

```
nvm alias default node
```

### Indicação da versão atual

Para saber qual a versão atual do Node.js o terminal está usando, basta executar o comando `current`.

```
nvm current
```

### Migração de pacotes globais

Quando alteramos a versão do Node.js que está sendo utilizada, a versão do NPM muda junto. Isso significa que se você utiliza algum pacote do NPM globalmente em uma versão, não terá acesso a ele quando estiver usando outra versão.

Para não ter o trabalho de instalar cada pacote global a cada nova instalação do Node.js, basta adicionar `--reinstall-packages-from`.

Com esse comando podemos, por exemplo, instalar a versão 6 do Node.js e já mandar ele automaticamente instalar os pacotes globais do NPM que instalamos quando estávamos usando a versão 5.

```
nvm install 6 --reinstall-packages-from=5
```

Como aprendemos até aqui, `node` é um atalho para indicar a versão mais recente. Caso queira instalar a versão mais recente disponível e já migrar os pacotes globais da versão mais recente que está instalada na sua máquina, basta executar:

```
nvm install node --reinstall-packages-from=node
```

No momento esta funcionalidade ainda não está disponível para o nvm-windows, sendo necessária a instalação manual dos pacotes globais sempre que instalar uma nova versão do Node.js.

### Definição de versão por projeto

A intenção de usar o NVM é poder ter uma versão do Node.js para cada projeto, mas é muito difícil conseguir lembrar qual a versão foi usada em cada um.

Para isso, basta criar na raiz do projeto um arquivo com o nome `.nvmrc` e colocar dentro dele o número da versão do Node.js que está sendo utilizada nesse projeto, como:

```
v12.4.0
```

Com isso, ao abrir o terminal dentro do projeto e executar o comando `nvm use`, o NVM vai automaticamente encontrar o arquivo `.nvmrc` e utilizar a versão indicada.