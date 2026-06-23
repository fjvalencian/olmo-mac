# Olmo website

Single-file landing page (`index.html`) for Olmo. No build step.

## Local preview
Open `index.html` in a browser, or run `python3 -m http.server` in this folder
and visit http://localhost:8000.

## Before launch — required edits in `index.html`
- `GITHUB_REPO` → your real `owner/repo` slug. This one constant powers the
  Download URL, every GitHub link (footer GitHub / License / Issues / Contribute,
  and the nav "Star" button), **and** the live star count (which stays hidden
  until the slug is real). The release asset must be named `Olmo.dmg`.
- `COFFEE_URL` → your real Buy-me-a-coffee link.
- Add a `LICENSE` (MIT) and a `CONTRIBUTING.md` at the repo root — the footer
  "MIT License" and "Contribute" links point at `/blob/main/LICENSE` and
  `/blob/main/CONTRIBUTING.md`.
- Replace the placeholder screenshot boxes (`.shot__ph`) with real **light-mode**
  captures in `assets/` (`screenshot-1.png`, `screenshot-2.png`), then swap the
  `.shot__ph` divs for `<img>` tags.
- Replace `assets/og.png` (currently a square stand-in of the icon) with a proper
  1200×630 social card.
- Set `og:image` (and ideally the favicon `href`) to an **absolute** `https://…`
  URL once the domain/Pages URL is known — OG scrapers (Slack, iMessage, X) ignore
  relative paths, so the social card won't render otherwise.
- Downscale `assets/favicon.png` to a small, simplified mark (it's currently the
  full ~884 KB app icon).
- Have a native speaker review the **JA** and **ZH** strings in the `I18N` object.

## Deploy
Pushes to `main` that touch `website/**` deploy via `.github/workflows/pages.yml`.
In the repo: **Settings → Pages → Source = "GitHub Actions"** (one-time setup).
