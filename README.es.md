<p align="center">
  <img src="assets/weft-studio.svg" width="112" alt="El agentito de Weft Studio" />
</p>

<h1 align="center">Weft Studio</h1>

<p align="center"><b>Diseña interfaces junto a tu agente de IA, en un lienzo que se edita en vivo.</b><br />
Una app de escritorio para Linux y Windows que funciona con Claude Code, Codex, OpenCode y Antigravity.</p>

<p align="center">
  <a href="README.md">English</a> ·
  <b>Español</b> ·
  <a href="README.pt-BR.md">Português</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a>
</p>

<p align="center">
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Versión" src="https://img.shields.io/github/v/release/Willi005/weft-studio-releases?include_prereleases&label=versi%C3%B3n&color=6E56CF" /></a>
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Descargas" src="https://img.shields.io/github/downloads/Willi005/weft-studio-releases/total?label=descargas&color=22C55E" /></a>
  <img alt="Linux x86_64" src="https://img.shields.io/badge/Linux-x86__64-FCC624?logo=linux&logoColor=black" />
  <img alt="Windows 11 x64" src="https://img.shields.io/badge/Windows%2011-x64-0078D6" />
  <img alt="Estado: beta" src="https://img.shields.io/badge/estado-beta-F59E0B" />
</p>

<p align="center">
  <a href="https://willi005.github.io/weft-studio-releases/es/"><b>Sitio web</b></a> ·
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><b>Descargar</b></a>
</p>

![El editor de Weft Studio: una landing en el lienzo con su titular seleccionado, el inspector de estilos a la derecha y un pedido al agente en el chat](docs/assets/screenshots/editor-dark.webp)

**Weft Studio** (antes CodeWeaves Studio) es una herramienta de diseño en la que tú y un agente de IA trabajáis sobre el mismo lienzo. Describes una pantalla, ves cómo el agente la dibuja y después la mueves, le cambias el estilo o la reescribes a mano. Cada diseño es un frame guardado como un archivo HTML legible (`design.ws.html`) y tiene su propio agente: **Claude Code, Codex, OpenCode o Antigravity**. Lo que cambias tú y lo que escribe el agente se ve al instante.

Este repositorio solo publica los instaladores; el código no está aquí.

## Qué puedes hacer

- **Diseñar con agentes:** describe lo que quieres y elige 1, 2 o 3 direcciones en paralelo, cada una con su agente, modelo y nivel de esfuerzo. El agente puede preguntarte antes de empezar, leer otros frames que nombres en el pedido y usar las imágenes que adjuntes.
- **Editar a mano en vivo:** seleccionar, mover y redimensionar; texto y estilos en el inspector (Simple, Pro, Code y Tweaks); capas, dibujo, deshacer y rehacer. Cada cambio se guarda solo y cada diseño tiene su historial de versiones.
- **Aplicaciones de varias pantallas:** un diseño puede declarar sus vistas (inicio, precios, contacto…) y el lienzo muestra un frame por vista sobre el mismo documento.
- **Tus propios archivos:** el panel **Assets** sube imágenes, GIF y vídeos al diseño. El agente sabe cuáles hay y los usa.
- **Comentar y presentar:** comentarios anclados a elementos y **Present** a pantalla completa, interactivo y en vivo.
- **Exportar e importar:** HTML legible con su runtime, que se abre en cualquier navegador; ZIP con el diseño, el runtime y los assets; PNG y JPEG. **Import** vuelve a abrir esos archivos, y también los `.dc.html` de Claude Design.
- **Llevar el diseño a tu código:** «Send to a coding agent…» copia un prompt para que Claude Code, Codex, Gemini CLI u OpenCode lean el diseño por **MCP** (solo lectura) y lo pasen a tu proyecto.
- **Proyectos:** un inicio con portadas, renombrado y papelera.

![Tres diseños uno al lado del otro en el lienzo: una landing de viajes, una app para pedir café y un panel de analítica](docs/assets/screenshots/canvas-dark.webp)

## Instalar

Descarga la última versión desde [Releases](https://github.com/Willi005/weft-studio-releases/releases).

| Sistema | Archivo | Cómo |
| --- | --- | --- |
| Linux x86_64 | `Weft-Studio-<versión>-x86_64.AppImage` | `chmod +x` y ábrela; la primera vez crea su entrada en el menú de aplicaciones |
| Debian / Ubuntu | `weft-studio_<versión>_amd64.deb` | `sudo apt install ./weft-studio_<versión>_amd64.deb` (instala también git) |
| Windows 11 x64 | `Weft-Studio-<versión>-x64-Setup.exe` | Ejecútalo; se instala por usuario, sin permisos de administrador |

**Requisitos:**
- **git** (en Windows, [Git for Windows](https://git-scm.com/download/win)).
- Al menos un agente con su cuenta. La bienvenida y **Settings → Providers** detectan cuáles tienes, te ofrecen instalar los que falten con su instalador oficial (te enseñan el comando antes de ejecutarlo) e iniciar sesión. Los modelos de otros proveedores llegan a través de OpenCode.
- No hace falta Node.js, salvo para instalar OpenCode en Windows (va por npm).

**El instalador de Windows todavía no está firmado**, así que Windows puede avisar de «editor desconocido». Para comprobar cualquier descarga, compara su suma con la de `SHA256SUMS.txt` de su release:
- Linux: `sha256sum <archivo>`
- Windows (PowerShell): `Get-FileHash <archivo>`

Al desinstalar en Windows, el desinstalador te pregunta aparte si borra la configuración y la caché y si borra las carpetas de proyectos. «No» es la respuesta por defecto en las dos.

## Actualizaciones

La app busca versiones nuevas en este repositorio al abrirse y cada seis horas, y avisa con las novedades. Solo descarga e instala cuando tú lo pides: **Update** descarga la versión, **Restart to update** la instala y vuelve a abrir la app, y **Settings → Updates** busca en el momento. La AppImage, el `.deb` y el instalador de Windows se actualizan desde la app.

**¿Vienes de CodeWeaves Studio?** Se actualiza sola a Weft Studio y conserva tus proyectos, cuentas y ajustes. Hasta la 0.2.0-beta.6 los archivos se llamaban `CodeWeaves-Studio-<versión>-x86_64.AppImage`, `codeweaves-studio_<versión>_amd64.deb` y `CodeWeaves-Studio-<versión>-x64-Setup.exe`; cada release sigue llevando copias con esos nombres para las instalaciones antiguas.

## Estado

Weft Studio está en **beta** (`0.2.0-beta.N`) y cada versión se publica como prerelease. Las novedades de cada una están en las notas de su [release](https://github.com/Willi005/weft-studio-releases/releases).

Si te gusta el proyecto, una ⭐ ayuda a que más gente lo encuentre.
