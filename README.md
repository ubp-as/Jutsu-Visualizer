# Jutsu-Visualizer

A real-time hand gesture recognition web app built with React and MediaPipe Hands. Point your webcam and use hand gestures to cast jutsu visual effects overlaid on your live camera feed. Both hands are tracked simultaneously — combine gestures to activate multiple jutsu at once.

**🔴 Live Demo → [naruto-jutsu-eosin.vercel.app](https://naruto-jutsu-eosin.vercel.app)**

---

## Gestures

| Gesture | Hand | Effect |
|---|---|---|
| Open palm | Left hand | Rasengan |
| Open palm | Right hand | Chidori |
| Fist with thumb up | Either hand | Fireball Jutsu |
| Pinch (thumb + index tip) | Either hand | Hollow Purple |

> **Tip:** Use both hands at the same time to cast multiple jutsu simultaneously — try Rasengan + Chidori at once!

---

## How It Works

- Uses **MediaPipe Hands** to track 21 hand landmarks per hand in real time
- Detects hand poses by comparing distances between landmark points
- Renders effects using the **Canvas 2D API** — Hollow Purple is a fully custom particle system with radial gradients and swirling ring animations at 60fps
- Video effects (Rasengan, Chidori, Fireball) are overlaid using `mix-blend-mode: screen` for transparent compositing
- Supports **dual-hand tracking** simultaneously — multiple jutsu can be active at the same time
- Tutorial screen teaches each gesture before launching the camera

---

## Tech Stack

- React 19
- MediaPipe Hands
- Vite
- Canvas 2D API

---

## Getting Started

### Prerequisites

- Node.js (v18+)
- A webcam

### Installation

```bash
git clone https://github.com/ubp-as/Jutsu-Visualizer.git
cd Jutsu-Visualizer
npm install
```

### Video Assets

The jutsu effect videos are included in `public/assets/`. No additional setup needed.

```
public/
└── assets/
    ├── naruto.mp4
    ├── chidori.mp4
    └── fireball.mp4
```

### Running Locally

```bash
npm run dev
```

Then open **https://localhost:5173** in your browser.

> **Note:** The app requires HTTPS for webcam access. Vite is configured with a self-signed SSL certificate — use `https://` not `http://`. Your browser may show a security warning; click **Advanced → Proceed**.

---

## Project Structure

```
jutsu-visualizer/
├── public/
│   └── assets/          # Video effect files
├── src/
│   ├── components/
│   │   ├── Camera.jsx   # Gesture detection and rendering logic
│   │   └── Tutorial.jsx # Tutorial/landing screen
│   ├── App.jsx
│   ├── App.css
│   ├── style.css
│   └── main.jsx
├── index.html
├── package.json
└── vite.config.js
```

---

## Author

Abdullah Salman — [github.com/ubp-as](https://github.com/ubp-as)
