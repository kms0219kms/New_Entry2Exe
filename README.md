<p align="center"><img src="./app/assets/images/SealCircle.png" width="150px" height="150px" alt="aventium softworks"></p>

<h1 align="center">Entry to EXE</h1>

<em><h5 align="center">(formerly Electron Launcher)</h5></em>

[<p align="center"><img src="https://img.shields.io/travis/kms0219kms/New_Entry2Exe.svg?style=for-the-badge" alt="travis">](https://travis-ci.org/kms0219kms/New_Entry2Exe) [<img src="https://img.shields.io/github/downloads/kms0219kms/New_Entry2Exe/total.svg?style=for-the-badge" alt="downloads">](https://github.com/kms0219kms/New_Entry2Exe/releases) <img src="https://forthebadge.com/images/badges/winter-is-coming.svg"  height="28px" alt="stark"></p>

## Tutorial
[![Tutorials](http://img.youtube.com/vi/JoywV6YmlKI/maxresdefault.jpg)](http://www.youtube.com/watch?v=JoywV6YmlKI "[4K] [Tip! Tip! Tip!] 엔트리(ent) 파일을 실행 파일(exe)로 간단하게 변환하기 [2차 개정판]")

## Downloads

You can download from [GitHub Releases](https://github.com/kms0219kms/New_Entry2Exe/releases)

#### Latest Release

[![](https://img.shields.io/github/release/kms0219kms/New_Entry2Exe.svg?style=flat-square)](https://github.com/kms0219kms/New_Entry2Exe/releases/latest)

#### Latest Pre-Release
[![](https://img.shields.io/github/release/kms0219kms/New_Entry2Exe/all.svg?style=flat-square)](https://github.com/kms0219kms/New_Entry2Exe/releases)

**Supported Platforms**

If you download from the [Releases](https://github.com/kms0219kms/New_Entry2Exe/releases) tab, select the installer for your system.

| Platform | File |
| -------- | ---- |
| Windows x64 | `your_program_name-setup-VERSION.exe` |
| macOS | `your_program_name-VERSION.dmg` |
| Linux x64 | `your_program_name-VERSION-x86_64.AppImage` |

## Console

To open the console, use the following keybind.

```console
ctrl + shift + i
```

Ensure that you have the console tab selected. Do not paste anything into the console unless you are 100% sure of what it will do. Pasting the wrong thing can expose sensitive information.

#### Export Output to a File

If you want to export the console output, simply right click anywhere on the console and click **Save as..**

![console example](https://i.imgur.com/T5e73jP.png)


## Development

### Getting Started

**System Requirements**

* [Node.js][nodejs] v12

---

**Clone and Install Dependencies**

```console
> git clone https://github.com/kms0219kms/New_Entry2Exe.git
> cd New_Entry2Exe
> npm install
```

---

**Launch Application**

```console
> npm start
```

---

**Build Installers**

To build for your current platform.

```console
> npm run dist
```

Build for a specific platform.

| Platform    | Command              |
| ----------- | -------------------- |
| Windows x64 | `npm run dist:win`   |
| macOS       | `npm run dist:mac`   |
| Linux x64   | `npm run dist:linux` |

Builds for macOS may not work on Windows/Linux and vice-versa.

---

### Visual Studio Code

All development of the launcher should be done using [Visual Studio Code][vscode].

Paste the following into `.vscode/launch.json`

```JSON
{
  "version": "0.2.0",
  "configurations": [
    {
      "name": "Debug Main Process",
      "type": "node",
      "request": "launch",
      "cwd": "${workspaceFolder}",
      "program": "${workspaceFolder}/node_modules/electron/cli.js",
      "args" : ["."],
      "outputCapture": "std"
    },
    {
      "name": "Debug Renderer Process",
      "type": "chrome",
      "request": "launch",
      "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron",
      "windows": {
        "runtimeExecutable": "${workspaceFolder}/node_modules/.bin/electron.cmd"
      },
      "runtimeArgs": [
        "${workspaceFolder}/.",
        "--remote-debugging-port=9222"
      ],
      "webRoot": "${workspaceFolder}"
    }
  ]
}
```

This adds two debug configurations.

#### Debug Main Process

This allows you to debug Electron's [main process][mainprocess]. You can debug scripts in the [renderer process][rendererprocess] by opening the DevTools Window.

#### Debug Renderer Process

This allows you to debug Electron's [renderer process][rendererprocess]. This requires you to install the [Debugger for Chrome][chromedebugger] extension.

Note that you **cannot** open the DevTools window while using this debug configuration. Chromium only allows one debugger, opening another will crash the program.

---

### Note on Third-Party Usage

You may use this software in your own project so long as the following conditions are met.

* Credit is expressly given to the original authors (Daniel Scalzi).
  * Include a link to the original source on the launcher's About page.
  * Credit the authors and provide a link to the original source in any publications or download pages.
* The source code remain **public** as a fork of this repository.

We reserve the right to update these conditions at any time, please check back periodically.

---

### See you ingame.


[nodejs]: https://nodejs.org/en/ 'Node.js'
[vscode]: https://code.visualstudio.com/ 'Visual Studio Code'
[mainprocess]: https://electronjs.org/docs/tutorial/application-architecture#main-and-renderer-processes 'Main Process'
[rendererprocess]: https://electronjs.org/docs/tutorial/application-architecture#main-and-renderer-processes 'Renderer Process'
[chromedebugger]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome 'Debugger for Chrome'
[discord]: https://discord.gg/zNWUXdt 'Discord'
[wiki]: https://github.com/dscalzi/HeliosLauncher/wiki 'wiki'
[nebula]: https://github.com/dscalzi/Nebula 'dscalzi/Nebula'
[v2branch]: https://github.com/dscalzi/HeliosLauncher/tree/ts-refactor 'v2 branch'
