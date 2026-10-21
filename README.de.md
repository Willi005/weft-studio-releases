<p align="center">
  <img src="assets/weft-studio.svg" width="112" alt="Der kleine Agent von Weft Studio" />
</p>

<h1 align="center">Weft Studio</h1>

<p align="center"><b>Gestalte Oberflächen zusammen mit deinem KI-Agenten, auf einer live bearbeitbaren Leinwand.</b><br />
Eine Desktop-App für Linux und Windows, die mit Claude Code, Codex, OpenCode und Antigravity funktioniert.</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.pt-BR.md">Português</a> ·
  <a href="README.fr.md">Français</a> ·
  <b>Deutsch</b> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a>
</p>

<p align="center">
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Version" src="https://img.shields.io/github/v/release/Willi005/weft-studio-releases?include_prereleases&label=version&color=6E56CF" /></a>
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/Willi005/weft-studio-releases/total?label=downloads&color=22C55E" /></a>
  <img alt="Linux x86_64" src="https://img.shields.io/badge/Linux-x86__64-FCC624?logo=linux&logoColor=black" />
  <img alt="Windows 11 x64" src="https://img.shields.io/badge/Windows%2011-x64-0078D6" />
  <img alt="Status: Beta" src="https://img.shields.io/badge/status-beta-F59E0B" />
</p>

<p align="center">
  <a href="https://willi005.github.io/weft-studio-releases/"><b>Website</b></a> ·
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><b>Download</b></a>
</p>

![Der Weft-Studio-Editor: eine Landingpage auf der Leinwand mit ausgewählter Überschrift, rechts der Stil-Inspektor und im Chat eine Anfrage an den Agenten](docs/assets/screenshots/editor-dark.webp)

**Weft Studio** (früher CodeWeaves Studio) ist ein Design-Werkzeug, in dem du und ein KI-Agent auf derselben Leinwand arbeiten. Beschreibe einen Bildschirm, sieh zu, wie der Agent ihn zeichnet, und verschiebe, gestalte oder schreibe ihn dann von Hand um. Jedes Design ist ein Frame, gespeichert als lesbare HTML-Datei (`design.ws.html`), mit einem eigenen Agenten: **Claude Code, Codex, OpenCode oder Antigravity**. Was du änderst und was der Agent schreibt, ist sofort zu sehen.

Dieses Repository veröffentlicht nur die Installationspakete; der Quellcode liegt nicht hier.

## Was du tun kannst

- **Mit Agenten gestalten:** beschreibe, was du willst, und probiere 1, 2 oder 3 Richtungen parallel aus, jede mit eigenem Agenten, Modell und Aufwand. Der Agent kann vorher Fragen stellen, andere genannte Frames lesen und angehängte Bilder verwenden.
- **Live von Hand bearbeiten:** auswählen, verschieben und skalieren; Text und Stile im Inspektor (Simple, Pro, Code und Tweaks); Ebenen, Zeichenwerkzeuge, Rückgängig und Wiederholen. Jede Änderung speichert sich selbst, und jedes Design hat seinen Versionsverlauf.
- **Apps mit mehreren Bildschirmen:** ein Design kann seine Ansichten deklarieren (Start, Preise, Kontakt…), und die Leinwand zeigt einen Frame pro Ansicht desselben Dokuments.
- **Eigene Dateien:** das **Assets**-Panel lädt Bilder, GIFs und Videos in ein Design. Der Agent kennt sie und verwendet sie.
- **Kommentieren und präsentieren:** an Elementen verankerte Kommentare und **Present** im Vollbild, interaktiv und live.
- **Exportieren und importieren:** lesbares HTML mit Runtime, das in jedem Browser läuft; ZIP mit Design, Runtime und Assets; PNG und JPEG. **Import** öffnet diese Dateien wieder, ebenso `.dc.html`-Dateien aus Claude Design.
- **Das Design in deinen Code bringen:** „Send to a coding agent…" kopiert einen Prompt, damit Claude Code, Codex, Gemini CLI oder OpenCode das Design über einen schreibgeschützten **MCP**-Server lesen und in dein Projekt übernehmen.
- **Projekte:** ein Startbildschirm mit Titelbildern, Umbenennen und Papierkorb.

![Drei Designs nebeneinander auf der Leinwand: eine Reise-Landingpage, eine Kaffee-Bestell-App und ein Analyse-Dashboard](docs/assets/screenshots/canvas-dark.webp)

## Installation

Lade die neueste Version unter [Releases](https://github.com/Willi005/weft-studio-releases/releases) herunter.

| System | Datei | So geht's |
| --- | --- | --- |
| Linux x86_64 | `Weft-Studio-<version>-x86_64.AppImage` | `chmod +x` und öffnen; beim ersten Start erscheint sie im Anwendungsmenü |
| Debian / Ubuntu | `weft-studio_<version>_amd64.deb` | `sudo apt install ./weft-studio_<version>_amd64.deb` (installiert auch git) |
| Windows 11 x64 | `Weft-Studio-<version>-x64-Setup.exe` | Ausführen; installiert für deinen Benutzer, ohne Administratorrechte |

**Voraussetzungen:**
- **git** (unter Windows [Git for Windows](https://git-scm.com/download/win)).
- Mindestens ein Agent mit Konto. Der Willkommensbildschirm und **Settings → Providers** erkennen vorhandene Agenten, bieten an, fehlende mit dem offiziellen Installer einzurichten (der Befehl wird vorher angezeigt), und melden dich an. Modelle anderer Anbieter kommen über OpenCode.
- Node.js ist nicht nötig, außer um OpenCode unter Windows zu installieren (über npm).

**Der Windows-Installer ist noch nicht signiert**, daher kann Windows vor einem unbekannten Herausgeber warnen. Um einen Download zu prüfen, vergleiche seine Prüfsumme mit der in `SHA256SUMS.txt` der jeweiligen Release:
- Linux: `sha256sum <datei>`
- Windows (PowerShell): `Get-FileHash <datei>`

## Updates

Die App sucht beim Öffnen und alle sechs Stunden in diesem Repository nach neuen Versionen und zeigt, was neu ist. Sie lädt und installiert nur, wenn du es willst: **Update** lädt herunter, **Restart to update** installiert und startet die App neu, und **Settings → Updates** prüft sofort. AppImage, `.deb` und der Windows-Installer aktualisieren sich aus der App heraus.

## Status

Weft Studio ist in der **Beta** (`0.2.0-beta.N`), und jede Version erscheint als Prerelease. Die Neuerungen jeder Version stehen in den [Release Notes](https://github.com/Willi005/weft-studio-releases/releases).

Wenn dir das Projekt gefällt, hilft ein ⭐ anderen, es zu finden.
