# Tutoriel Helios Launcher (Français)

## 1) Installation des logiciels nécessaire

Vous devez télécharger les logiciels nécessaires pour pouvoir cloner un répertoire Git, modifier le code et compiler le launcher

Vous aurez besoin de:

* [GitHub Desktop](https://desktop.github.com/)
* Un éditeur de code, nous utiliserons [Visual Studio Code](https://code.visualstudio.com/) (Recommandé pour suivre le tuto)
* [Node.js](https://nodejs.org/fr/) (Minimum v14)

## 2) Cloner le repertoire sur GitHub Desktop

Ouvrez **GitHub Desktop** et cliquez sur "File" puis "Clone repository..."

![Screenshot Github 1](https://i.imgur.com/LYGLoSR.png)

Puis entrez le lien suivant

```
https://github.com/ZaptoInc/HeliosLauncherFR
```

Puis cliquez sur "Clone"

![Screenshot Github 2](https://i.imgur.com/CFak3VY.png)

Ensuite **Github Desktop** vous demandera ce que vous voulez faire avec cette fork, cliquez sur "For my own purposes" et cliquez sur "Continue"

![Screenshot Github 3](https://i.imgur.com/adqeb9R.png)

Enfin, dans "Open the repository in your external editor", cliquez sur "Open in Visual Studio Code"

![Screenshot Github 4](https://i.imgur.com/BaOz65s.png)

## 4) Ouvrir la console

Une fois **Visual Studio Code** ouvert, cliquez sur "Terminal" puis "New Terminal"

![Screenshot Visual Studio Code 1](https://i.imgur.com/Xveaqpz.png)

Un terminal devrait s'ouvrir en bas

![Screenshot Visual Studio Code 2](https://i.imgur.com/qm9UOMv.png)

## 4) Installer les dépendances

Entrez dans le terminal: 

```console
> npm install
```

Patientez que **Node.js** télécharge et installe les dépendances necessaire.

Le résultat devrait ressembler à peu près à ceci:

![Screenshot Visual Studio Code 3](https://i.imgur.com/5u18mTi.png)

## 5) Modification requise

Pour votre launcher, vous aurez besoin d'un identifiant d'application et d'un nom de produit

Pour le tuto, j'ai choisi `aventurelauncher` comme nom identifiant d'application et `Aventure Launcher` comme nom de produit

⚠️ **Attention!** ⚠️

L'identifiant d'application doit être en minuscule, sans espace et uniquement contenir des lettres des chiffres, des tirets du 8 (_) ou des tirets du 6 (-)

---

Ouvrir le fichier `package.json` et modifier la ligne 2 et remplacer `helioslauncherfr` par votre identifiant d'application



