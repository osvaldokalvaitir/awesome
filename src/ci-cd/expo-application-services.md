# Expo Application Services

Expo Application Services (EAS) é um conjunto de serviços em nuvem hospedados para aplicativos Expo e React Native, incluindo builds nativas, atualizações over-the-air e envios para lojas de aplicativos.

## Documentação e Acesso ao Serviço

Clique [aqui](https://expo.dev/eas) para ver a documentação e acessar o serviço.

## Instalação do CLI

Instalação global do CLI do EAS:

```
npm install -g eas-cli
```

## Autenticação

Verificar se o usuário está logado:

```
eas whoami
```

Para logar com um usuário:

```
eas login
```

Para deslogar com um usuário:

```
eas logout
```

## Configuração

Iniciar a configuração do EAS:

```
eas build:configure
```

Pode escolher por etapa ou todas as plataformas.

## Build Local

Gerar build APK local do Android com EAS:

```
eas build -p android --profile preview --local
```

Gerar build IPA local do iOS com EAS:

```
eas build -p ios --profile preview --local
```

## Build na Nuvem

Gerar build interna de testes do Android na cloud do EAS:

```
eas build -p android --profile preview
```

Gerar build de produção do Android na cloud do EAS:

```
eas build -p android --profile production --message "first production deploy"
```

Gerar build de produção do iOS na cloud do EAS:

```
eas build -p ios --profile production --message "first production deploy"
```

## Versionamento

Definindo a versão de referência:

```
eas build:version:set
```

Depois escolher a plataforma e versão.

## Expo Update

Configurar Expo Update depois de instalar o [expo-updates](../runtime/nodejs/libs/expo-updates.md):

```
eas update:configure
```

Atualizar build:

```
eas update --branch preview --message "alguma mensagem"
```