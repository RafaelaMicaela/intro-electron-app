# Criando uma aplicação em Electron

## Pré-Requisitos

Pra usar o Electron, é necessário instalar o [`Nodejs`](https://nodejs.org/en) e usar a versão mais recente disponível.

```sh
node -v
npm -v
```

## Crie seu aplicativo

aplicativos Electron seguem a mesma estrutural geral que outros projetos Node.js. vamos começar criando uma pasta

```sh
mkdir my-electron-app && cd my-electron-app
```

abra a pasta no seu Vscode e abra o terminal e digite o comando pra iniciar um projeto node

```sh
npm init 
```

Em seguida, instale o pacote `electron` nas `devDependencies` do seu aplicativo

```sh
npm install --save-dev electron
```

No campo `scripst` do seu `package.json` configure adicionado o comando `start` assim:

```sh
  "scripts": {
     "start": "electron ."
  }
```

## Crie uma página web

crie um arquivo `index.html` na pasta raíz do seu projeto

```sh
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ola Mundo</title>
</head>
<body>
    <h1>Ola Mundo </h1>
    <P>Minha primeira aplicação Electron👋</P>
</body>
</html>
```

## Abrindo sua página web em uma janela do navegador

crie um arquivo `index.js` na pasta raíz do seu projeto e configure adicionando o módulo `app` e `BrowserWindow`

```sh
const { app, BrowserWindow } = require('electron')
```

adicione o conteúdo do seu index.js pelo código a seguir.

```sh
const createWindow = () => {
  const win = new BrowserWindow({
    width: 800,
    height: 600
  })

  win.loadFile('index.html')
}

app.whenReady().then(() => {
  createWindow()
}) 
```

## Rodando o projeto

pra rodar a aplicação digite o comando `npm start` no seu terminal.

```sh
npm start
```
