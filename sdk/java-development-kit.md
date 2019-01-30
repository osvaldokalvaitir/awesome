# Java Development Kit (JDK)

Kit de Desenvolvimento Java é um conjunto de utilitários que permitem criar sistemas de software para a plataforma Java. É composto por compilador e bibliotecas.

## Instalação

`Atenção: A versão 8 do JDK é obrigatória, não utilize versões mais recentes. Caso esteja com o JDK instalado em sua máquina, certifique-se que sua versão seja a 8.`

- **Linux**

  Para instalar o JDK na versão 8, executar os seguintes comandos:

  ```
  sudo add-apt-repository ppa:openjdk-r/ppa
  sudo apt-get update
  sudo apt-get install openjdk-8-jdk
  ```

  Podemos testar a instalação do JDK com o seguinte comando:

  ```
  java -version
  ```

- **OS X**

  O JDK pode ser baixado pelo link `http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html`  

  Após instalado, execute o .dmg e instale seguindo os passos do instalador.

- **Windows usando Chocolatey**

  Para instalar o JDK, executar no Chocolatey o seguinte comando:

  ```
  choco install -y jdk8
  ```

## Documentação e Instalação

Clique [aqui](https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html) para ver a documentação e outras opções de instalação.
