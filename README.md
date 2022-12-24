# Design Project CI/CD

## Available Scripts

To start the electron app

### `npm run electron`

<br/>
Code responsible to run the electron and react together
https://github.com/Anmol-Dhiman/Design-Project/blob/e67dbe099869e18b0059b1600d748d0038c0cf01/frontend/public/main.js#L7-L22

```javascript
//custom scripts to run and build electron app

"electron": "concurrently -k \"cross-env BROWSER=none npm start\" \"npm run electron:start\"",
"electron:start": "wait-on tcp:127.0.0.1:3000 && electron .",
"electron:build": "npm run build && electron-builder -c.extraMetadata.main=build/main.js"
```

Extension to install
<br/>
![TODO-Highlight](vscode:extension/wayou.vscode-todo-highlight)
