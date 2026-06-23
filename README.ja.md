<p align="center">
  <img src="assets/olmo-icon.png" width="120" alt="Olmo" />
</p>

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


## API キー（BYOK）

Olmo は **bring-your-own-keys** です。Deepgram と OpenAI のアカウントを自分で
接続するので、音声もノートも *あなたが* 管理するサービスへ直接送られます。
私たちのサーバーを経由しません。

### なぜ Deepgram なのか

Olmo は **話しながらリアルタイムで**文字起こしするため、速くて正確な
ストリーミング音声認識が必要です。Deepgram はまさにそのために作られています。
低遅延のストリーミング、高い精度と多言語対応、そしてサブスク不要の
シンプルな**従量課金**。新規アカウントにはクレジットカード不要で
**$200 分の無料クレジット**が付与されます — 支払いが始まるまでに多くの会議を
こなせます。

> $200 は**登録時の一度きりのクレジット**で（登録から1年で失効）、毎月もらえる
> 枠ではありません。使い切った後は、文字起こしした分だけ従量課金で支払います。

**キーの取得:**

1. [console.deepgram.com/signup](https://console.deepgram.com/signup) で登録 — 無料、カード不要。
2. コンソールで **API Keys → Create a New API Key** からキーを作成しコピー。
3. Olmo の **設定 → API キー** を開き、Deepgram の欄に貼り付けます。

**OpenAI のキー**も同じ手順で設定します（要約の生成に使われます）。

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
