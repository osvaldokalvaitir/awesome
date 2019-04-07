# Android SDK

Kit de Desenvolvimento de Software para Android é um pacote com diversas ferramentas utilizadas pelo Android Studio e pelos desenvolvedores Android, incluindo componentes como o SDK Tools, Build Tools e o Platform Tools.

## Instalação e Configuração

Acesse `https://developer.android.com/studio/#downloads`, na opção `Somente ferramentas de linha de comando` baixe o SDK referente ao seu sistema operacional.

- **Linux/macOS**

  Crie uma pasta em um local desejado para instalação do SDK. Ex: `~/Android/Sdk`

  Após realizado o download, extraia o conteúdo do pacote para a pasta criada anteriormente.

  Com esse endereço precisamos configurar algumas variáveis ambiente em nosso sistema, procure pelo primeiro dos seguintes arquivos existentes no seu sistema: `~/.bash_profile`, `~/.profile` ou `~/.zshrc`, e adicione essas três linhas no arquivo (de preferência no início):

  ```
  export ANDROID_HOME=~/Android/Sdk
  export PATH=$PATH:$ANDROID_HOME/tools
  export PATH=$PATH:$ANDROID_HOME/platform-tools
  ```

  `Se nenhum desses arquivos existir, crie o ~/.bash_profile. Caso esteja utilizando uma pasta diferente para a SDK do Android, altere acima.`

  Agora, abra seu terminal e execute o seguinte comando:

  ```
  ~/Android/Sdk/tools/bin/sdkmanager "platform-tools" "platforms;android-27" "build-tools;27.0.3"
  ```

  Aceite todas licensas digitando `y` caso necessário.

- **Windows**

  Crie uma pasta em um local desejado para instalação da SDK. Ex: `C:\Android\Sdk`.

  Após realizado o download, extraia o conteúdo do pacote para a pasta criada anteriormente.

  Agora, no Painel de Controle do Windows, abra o item `Sistema e Segurança` ou `Sistema`, clique em `Configurações avançadas do sistema`, selecione `Variáveis de ambiente`. Na grade `Variáveis do sistema`, clique no botão `Novo...`, indique o nome da variável como `ANDROID_HOME`, adicione o caminho utilizado acima (Ex: `C:\Android\Sdk`) como segundo parâmetro e clique em OK.

  ![Android SDK 1](/assets/android-sdk/1.png)

  Na mesma grade `Variáveis do sistema`, clique na variável `PATH` e então em `Editar`. Haverá uma lista de caminhos e você deve adicionar esses dois novos caminhos no fim da lista:

  ```
  %ANDROID_HOME%\platform-tools
  %ANDROID_HOME%\tools
  ```

  Agora, abra seu Command Prompt ou PowerShell como administrador e execute o seguinte comando:

  ```
  C:\Android\Sdk\tools\bin\sdkmanager  "platform-tools" "platforms;android-27" "build-tools;27.0.3"
  ```

  Aceite todas licensas digitando `y` quando necessário.
