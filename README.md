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

## Tech

SwiftUI (macOS 14+) · AVFoundation + ScreenCaptureKit (mic + system audio) ·
Deepgram (speech-to-text) · OpenAI (summaries) · Core Data (local storage) ·
Google Calendar & Notion APIs.

## Contributing

Contributions are welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). Found a bug or
have an idea? Open an [issue](https://github.com/fjvalencian/olmo-mac/issues).

## License

[MIT](LICENSE).
