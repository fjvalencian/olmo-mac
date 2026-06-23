# Contributing to Olmo

Thanks for your interest in Olmo — an open-source, privacy-first AI meeting
notetaker for macOS. Contributions of all sizes are welcome: bug reports, fixes,
features, docs, and translations.

## Ground rules

- Be kind and constructive. Assume good intent.
- Olmo is **local-first / BYOK** (Bring Your Own Keys). Please don't add features
  that send user audio or notes to servers other than the ones the user
  explicitly configures (Deepgram / OpenAI / Notion via their own tokens).
- Never commit secrets, API keys, certificates, or provisioning profiles.

## Getting set up

Requirements: macOS 14+, Xcode 15+, and [XcodeGen](https://github.com/yonaskolb/XcodeGen)
(`brew install xcodegen`).

```bash
git clone https://github.com/fjvalencian/olmo-mac.git
cd olmo-mac/Olmo-MacOS
xcodegen generate          # regenerate the .xcodeproj from project.yml
open Olmo-MacOS.xcodeproj   # then ⌘R in Xcode
```

> Run `xcodegen generate` whenever you add or remove a Swift file — sources are
> resolved from folder paths in `project.yml`.

## Making a change

1. **Fork** the repo and create a branch from `main`:
   `git checkout -b fix/short-description` (or `feat/…`, `docs/…`).
2. Keep changes focused — one logical change per pull request.
3. **Match the existing style** (naming, structure, comment density). Don't
   reformat unrelated code.
4. Build and run the app to confirm your change works. If you touched testable
   logic, add or update a test under `Olmo-MacOSTests/`.
5. Commit with a clear message (e.g. `fix(record): …`, `feat(notes): …`).

## Opening a pull request

- Push your branch to your fork and open a PR against `main`.
- Describe **what** changed and **why**, and how you tested it. Screenshots help
  for UI changes.
- A maintainer will review. Please be patient — this is a small project.

## Reporting bugs / requesting features

Open an [issue](https://github.com/fjvalencian/olmo-mac/issues) with steps to
reproduce (for bugs) or the problem you're trying to solve (for features).

By contributing, you agree that your contributions will be licensed under the
project's [MIT License](LICENSE).
