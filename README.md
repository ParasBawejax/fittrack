<div align="center">
  <img src="icons/icon-192.png" width="96" height="96" alt="FitTrack Logo" />
  <h1>FitTrack</h1>
  <p>Personal fitness tracker · Calorie logging · Workout logging · Progress charts</p>
  <p>
    <img src="https://img.shields.io/badge/PWA-Ready-6c63ff?style=flat-square&logo=pwa" />
    <img src="https://img.shields.io/badge/Works_Offline-Yes-22d07a?style=flat-square" />
    <img src="https://img.shields.io/badge/No_Build_Step-Static-ff8c42?style=flat-square" />
    <img src="https://img.shields.io/badge/AI_Powered-Anthropic-6c63ff?style=flat-square" />
  </p>
  <br />
  <a href="https://parasbawejax.github.io/fittrack/"><strong>→ Open App</strong></a>
</div>

---

## Overview

FitTrack is a lightweight Progressive Web App for tracking fitness goals. It runs entirely in the browser — no backend, no account, no subscription. Your data stays on your device.

Built for a specific goal: losing weight on a vegetarian Indian diet while building healthy habits before college. Calorie targets, macro splits, and goal weight are pre-configured accordingly, and the food search understands Indian meals natively.

---

## Features

| Feature | Details |
|---|---|
| **Calorie Tracker** | Daily log with calorie + macro breakdown (protein, carbs, fat) |
| **AI Food Search** | Search any food including Indian meals — powered by Claude AI |
| **Workout Logger** | Log exercises with sets, reps, and optional weight |
| **Weight Tracking** | Daily weight log with trend chart and journey progress bar |
| **Offline Support** | Full PWA — add to home screen, works without internet* |
| **Local Storage** | All data saved on-device, nothing sent to any server |

*Food search requires internet. Everything else works offline.

---

## Stack

- **React 18** — via [esm.sh](https://esm.sh) CDN, no build step
- **Anthropic Claude API** — for AI-powered food nutrition lookup
- **Vanilla CSS** — no framework, pure inline styles
- **Service Worker** — for offline caching and PWA support
- **localStorage** — for persistent on-device data storage

---

## Setup

### Deploy to GitHub Pages

**1. Fork or clone this repository**

```bash
git clone https://github.com/ParasBawejax/fittrack.git
cd fittrack
```

**2. Enable GitHub Pages**

Go to your repo → **Settings → Pages → Source → Deploy from branch → main → / (root)**

**3. That's it.** No `npm install`, no build step. GitHub Pages serves the static files directly.

Your app will be live at:
```
https://<your-username>.github.io/fittrack/
```

---

### Run Locally

Since there's no build step, you just need a simple HTTP server:

```bash
# Python (built-in)
python3 -m http.server 8000

# Then open: http://localhost:8000
```

Or use the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension in VS Code.

---

### Add to Home Screen (Mobile)

**iPhone — Safari:**
1. Open the app URL in Safari
2. Tap the **Share** button ↑
3. Tap **Add to Home Screen**
4. Tap **Add**

**Android — Chrome:**
1. Open the app URL in Chrome
2. Tap the **⋮** menu
3. Tap **Add to Home screen**
4. Tap **Add**

Once added, the app launches full-screen like a native app and works offline.

---

## Configuration

Personal targets are set at the top of `index.html` inside the `<script>` block:

```js
const GOALS = { calories: 1950, protein: 110, carbs: 220, fat: 60 };
const TARGET = 78; // goal weight in kg
```

Adjust these to your own numbers.

---

## Project Structure

```
fittrack/
├── index.html       # Entire app — HTML + React + styles in one file
├── sw.js            # Service worker for offline caching
├── manifest.json    # PWA manifest (name, icons, theme)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── README.md
```

---

## Privacy

- No account required
- No data sent to any server (except food search queries to the Anthropic API)
- All logs stored in your browser's `localStorage`
- Clearing site data will erase your history

---

## License

MIT — use it however you want.
