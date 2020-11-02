# keytool

O keytool é um utilitário de gerenciamento de chaves e certificados. Ele permite que os usuários administrem seus próprios pares de chaves pública/privada e certificados associados para uso na auto-autenticação (onde o usuário se autentica para outros usuários/serviços) ou integridade de dados e serviços de autenticação, usando assinaturas digitais.

## Documentação

Clique [aqui](https://docs.oracle.com/javase/7/docs/technotes/tools/windows/keytool.html) para ver a documentação.

## Acesso ao Aplicativo

No Windows o keytool está na pasta `C:\Program Files\Java\jdkx.x.x_x\bin` e no Linux ou macOS, o aplicativo está presente de forma global.

## Gerar Assinatura da APK

Para gerar a assinatura da APK, execute o seguinte comando no terminal (no Windows precisa estar na pasta onde está o keytool):

```
keytool -genkeypair -v -keystore <nome_keystore>.keystore -alias <nome_alias> -keyalg RSA -keysize 2048 -validity 10000
```

Onde: 

- `<nome_keystore>` - Nome da keystore, pode ser o mesmo da aplicação
- `<nome_alias>` - Nome do alias, pode ser o mesmo da keystore

Aparecerá as seguintes perguntas:

<sub> Informe a senha da área de armazenamento de chaves: **Digite uma senha. Ex: 123456** </sub>

<sub> Informe novamente a nova senha: **Digite a mesma senha de anteriormente** </sub>

<sub> Qual é o seu nome e o seu sobrenome? **Digite seu nome e sobrenome** </sub>

<sub> Qual é o nome da sua unidade organizacional? **Digite o nome da sua unidade organizacional** </sub>

<sub> Qual é o nome da sua empresa? **Digite o nome da sua empresa** </sub>

<sub> Qual é o nome da sua Cidade ou Localidade? **Digite o nome da sua cidade** </sub>

<sub> Qual é o nome do seu Estado ou Município? **Digite o nome do estado** </sub>

<sub> Quais são as duas letras do código do país desta unidade? **Digite as duas letras do código do país** </sub>

<sub> `<dados_informados>` Está correto? **sim (se tiver em português) ou yes (se tiver em inglês)** </sub>

<sub>Informar a senha da chave de `<nome_alias>` (RETURN) se for igual à senha da área do armazenamento de chaves): [Armazenando `<nome_keystore>`]**Digite uma nova senha ou dê Enter para usar a mesma senha da área de armazenamento de chaves**</sub>

Depois de concluído, aparecerá um arquivo de extensão keystore na pasta.