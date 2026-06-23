<p align="center">
  <img src="assets/olmo-icon.png" width="120" alt="Olmo" />
</p>

<p align="center"><b>English</b> · <a href="README.es.md">Español</a> · <a href="README.ja.md">日本語</a> · <a href="README.zh.md">中文</a></p>

# Olmo

**An open-source, privacy-first AI meeting notetaker for macOS.**

Olmo records your meetings and calls, transcribes them in real time, and turns
them into clean, editable Markdown summaries — running on your own Mac with your
own API keys. No bot joins your call, and your notes stay with you.

## Features

- **Both sides of the call.** Captures your microphone *and* the other person's
  voice (system audio), with or without headphones.
- **No bot.** Nothing joins your meeting — recording happens locally on your Mac.
- **Live transcription** and **AI summaries**, rendered as clean Markdown you can
  edit, search, and keep.
- **Bring your own keys (BYOK).** Use your own Deepgram and OpenAI keys; your
  audio and notes never pass through our servers.
- **Notion sync.** Every summary auto-exports to a Notion page — one meeting, one
  page, never duplicated.
- **Google Calendar.** See your meetings and start notes straight from your
  calendar.

## Install

- **Download** the latest `Olmo.dmg` from the
  [Releases](https://github.com/fjvalencian/olmo-mac/releases) page.
  Requires **macOS 14 or later**.
- **Website:** <https://fjvalencian.github.io/olmo-mac/>

### Build from source

Requirements: macOS 14+, Xcode 15+, and
[XcodeGen](https://github.com/yonaskolb/XcodeGen) (`brew install xcodegen`).

```bash
git clone https://github.com/fjvalencian/olmo-mac.git
cd olmo-mac/Olmo-MacOS
xcodegen generate
open Olmo-MacOS.xcodeproj   # then ⌘R
```


## API keys (BYOK)

Olmo is **bring-your-own-keys**: you connect your own Deepgram and OpenAI
accounts, so your audio and notes go straight to the services *you* control —
never through a server of ours.

### Why Deepgram?

Olmo transcribes **live, while you talk**, so it needs fast, accurate, real-time
speech-to-text. Deepgram is built exactly for that: low-latency streaming, strong
accuracy and multilingual support, and a simple **pay-as-you-go** model with no
subscription. New accounts get **$200 in free credits** with no credit card — a
lot of meetings before you pay anything.

> The $200 is a **one-time sign-up credit** (it expires one year after signup),
> not a monthly allowance. After it runs out you only pay for what you
> transcribe, at pay-as-you-go rates.

**Get your key:**

1. Sign up at [console.deepgram.com/signup](https://console.deepgram.com/signup) — free, no credit card.
2. In the Console, go to **API Keys → Create a New API Key** and copy it.
3. In Olmo, open **Settings → API keys** and paste it in the Deepgram field.

You set your **OpenAI key** the same way (it powers the AI summaries).

## Tech

SwiftUI (macOS 14+) · AVFoundation + ScreenCaptureKit (mic + system audio) ·
Deepgram (speech-to-text) · OpenAI (summaries) · Core Data (local storage) ·
Google Calendar & Notion APIs.

## Contributing

Contributions are welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). Found a bug or
have an idea? Open an [issue](https://github.com/fjvalencian/olmo-mac/issues).

## License

[MIT](LICENSE).
