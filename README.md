# Design Project CI/CD

## Available Scripts

To start the electron app

### `npm run electron`

<br/>

```javascript
//Code responsible to run the electron and react together
function createWindow() {
  const main = new BrowserWindow({
    width: 800,
    height: 600,
    webPreferences: {
      nodeIntegration: true,
      enableRemoteModule: true,
    },
  });

  main.loadURL(
    isDev
      ? "http://localhost:3000"
      : `file://${path.join(__dirname, "../build/index.html")}`
  );
}
```

```javascript
//custom scripts to run and build electron app

"electron": "concurrently -k \"cross-env BROWSER=none npm start\" \"npm run electron:start\"",
"electron:start": "wait-on tcp:127.0.0.1:3000 && electron .",
"electron:build": "npm run build && electron-builder -c.extraMetadata.main=build/main.js"
```

Extension to install
<br/>
![TODO-Highlight](vscode:extension/wayou.vscode-todo-highlight)
