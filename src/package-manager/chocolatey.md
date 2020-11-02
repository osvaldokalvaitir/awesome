# Chocolatey

Gerenciador de pacotes para o Windows.

## Documentação e Instalação

Clique [aqui](https://chocolatey.org/) para ver a documentação e outras opções de instalação.

## Instalação

Execute o prompt de comando ou powershell como administrador e siga os passos de acordo com o escolhido:

- **Command Prompt**

  Caso a opção tenha sido `Command Prompt`, execute o comando abaixo na janela aberta para instalar o Chocolatey:

  ```
  @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
  ```

- **Powershell**

  Caso a opção tenha sido `Powershell`, execute o comando abaixo para verificar se você possui permissões para instalar dependências com o terminal:

  ```
  Get-ExecutionPolicy
  ```

  Se o retorno desse comando for `“Restricted”`, execute o próximo comando em seu terminal, se não, prossiga para o próximo passo:

  ```
  Set-ExecutionPolicy AllSigned
  ```

  Agora, execute o seguinte comando para instalar o Chocolatey:

  ```
  Set-ExecutionPolicy Bypass -Scope Process -Force; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
  ```

Agora, teste se a instalação ocorreu corretamente executando o seguinte comando no seu terminal (nada irá acontecer, mas não deve retornar erros). Nesse passo pode ser necessário reiniciar seu terminal.

```
choco
```
