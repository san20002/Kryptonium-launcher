<p align="center"><img src="./app/assets/images/SealCircle.png" width="150px" height="150px" alt="aventium softworks"></p>

<h1 align="center">HeliosLauncherFR</h1>

<em><h5 align="center">(Ancien Launcher Electron)</h5></em>

[<p align="center"><img src="https://img.shields.io/travis/dscalzi/HeliosLauncher.svg?style=for-the-badge" alt="travis">](https://travis-ci.org/dscalzi/HeliosLauncher) [<img src="https://img.shields.io/github/downloads/dscalzi/HeliosLauncher/total.svg?style=for-the-badge" alt="downloads">](https://github.com/dscalzi/HeliosLauncher/releases) <img src="https://forthebadge.com/images/badges/winter-is-coming.svg"  height="28px" alt="stark"></p>

<p align="center">Rejoignez des serveurs moddés sans vous soucier d'installer Java, Forge ou d'autres mods. Nous nous en occuperons pour vous.</p>

![Screenshot 1](https://i.imgur.com/7uqUPnB.png)
![Screenshot 2](https://i.imgur.com/2SosdCr.png)

## Fonctionnalités

* 🔒 Gestion complète des comptes.
  * Possibilité d'ajouter plusieurs comptes et changer facilement entre eux.
  * Les informations d'identification ne sont jamais stockées et transmises directement à Mojang.
* 📂 Gestion efficace des assets.
  * Recevez les mises à jour du client dès que nous les publions.
  * Les fichiers sont validés avant le lancement. Les fichiers corrompus ou incorrects seront retéléchargés.
* ☕ **Validation automatique de Java.**
  * Si vous avez une version incompatible de Java installée, nous installerons la bonne *pour vous*.
  * Vous n'avez pas besoin d'installer Java pour exécuter le launcher.
* 📰 Flux d'actualités intégré nativement dans le launcher.
* ⚙️ Gestion intuitive des paramètres, y compris un panneau de configuration Java.
* Prend en charge tous nos serveurs.
  * Changez facilement entre les configurations de serveur.
  * Affiche le nombre de joueurs du serveur sélectionné.
* Mises à jour automatiques. C'est vrai, le launcher se met à jour tout seul.
*  Voir l'état des services de Mojang.

Cette liste n'est pas exhaustive. Téléchargez et installez le launcher pour voir tout ce qu'il peut faire!

#### Besoin d'aide? [Consultez le wiki.][wiki]

#### Vous aimez le projet? Laisser une ⭐ étoile sur la repo!

**Plateformes prises en charge**

| Plateforme | Fichier |
| -------- | ---- |
| Windows x64 | `helioslauncherfr-setup-VERSION.exe` |
| macOS | `helioslauncherfr-setup-VERSION.dmg` |
| Linux x64 | `helioslauncherfr-setup-VERSION.AppImage` |

## Console

Pour ouvrir la console, utilisez la combinaison de touches suivante.

```console
ctrl + shift + i
```

Assurez-vous que l'onglet de la console est sélectionné. Ne collez rien dans la console à moins d'être sûr à 100% de ce que ça va faire. Coller la mauvaise chose peut exposer des informations sensibles.

#### Exporter la sortie vers un fichier

Si vous souhaitez exporter la sortie de la console, cliquez simplement avec le bouton droit n'importe où sur la console et cliquez sur **Enregistrer sous ..**

![example de console](https://i.imgur.com/T5e73jP.png)


## Développement

Cette section détaille la configuration d'un environnement de développement de base.

### Mise en route

**Configuration requise**

* [Node.js][nodejs] v14

---

**Cloner et installer les dépendances**

```console
> git clone https://github.com/dscalzi/HeliosLauncher.git
> cd HeliosLauncherFR
> npm install
```

---

**Lancer l'application**

```console
> npm start
```

---

**Generer les installateurs**

À construire sur votre plate-forme actuelle.

```console
> npm run dist
```

Generer pour une plate-forme spécifique.

| Platform    | Command              |
| ----------- | -------------------- |
| Windows x64 | `npm run dist:win`   |
| macOS       | `npm run dist:mac`   |
| Linux x64   | `npm run dist:linux` |

La génération pour macOS peut ne pas fonctionner sous Windows/Linux et vice-versa.

---

### Visual Studio Code

Tout le développement du launcher doit être effectué en utilisant [Visual Studio Code][vscode].

Collez ce qui suit dans `.vscode/launch.json`

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

## Resources

* [Wiki][wiki]
* [Nebula (Create Distribution.json)][nebula]
* [v2 Rewrite Branch (WIP)][v2branch]

The best way to contact the developers is on Discord.

[![discord](https://discordapp.com/api/guilds/211524927831015424/embed.png?style=banner3)][discord]

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
