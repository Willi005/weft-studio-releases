<p align="center">
  <img src="assets/weft-studio.svg" width="112" alt="Le petit agent de Weft Studio" />
</p>

<h1 align="center">Weft Studio</h1>

<p align="center"><b>Concevez des interfaces avec votre agent IA, sur un canevas modifiable en direct.</b><br />
Une application de bureau pour Linux et Windows, compatible avec Claude Code, Codex, OpenCode et Antigravity.</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.pt-BR.md">Português</a> ·
  <b>Français</b> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a>
</p>

<p align="center">
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Version" src="https://img.shields.io/github/v/release/Willi005/weft-studio-releases?include_prereleases&label=version&color=6E56CF" /></a>
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Téléchargements" src="https://img.shields.io/github/downloads/Willi005/weft-studio-releases/total?label=t%C3%A9l%C3%A9chargements&color=22C55E" /></a>
  <img alt="Linux x86_64" src="https://img.shields.io/badge/Linux-x86__64-FCC624?logo=linux&logoColor=black" />
  <img alt="Windows 11 x64" src="https://img.shields.io/badge/Windows%2011-x64-0078D6" />
  <img alt="Statut : bêta" src="https://img.shields.io/badge/statut-b%C3%AAta-F59E0B" />
</p>

<p align="center">
  <a href="https://willi005.github.io/weft-studio-releases/"><b>Site web</b></a> ·
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><b>Télécharger</b></a>
</p>

![L'éditeur Weft Studio : une landing page sur le canevas avec son titre sélectionné, l'inspecteur de styles à droite et une demande à l'agent dans le chat](docs/assets/screenshots/editor-dark.webp)

**Weft Studio** est un outil de design où vous et un agent IA travaillez sur le même canevas. Décrivez un écran, regardez l'agent le dessiner, puis déplacez-le, changez son style ou réécrivez-le à la main. Chaque design est un frame enregistré dans un fichier HTML lisible (`design.ws.html`) et possède son propre agent : **Claude Code, Codex, OpenCode ou Antigravity**. Vos modifications et ce qu'écrit l'agent apparaissent instantanément.

Ce dépôt ne publie que les installateurs ; le code source n'est pas ici.

## Ce que vous pouvez faire

- **Concevoir avec des agents :** décrivez ce que vous voulez et essayez 1, 2 ou 3 directions en parallèle, chacune avec son agent, son modèle et son niveau d'effort. L'agent peut vous poser des questions d'abord, lire d'autres frames que vous mentionnez et utiliser les images jointes.
- **Modifier à la main, en direct :** sélectionner, déplacer et redimensionner ; texte et styles dans l'inspecteur (Simple, Pro, Code et Tweaks) ; calques, outils de dessin, annuler et rétablir. Chaque modification s'enregistre seule et chaque design a son historique de versions.
- **Applications multi-écrans :** un design peut déclarer ses vues (accueil, tarifs, contact…) et le canevas affiche un frame par vue du même document.
- **Vos propres fichiers :** le panneau **Assets** importe images, GIF et vidéos dans un design. L'agent sait qu'ils existent et les utilise.
- **Commenter et présenter :** commentaires ancrés aux éléments et **Present** en plein écran, interactif et en direct.
- **Exporter et importer :** HTML lisible avec son runtime, qui s'ouvre dans n'importe quel navigateur ; ZIP avec le design, le runtime et les assets ; PNG et JPEG. **Import** rouvre ces fichiers, ainsi que les `.dc.html` de Claude Design.
- **Passer le design à votre code :** « Send to a coding agent… » copie un prompt pour que Claude Code, Codex, Gemini CLI ou OpenCode lisent le design via un serveur **MCP** en lecture seule et l'intègrent à votre projet.
- **Projets :** un écran d'accueil avec couvertures, renommage et corbeille.

![Trois designs côte à côte sur le canevas : une landing page de voyage, une application de commande de café et un tableau de bord analytique](docs/assets/screenshots/canvas-dark.webp)

## Installation

Téléchargez la dernière version depuis [Releases](https://github.com/Willi005/weft-studio-releases/releases).

| Système | Fichier | Comment |
| --- | --- | --- |
| Linux x86_64 | `Weft-Studio-<version>-x86_64.AppImage` | `chmod +x` puis ouvrez-la ; au premier lancement elle s'ajoute au menu des applications |
| Debian / Ubuntu | `weft-studio_<version>_amd64.deb` | `sudo apt install ./weft-studio_<version>_amd64.deb` (installe aussi git) |
| Windows 11 x64 | `Weft-Studio-<version>-x64-Setup.exe` | Lancez-le ; il s'installe pour votre utilisateur, sans droits d'administrateur |

**Prérequis :**
- **git** (sous Windows, [Git for Windows](https://git-scm.com/download/win)).
- Au moins un agent avec son compte. L'écran d'accueil et **Settings → Providers** détectent ceux que vous avez, proposent d'installer les autres avec leur installateur officiel (en montrant la commande avant) et vous connectent. Les modèles d'autres fournisseurs passent par OpenCode.
- Node.js n'est pas nécessaire, sauf pour installer OpenCode sous Windows (via npm).

**L'installateur Windows n'est pas encore signé**, Windows peut donc signaler un éditeur inconnu. Pour vérifier un téléchargement, comparez sa somme de contrôle avec celle du `SHA256SUMS.txt` de la release :
- Linux : `sha256sum <fichier>`
- Windows (PowerShell) : `Get-FileHash <fichier>`

## Mises à jour

L'application cherche de nouvelles versions dans ce dépôt à l'ouverture et toutes les six heures, et vous présente les nouveautés. Elle ne télécharge et n'installe que si vous le demandez : **Update** télécharge, **Restart to update** installe et relance l'application, et **Settings → Updates** vérifie immédiatement. L'AppImage, le `.deb` et l'installateur Windows se mettent à jour depuis l'application.

## Statut

Weft Studio est en **bêta** (`0.2.0-beta.N`) et chaque version est publiée en prerelease. Les nouveautés de chacune sont dans ses [notes de version](https://github.com/Willi005/weft-studio-releases/releases).

Si le projet vous plaît, une ⭐ aide d'autres personnes à le trouver.
