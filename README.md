# Histiq

Browser extension that automatically indexes every page you visit and lets you search your entire reading history by meaning — not just keywords.

Works in Chrome, Edge, and Firefox.

## Features

- 🔍 **Semantic Search** — find pages by meaning, context, and topic, not exact words
- 📄 **PDF Indexing** — text-layer PDFs are indexed automatically
- ⚡ **Sub-50ms Search** — local embeddings, no API calls, no cloud
- 🔒 **Privacy First** — everything stays on your device; banks, logins, and private pages are filtered out
- 🌐 **Chrome, Edge & Firefox** — separate builds for Chromium and Firefox MV3
- 📦 **Vault Export / Import** — encrypted backup of your entire index
- 🎯 **Custom Filters** — include/exclude domains and URL patterns

## Trial & Pricing

14-day free trial, no credit card required. After the trial, a paywall is shown inside the popup. Three plans available via Polar:

| Plan | Price |
|------|-------|
| Monthly | $6.99 / mo |
| Annual | $4.17 / mo (billed $49.99/yr) |
| Lifetime | $129 once |

## Project Structure

```
src/                        # TypeScript + React source
dist/                       # Chrome / Edge build (MV3, offscreen document)
dist-firefox/               # Firefox build (MV3, background module)
landing/                    # Marketing site (histiq.com)
```

## Builds

### Chrome & Edge (`dist/`)

- Manifest V3, classic service worker (no `"type": "module"`)
- PDF extraction runs in an **offscreen document** (`dist/offscreen/`)
- pdf.js polyfills injected via classic `<script>` before the ES module + blob URL into the worker
- Trial UI injected via standalone `dist/ui/popup/trial-ui.js`

### Firefox (`dist-firefox/`)

- Manifest V3 with `"background": { "scripts": [...], "type": "module" }`
- No offscreen API — pdf.js runs directly in the background page
- Worker loaded via `chrome.runtime.getURL(...)` (blob workers blocked by Firefox CSP)
- Inline polyfills in `dist-firefox/background/background.js`

## Tech Stack

| Layer | Technology |
|-------|-----------|
| UI | React 18 + TypeScript |
| Build | Vite 5 |
| Storage | Dexie.js (IndexedDB) |
| Embeddings | Xenova/all-MiniLM-L6-v2 (384-dim, local) |
| PDF | pdf.js v5 |
| Payments | Polar.sh |

## Development

```bash
npm install
npm run build          # builds dist/ (Chrome/Edge)
npm run build:firefox  # builds dist-firefox/
```

Load unpacked in Chrome: `chrome://extensions/` → Developer mode → Load unpacked → select `dist/`

Load in Firefox: `about:debugging` → This Firefox → Load Temporary Add-on → select `dist-firefox/manifest.json`

## License

MIT
