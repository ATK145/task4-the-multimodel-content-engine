# 🎬 ATK — AI Viral Content Engine

> **by Aisha Tariq Khan**  
> Turn any video into 5 viral short-form Reels — powered by Claude AI, runs entirely in your browser.

[![Deploy to GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-blue?logo=github)](https://pages.github.com)
[![Claude AI](https://img.shields.io/badge/Powered%20by-Claude%20Sonnet-orange)](https://anthropic.com)
[![Author](https://img.shields.io/badge/Author-Aisha%20Tariq%20Khan-e63f6b)](https://github.com/YOUR_USERNAME)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 🚀 Live Demo

**[→ Open ATK AI](https://YOUR_USERNAME.github.io/atk)**

---

## ✨ What It Does

ATK is a **fully browser-based** AI pipeline that:

1. 🎙️ **Transcribes** your video/audio using Claude AI
2. 🧠 **Scores** every segment for viral potential (hook, emotion, shareability, novelty)
3. ✍️ **Generates** captions, hooks, headlines & CTAs per platform
4. 🎬 **Creates** Runway Gen-3 B-roll prompts ready for AI video generation
5. 📦 **Exports** everything as JSON or copy-pastes to clipboard

No backend. No server. No data leaves your browser (except the Anthropic API call).

---

## 🔌 Requirements

- An **Anthropic API key** — [get one here](https://console.anthropic.com)
- A modern browser (Chrome, Firefox, Safari, Edge)
- Your video or audio file (MP4, MOV, AVI, MKV, MP3, WAV, M4A, WEBM)

---

## 🚢 Deploy to GitHub Pages (2 minutes)

### Option A — Direct Upload

1. Fork or clone this repo
2. Go to **Settings → Pages**
3. Set Source to `main` branch, folder `/` (root)
4. Visit `https://YOUR_USERNAME.github.io/atk`

### Option B — Auto-deploy via GitHub Actions

The included `.github/workflows/deploy.yml` auto-deploys on every push to `main`.

---

## 📁 Project Structure

```
atk/
├── index.html                   ← Entire web app (single file, no build step)
├── README.md
├── .github/
│   └── workflows/
│       └── deploy.yml           ← GitHub Actions auto-deploy
└── src/                         ← Optional Python CLI pipeline
    ├── pipeline.py
    ├── transcriber.py
    ├── viral_detector.py
    ├── caption_generator.py
    ├── broll_generator.py
    └── exporter.py
```

---

## 🔒 Privacy & Security

- Your API key is **never stored** (session only, cleared on refresh)
- Video files are **processed in-browser** — never uploaded to any server
- Only the transcript text is sent to Anthropic's API for analysis
- All results stay in your browser

---

## 🧠 How the AI Pipeline Works

```
VIDEO/AUDIO FILE (browser)
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — Transcribe     │  → Timestamped segments
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — Viral Scoring  │  → 0-100 score per segment
│  5 criteria × 20 pts each   │
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — Captions       │  → Headline, hook, caption,
│                             │     CTA, hashtags, A/B test
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — B-Roll         │  → Runway Gen-3 prompts
└─────────────────────────────┘
        │
        ▼
    📋 Copy / ⬇ Download JSON
```

---

## 📄 License

MIT © 2025 **Aisha Tariq Khan**
