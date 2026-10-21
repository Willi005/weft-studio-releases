<p align="center">
  <img src="assets/weft-studio.svg" width="112" alt="Weft Studio 的小助手" />
</p>

<h1 align="center">Weft Studio</h1>

<p align="center"><b>与你的 AI 智能体一起，在实时编辑的画布上设计界面。</b><br />
适用于 Linux 和 Windows 的桌面应用，支持 Claude Code、Codex、OpenCode 和 Antigravity。</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.pt-BR.md">Português</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <b>简体中文</b> ·
  <a href="README.ja.md">日本語</a>
</p>

<p align="center">
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="版本" src="https://img.shields.io/github/v/release/Willi005/weft-studio-releases?include_prereleases&label=version&color=6E56CF" /></a>
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="下载量" src="https://img.shields.io/github/downloads/Willi005/weft-studio-releases/total?label=downloads&color=22C55E" /></a>
  <img alt="Linux x86_64" src="https://img.shields.io/badge/Linux-x86__64-FCC624?logo=linux&logoColor=black" />
  <img alt="Windows 11 x64" src="https://img.shields.io/badge/Windows%2011-x64-0078D6" />
  <img alt="状态：beta" src="https://img.shields.io/badge/status-beta-F59E0B" />
</p>

<p align="center">
  <a href="https://willi005.github.io/weft-studio-releases/"><b>官网</b></a> ·
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><b>下载</b></a>
</p>

![Weft Studio 编辑器：画布上一个法律助手落地页的标题被选中，右侧是样式检查器，左侧是与智能体的对话](docs/assets/screenshots/editor-dark.webp)

**Weft Studio**是一款设计工具，你和 AI 编程智能体在同一块画布上协作。描述一个页面，看着智能体把它画出来，然后亲手移动、调整样式或改写。每个设计都是一个画框（frame），保存为可读的 HTML 文件（`design.ws.html`），并拥有自己的智能体：**Claude Code、Codex、OpenCode 或 Antigravity**。你的改动和智能体写入的内容都会立即显示。

本仓库只发布安装包，源代码不在这里。

## 你可以做什么

- **与智能体一起设计：** 描述你的需求，并行尝试 1、2 或 3 个方向，每个方向都有自己的智能体、模型和思考强度。智能体可以先向你提问、读取你提到的其他画框，并使用你附加的图片。
- **实时手动编辑：** 选择、移动和缩放；在检查器（Simple、Pro、Code 和 Tweaks）中修改文字和样式；图层、绘图工具、撤销和重做。每次改动都会自动保存，每个设计都有自己的版本历史。
- **多页面应用：** 一个设计可以声明多个视图（首页、价格、联系…），画布会为同一文档的每个视图显示一个画框。
- **你自己的文件：** **Assets** 面板可以把图片、GIF 和视频上传到设计中，智能体知道它们并会使用。
- **评论与演示：** 固定在元素上的评论，以及全屏、可交互、实时的 **Present** 模式。
- **导出与导入：** 带运行时的可读 HTML，可在任意浏览器中打开；包含设计、运行时和素材的 ZIP；PNG 和 JPEG。**Import** 可以重新打开这些文件，也支持 Claude Design 的 `.dc.html` 文件。
- **把设计交给你的代码：** “Send to a coding agent…” 会复制一段提示词，让 Claude Code、Codex、Gemini CLI 或 OpenCode 通过只读的 **MCP** 服务器读取设计，并实现到你的项目中。
- **项目管理：** 带封面、重命名和回收站的主页。

![画布上的五个画框：同一落地页的浅色和深色版本，以及助手、隐私和个人资料视图](docs/assets/screenshots/canvas-dark.webp)

## 安装

从 [Releases](https://github.com/Willi005/weft-studio-releases/releases) 下载最新版本。

| 系统 | 文件 | 方法 |
| --- | --- | --- |
| Linux x86_64 | `Weft-Studio-<版本>-x86_64.AppImage` | `chmod +x` 后打开；首次运行会加入应用菜单 |
| Debian / Ubuntu | `weft-studio_<版本>_amd64.deb` | `sudo apt install ./weft-studio_<版本>_amd64.deb`（同时安装 git） |
| Windows 11 x64 | `Weft-Studio-<版本>-x64-Setup.exe` | 运行即可；按用户安装，无需管理员权限 |

**系统要求：**
- **git**（Windows 上为 [Git for Windows](https://git-scm.com/download/win)）。
- 至少一个已登录账号的智能体。欢迎页和 **Settings → Providers** 会检测已安装的智能体，提供用官方安装程序安装缺失的智能体（执行前会显示命令），并帮你登录。其他厂商的模型可通过 OpenCode 使用。
- 不需要 Node.js，除非要在 Windows 上安装 OpenCode（通过 npm）。

**Windows 安装程序暂未签名**，因此 Windows 可能提示“未知发布者”。要校验下载文件，请将其校验和与对应 release 中 `SHA256SUMS.txt` 的值比较：
- Linux：`sha256sum <文件>`
- Windows（PowerShell）：`Get-FileHash <文件>`

## 更新

应用在启动时和每六小时会到本仓库检查新版本，并告诉你有哪些新内容。只有在你要求时才会下载和安装：**Update** 下载，**Restart to update** 安装并重启应用，**Settings → Updates** 立即检查。AppImage、`.deb` 和 Windows 安装版都能在应用内更新。

## 状态

Weft Studio 目前处于 **beta** 阶段（`0.2.0-beta.N`），每个版本都以 prerelease 形式发布。每个版本的更新内容见其 [release 说明](https://github.com/Willi005/weft-studio-releases/releases)。

如果你喜欢这个项目，点一个 ⭐ 能帮助更多人发现它。
