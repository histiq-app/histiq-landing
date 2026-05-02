# Histiq — AI Search for Your Browser History

> Find any page you've ever read — by meaning, not keywords.

[![Website](https://img.shields.io/badge/website-histiq.com-7c5af0)](https://histiq.com)
[![License: MIT](https://img.shields.io/badge/license-MIT-7c5af0.svg)](LICENSE)
[![Privacy](https://img.shields.io/badge/privacy-100%25%20local-22c55e)](https://histiq.com/privacy)

**Histiq** is a privacy-first browser extension that indexes everything you read in Chrome, Firefox, and Edge, then lets you search by meaning and chat with your history using local AI.

🔒 **100% local. No cloud. No tracking.**

---

## The Problem

You read thousands of pages every year — articles, docs, research, blog posts. A week later you remember the topic, but not the title or URL. Native browser history only searches by title and URL, so you spend 20 minutes scrolling through history hoping to recognize a link.

## The Solution

Histiq quietly indexes the actual content of pages you visit, on your own device. Then you can:

- **Search semantically** — "the article about startup fundraising I read last month" finds it.
- **Chat with your history** — ask questions across everything you've read, get answers with citations linking back to the original pages.
- **Stay private** — nothing is sent to any server. Your reading habits remain yours.

---

## Features

- 🧠 **Semantic search** — find pages by what they're about, not just words in the title.
- 💬 **AI chat with your history** — ask questions across everything you've ever read, get cited answers.
- 🔒 **Fully local & private** — your history never leaves your computer. AI runs locally via Gemini Nano or WebLLM.
- ⚡ **Automatic indexing** — silently indexes every page you visit in the background. No manual work.
- 🌐 **Chrome, Firefox & Edge** — works across all major browsers.
- 🗝️ **Your API key, your choice** — prefer GPT-4 or Claude? Plug in your own API key. Histiq never proxies the request.

---

## How It Works

1. **Install the extension** from the Chrome Web Store, Firefox Add-ons (AMO), or Edge Add-ons.
2. **Browse normally** — Histiq runs silently in the background, indexing every page locally on your device.
3. **Search and ask** — hit `Ctrl+Shift+H` anytime to open semantic search or AI chat.

All embeddings, storage, and AI inference happen in your browser. No account. No login. No telemetry.

---

## Pricing

| Plan | Price | What's included |
|------|-------|-----------------|
| **Free trial** | $0 — 14 days | Full access. No credit card required. |
| **Monthly** | $6.99 / month | Cancel anytime. |
| **Annual** | $4.17 / month | Billed $49.99/year — save 40%. Most popular. |

After the trial, your indexed history is **frozen, not deleted** — pay anytime to unfreeze instantly. Data is preserved locally for 30 days.

---

## Tech Stack

- **Embeddings:** Xenova `all-MiniLM-L6-v2` (384-dim, runs in-browser via Transformers.js)
- **Vector storage:** IndexedDB via Dexie
- **Local AI providers:** Chrome Prompt API (Gemini Nano), WebLLM (Llama / Qwen quantized models)
- **Cloud AI (optional):** OpenAI / Anthropic / Google — bring your own key
- **Frontend:** TypeScript, React, Vite
- **Browser support:** Manifest V3 (Chrome, Edge), Manifest V3 with event pages (Firefox)

---

## Privacy

- All embeddings and AI inference run **on your device**.
- Browsing history is stored exclusively in your browser's IndexedDB.
- **No account, no login, no email required.**
- License validation is the only outbound request — sent directly to the payment processor's API.
- Open to audit — extension code is inspectable in the browser DevTools.

Read the full [Privacy Policy](https://histiq.com/privacy).

---

## Repository Contents

This repository contains the marketing website (`histiq.com`) source code:

```
.
├── index.html          # Landing page
├── style.css           # Styles (dark theme, design tokens)
├── script.js           # FAQ accordion, scroll effects, smooth scroll
├── header.html         # Reusable header
├── footer.html         # Reusable footer
├── terms.html          # Terms of Service
├── privacy.html        # Privacy Policy
├── refund.html         # Refund Policy
└── histiq-child/       # WordPress / Astra child theme
    ├── style.css
    ├── functions.php
    ├── header.php
    ├── index.php
    └── histiq/
        ├── head.php
        ├── footer.php
        └── footer.css
```

The browser extension itself is maintained in a separate (private) repository.

---

## Roadmap

- [x] Local semantic search across browsing history
- [x] AI chat with history (Gemini Nano / WebLLM / Cloud API cascade)
- [x] Cross-browser support (Chrome, Firefox, Edge)
- [x] Subscription via third-party Merchant of Record
- [ ] Public launch on Chrome Web Store, Firefox Add-ons, Edge Add-ons
- [ ] ProductHunt launch
- [ ] Optional E2E-encrypted multi-device sync (v1.1)

---

## Contact

- **Website:** [histiq.com](https://histiq.com)
- **Support:** [support@histiq.com](mailto:support@histiq.com)

## Company

**Infivion LLC** — Wyoming, United States

## License

MIT — see [LICENSE](LICENSE).
