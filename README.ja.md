<p align="center"><a href="README.md">English</a> · <a href="README.es.md">Español</a> · <b>日本語</b> · <a href="README.zh.md">中文</a></p>

# Olmo

**プライバシー重視・オープンソースの、macOS 向け AI 会議ノートアプリ。**

Olmo は会議や通話を録音し、リアルタイムで文字起こしして、編集できるきれいな
Markdown の要約に変換します。すべてあなたの Mac 上で、あなた自身の API キーを
使って動作します。通話にボットは参加せず、ノートはあなたの手元に残ります。

## 主な機能

- **通話の両方の声。** マイクと相手の声（システム音声）を、ヘッドホンの有無に
  かかわらず収録します。
- **ボットなし。** 会議には何も参加しません。録音はあなたの Mac の中で行われます。
- **リアルタイム文字起こし**と **AI 要約**を、編集・検索・保存できる Markdown
  として生成します。
- **自分のキーを使う（BYOK）。** Deepgram と OpenAI のキーは自分のものを使用。
  音声もノートも当社のサーバーを経由しません。
- **Notion 連携。** 各要約は自動で Notion のページに書き出されます — 1 会議＝
  1 ページ、重複なし。
- **Google カレンダー。** カレンダーから会議を確認し、そのままノートを取り始め
  られます。

## インストール

- [Releases](https://github.com/fjvalencian/olmo-mac/releases) から最新の
  `Olmo.dmg` を**ダウンロード**してください。**macOS 14 以降**が必要です。
- **ウェブサイト:** <https://fjvalencian.github.io/olmo-mac/>

### ソースからビルド

必要なもの: macOS 14+、Xcode 15+、
[XcodeGen](https://github.com/yonaskolb/XcodeGen)（`brew install xcodegen`）。

```bash
git clone https://github.com/fjvalencian/olmo-mac.git
cd olmo-mac/Olmo-MacOS
xcodegen generate
open Olmo-MacOS.xcodeproj   # その後 ⌘R
```

## 技術スタック

SwiftUI (macOS 14+) · AVFoundation + ScreenCaptureKit（マイク＋システム音声）·
Deepgram（音声認識）· OpenAI（要約）· Core Data（ローカル保存）·
Google Calendar・Notion API。

## コントリビュート

コントリビューションを歓迎します — [CONTRIBUTING.md](CONTRIBUTING.md) を
ご覧ください。バグやアイデアがあれば
[issue](https://github.com/fjvalencian/olmo-mac/issues) を開いてください。

## ライセンス

[MIT](LICENSE)。
