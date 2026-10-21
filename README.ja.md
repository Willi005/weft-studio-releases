<p align="center">
  <img src="assets/weft-studio.svg" width="112" alt="Weft Studio の小さなエージェント" />
</p>

<h1 align="center">Weft Studio</h1>

<p align="center"><b>AI エージェントと一緒に、ライブ編集できるキャンバスで UI をデザイン。</b><br />
Claude Code、Codex、OpenCode、Antigravity に対応した Linux / Windows 向けデスクトップアプリです。</p>

<p align="center">
  <a href="README.md">English</a> ·
  <a href="README.es.md">Español</a> ·
  <a href="README.pt-BR.md">Português</a> ·
  <a href="README.fr.md">Français</a> ·
  <a href="README.de.md">Deutsch</a> ·
  <a href="README.zh-CN.md">简体中文</a> ·
  <b>日本語</b>
</p>

<p align="center">
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="バージョン" src="https://img.shields.io/github/v/release/Willi005/weft-studio-releases?include_prereleases&label=version&color=6E56CF" /></a>
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><img alt="ダウンロード数" src="https://img.shields.io/github/downloads/Willi005/weft-studio-releases/total?label=downloads&color=22C55E" /></a>
  <img alt="Linux x86_64" src="https://img.shields.io/badge/Linux-x86__64-FCC624?logo=linux&logoColor=black" />
  <img alt="Windows 11 x64" src="https://img.shields.io/badge/Windows%2011-x64-0078D6" />
  <img alt="ステータス：ベータ" src="https://img.shields.io/badge/status-beta-F59E0B" />
</p>

<p align="center">
  <a href="https://willi005.github.io/weft-studio-releases/"><b>ウェブサイト</b></a> ·
  <a href="https://github.com/Willi005/weft-studio-releases/releases"><b>ダウンロード</b></a>
</p>

![Weft Studio のエディター：キャンバス上のランディングページで見出しが選択され、右にスタイルインスペクター、左のチャットにエージェントへの依頼が表示されている](docs/assets/screenshots/editor-dark.webp)

**Weft Studio**（旧 CodeWeaves Studio）は、あなたと AI コーディングエージェントが同じキャンバスで作業するデザインツールです。画面の内容を伝えると、エージェントがそれを描いていく様子が見られ、そのあと手で移動したり、スタイルを変えたり、書き直したりできます。各デザインは読みやすい HTML ファイル（`design.ws.html`）として保存されるフレームで、それぞれ専用のエージェント（**Claude Code、Codex、OpenCode、Antigravity**）を持ちます。あなたの変更もエージェントの書き込みも、すぐに反映されます。

このリポジトリはインストーラーのみを公開しており、ソースコードは含まれていません。

## できること

- **エージェントとデザイン：** 作りたいものを伝え、1〜3 つの方向性を並行して試せます。それぞれにエージェント、モデル、思考レベルを設定できます。エージェントは作業前に質問したり、指定した他のフレームを読んだり、添付した画像を使ったりできます。
- **ライブで手動編集：** 選択、移動、リサイズ。インスペクター（Simple、Pro、Code、Tweaks）でテキストとスタイルを変更。レイヤー、描画ツール、元に戻す／やり直し。変更は自動保存され、デザインごとにバージョン履歴があります。
- **複数画面のアプリ：** デザインにビュー（ホーム、料金、お問い合わせ…）を定義すると、同じドキュメントのビューごとにフレームがキャンバスに表示されます。
- **自分のファイル：** **Assets** パネルから画像、GIF、動画をデザインにアップロードできます。エージェントはそれらを把握して使います。
- **コメントとプレゼン：** 要素に固定されるコメントと、フルスクリーンでインタラクティブに動く **Present** モード。
- **エクスポートとインポート：** どのブラウザでも開ける、ランタイム付きの読みやすい HTML。デザイン・ランタイム・アセットをまとめた ZIP。PNG と JPEG。**Import** でこれらのファイルや Claude Design の `.dc.html` を開けます。
- **デザインをコードへ：** 「Send to a coding agent…」でプロンプトをコピーすると、Claude Code、Codex、Gemini CLI、OpenCode が読み取り専用の **MCP** サーバー経由でデザインを読み、あなたのプロジェクトに実装します。
- **プロジェクト管理：** カバー画像、名前の変更、ゴミ箱を備えたホーム画面。

![キャンバスに並んだ 3 つのデザイン：旅行のランディングページ、コーヒー注文アプリ、分析ダッシュボード](docs/assets/screenshots/canvas-dark.webp)

## インストール

最新版は [Releases](https://github.com/Willi005/weft-studio-releases/releases) からダウンロードできます。

| システム | ファイル | 方法 |
| --- | --- | --- |
| Linux x86_64 | `Weft-Studio-<バージョン>-x86_64.AppImage` | `chmod +x` して起動。初回起動時にアプリメニューに追加されます |
| Debian / Ubuntu | `weft-studio_<バージョン>_amd64.deb` | `sudo apt install ./weft-studio_<バージョン>_amd64.deb`（git も入ります） |
| Windows 11 x64 | `Weft-Studio-<バージョン>-x64-Setup.exe` | 実行するだけ。ユーザー単位でインストールされ、管理者権限は不要です |

**必要なもの：**
- **git**（Windows では [Git for Windows](https://git-scm.com/download/win)）。
- アカウント付きのエージェントが少なくとも 1 つ。ようこそ画面と **Settings → Providers** がインストール済みのエージェントを検出し、足りないものを公式インストーラーで入れること（実行前にコマンドを表示）とサインインを提案します。他社のモデルは OpenCode 経由で使えます。
- Node.js は不要です（Windows で OpenCode を npm でインストールする場合を除く）。

**Windows インストーラーはまだコード署名されていない**ため、「不明な発行元」と警告されることがあります。ダウンロードを確認するには、各 release の `SHA256SUMS.txt` とチェックサムを比較してください：
- Linux：`sha256sum <ファイル>`
- Windows（PowerShell）：`Get-FileHash <ファイル>`

## アップデート

アプリは起動時と 6 時間ごとにこのリポジトリで新しいバージョンを確認し、新機能を知らせます。ダウンロードとインストールはあなたが指示したときだけです：**Update** でダウンロード、**Restart to update** でインストールして再起動、**Settings → Updates** ですぐに確認。AppImage、`.deb`、Windows インストーラー版はすべてアプリ内から更新できます。

## ステータス

Weft Studio は **ベータ版**（`0.2.0-beta.N`）で、各バージョンは prerelease として公開されます。各バージョンの変更点は [リリースノート](https://github.com/Willi005/weft-studio-releases/releases) をご覧ください。

気に入ったら ⭐ をお願いします。他の人が見つけやすくなります。
