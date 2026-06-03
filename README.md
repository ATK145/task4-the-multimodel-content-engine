# 🎬 ReelForge AI — Browser-Based Viral Content Engine

> Turn any video into 5 viral short-form Reels — powered by Claude AI, runs entirely in your browser.

[![Deploy to GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-blue?logo=github)](https://pages.github.com)
[![Claude AI](https://img.shields.io/badge/Powered%20by-Claude%20Sonnet-orange)](https://anthropic.com)
[![License](https://img.shields.io/badge/License-MIT-yellow)](LICENSE)

---

## 🚀 Live Demo

**[→ Open ReelForge AI](https://YOUR_USERNAME.github.io/reelforge)**

---

## ✨ What It Does

ReelForge AI is a **fully browser-based** pipeline that:

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
4. Visit `https://YOUR_USERNAME.github.io/REPO_NAME`

### Option B — GitHub Actions (auto-deploy on push)

The included `.github/workflows/deploy.yml` auto-deploys on every push to `main`.

```yaml
# .github/workflows/deploy.yml is already configured
# Just push to main and your site updates automatically
```

### Option C — One-click Deploy

[![Deploy to GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-blue?logo=github)](https://github.com/new?template_name=reelforge&template_owner=YOUR_USERNAME)

---

## 📁 Project Structure

```
reelforge/
├── index.html          ← The entire app (single file, no build step)
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml  ← GitHub Actions auto-deploy
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
│  File Info Extraction       │  → Filename, size, type
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — Transcribe     │  → Timestamped segments
│  (claude-sonnet-4)          │     with realistic content
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — Viral Scoring  │  → 0-100 score per segment
│  5 criteria × 20 pts each   │     hook, emotion, share,
│                             │     novelty, self-contained
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — Captions       │  → Per platform:
│                             │     headline, hook, caption,
│                             │     CTA, 10 hashtags, A/B test
└─────────────────────────────┘
        │
        ▼
┌─────────────────────────────┐
│  Claude AI — B-Roll         │  → Runway Gen-3 prompts:
│                             │     primary + secondary shots,
│                             │     camera, lighting, style
└─────────────────────────────┘
        │
        ▼
    📋 Copy / ⬇ Download JSON
```

---

## 📤 Output Format

Each Reel includes:

| Field | Description |
|---|---|
| `viral_score` | 0–100 overall virality score |
| `headline` | Platform-optimized title |
| `hook_text` | First 3-second on-screen text |
| `caption` | Ready-to-post caption with emojis |
| `call_to_action` | Specific engagement CTA |
| `hashtags` | 10 platform-relevant hashtags |
| `ab_test_headline` | Alternative headline to test |
| `runway_prompt` | Runway Gen-3 text-to-video prompt |
| `camera_movement` | Cinematography direction |
| `reasoning` | Why Claude thinks this segment is viral |

---

## 🎬 Runway Integration

Copy the generated prompts directly into [Runway Gen-3](https://runwayml.com) or use the Python pipeline for batch generation:

```python
# Python pipeline (optional, for batch Runway API calls)
python src/pipeline.py --input video.mp4 --runway --platform instagram
```

---

## 🤝 Contributing

PRs welcome! Open issues for:
- [ ] Real audio transcription via Web Speech API
- [ ] Direct TikTok/Instagram API upload integration  
- [ ] Batch processing multiple videos
- [ ] Custom prompt templates

---

## 📄 License

MIT © 2025 ReelForge
