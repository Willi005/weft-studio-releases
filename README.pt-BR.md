<p align="center">
  <img src="assets/weft-studio.svg" width="112" alt="O agentezinho do Weft Studio" />
</p>

<h1 align="center">Weft Studio</h1>

<p align="center"><b>Crie interfaces junto com seu agente de IA, em um canvas editável ao vivo.</b><br />
Um app desktop para Linux e Windows que funciona com Claude Code, Codex, OpenCode e Antigravity.</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <b>Português</b> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <a href="README.ja.md">日本語</a>
</p>

<p align="center">
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Versão" src="https://img.shields.io/github/v/release/Willi005/weft-studio-releases?include_prereleases&label=vers%C3%A3o&color=6E56CF" /></a>
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/Willi005/weft-studio-releases/total?label=downloads&color=22C55E" /></a>
  <img alt="Linux x86_64" src="https://img.shields.io/badge/Linux-x86__64-FCC624?logo=linux&logoColor=black" />
  <img alt="Windows 11 x64" src="https://img.shields.io/badge/Windows%2011-x64-0078D6" />
  <img alt="Status: beta" src="https://img.shields.io/badge/status-beta-F59E0B" />
</p>

<p align="center">
  <a href="https://willi005.github.io/weft-studio-releases/"><b>Site</b></a> ·
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><b>Baixar</b></a>
</p>

![O editor do Weft Studio: uma landing page no canvas com o título selecionado, o inspetor de estilos à direita e um pedido ao agente no chat](docs/assets/screenshots/editor-dark.webp)

**Weft Studio** (antes CodeWeaves Studio) é uma ferramenta de design em que você e um agente de IA trabalham no mesmo canvas. Descreva uma tela, veja o agente desenhá-la e depois mova, mude o estilo ou reescreva à mão. Cada design é um frame salvo como um arquivo HTML legível (`design.ws.html`) e tem seu próprio agente: **Claude Code, Codex, OpenCode ou Antigravity**. O que você muda e o que o agente escreve aparecem na hora.

Este repositório publica apenas os instaladores; o código-fonte não está aqui.

## O que você pode fazer

- **Criar com agentes:** descreva o que quer e experimente 1, 2 ou 3 direções em paralelo, cada uma com seu agente, modelo e nível de esforço. O agente pode fazer perguntas antes de começar, ler outros frames que você mencionar e usar imagens anexadas.
- **Editar à mão, ao vivo:** selecionar, mover e redimensionar; texto e estilos no inspetor (Simple, Pro, Code e Tweaks); camadas, ferramentas de desenho, desfazer e refazer. Cada mudança é salva sozinha e cada design tem seu histórico de versões.
- **Apps com várias telas:** um design pode declarar suas views (início, preços, contato…) e o canvas mostra um frame por view do mesmo documento.
- **Seus próprios arquivos:** o painel **Assets** envia imagens, GIFs e vídeos para o design. O agente sabe quais existem e os usa.
- **Comentar e apresentar:** comentários presos a elementos e **Present** em tela cheia, interativo e ao vivo.
- **Exportar e importar:** HTML legível com seu runtime, que abre em qualquer navegador; ZIP com o design, o runtime e os assets; PNG e JPEG. **Import** reabre esses arquivos e também os `.dc.html` do Claude Design.
- **Levar o design para o seu código:** "Send to a coding agent…" copia um prompt para que Claude Code, Codex, Gemini CLI ou OpenCode leiam o design por um servidor **MCP** somente leitura e o implementem no seu projeto.
- **Projetos:** uma tela inicial com capas, renomear e lixeira.

![Três designs lado a lado no canvas: uma landing page de viagens, um app para pedir café e um painel de análise](docs/assets/screenshots/canvas-dark.webp)

## Instalar

Baixe a versão mais recente em [Releases](https://github.com/Willi005/weft-studio-releases/releases).

| Sistema | Arquivo | Como |
| --- | --- | --- |
| Linux x86_64 | `Weft-Studio-<versão>-x86_64.AppImage` | `chmod +x` e abra; na primeira vez ele entra no menu de aplicativos |
| Debian / Ubuntu | `weft-studio_<versão>_amd64.deb` | `sudo apt install ./weft-studio_<versão>_amd64.deb` (instala também o git) |
| Windows 11 x64 | `Weft-Studio-<versão>-x64-Setup.exe` | Execute; instala para o seu usuário, sem permissões de administrador |

**Requisitos:**
- **git** (no Windows, [Git for Windows](https://git-scm.com/download/win)).
- Pelo menos um agente com sua conta. A tela de boas-vindas e **Settings → Providers** detectam os que você tem, oferecem instalar os que faltam com o instalador oficial (mostrando o comando antes) e fazem o login. Modelos de outros provedores chegam pelo OpenCode.
- Não precisa de Node.js, exceto para instalar o OpenCode no Windows (via npm).

**O instalador do Windows ainda não é assinado**, então o Windows pode avisar sobre um editor desconhecido. Para conferir qualquer download, compare o checksum com o do `SHA256SUMS.txt` da release:
- Linux: `sha256sum <arquivo>`
- Windows (PowerShell): `Get-FileHash <arquivo>`

## Atualizações

O app procura novas versões neste repositório ao abrir e a cada seis horas, e mostra as novidades. Ele só baixa e instala quando você pede: **Update** baixa, **Restart to update** instala e reabre o app, e **Settings → Updates** verifica na hora. A AppImage, o `.deb` e o instalador do Windows se atualizam pelo próprio app.

## Status

O Weft Studio está em **beta** (`0.2.0-beta.N`) e cada versão é publicada como prerelease. As novidades de cada uma estão nas [notas da release](https://github.com/Willi005/weft-studio-releases/releases).

Se você gostou do projeto, uma ⭐ ajuda outras pessoas a encontrá-lo.
