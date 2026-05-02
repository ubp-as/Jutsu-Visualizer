# Naruto Jutsu Hand Gesture Visualizer

A real-time hand gesture recognition web app built with React and MediaPipe Hands. Point your webcam and use hand gestures to cast Naruto jutsu visual effects overlaid on your live camera feed. Both hands are tracked simultaneously — combine gestures to activate multiple jutsu at once.

🔴 **[Live Demo → https://naruto-jutsu-eosin.vercel.app](https://naruto-jutsu-eosin.vercel.app)**

## Gestures

| Gesture | Hand | Effect |
|---|---|---|
| Open palm | Left hand | Rasengan |
| Open palm | Right hand | Chidori |
| Closed fist with thumb up | Either hand | Fireball |
| Pinch (thumb + index finger) | Either hand | Hollow Purple |

> 💡 **Tip:** Use both hands at the same time to cast multiple jutsu simultaneously — try Rasengan + Chidori at once!

## How It Works

- Uses **MediaPipe Hands** to track 21 hand landmarks per hand in real time
- Detects hand poses by comparing distances between landmark points
- Renders effects using the **Canvas 2D API** — Hollow Purple is a fully custom particle system with radial gradients and swirling ring animations at 60fps
- Video effects (Rasengan, Chidori, Fireball) are overlaid using `mix-blend-mode: screen` for a transparent compositing effect
- Supports **dual-hand tracking simultaneously** — multiple jutsu can be active at the same time

## Tech Stack

- React 19
- MediaPipe Hands
- Vite
- Canvas 2D API

## Getting Started

### Prerequisites

- Node.js (v18+)
- A webcam

### Installation

```bash
git clone https://github.com/ubp-as/Naruto-Jutsu-Visualizer.git
cd Naruto-Jutsu-Visualizer
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

### Running the App

```bash
npm run dev
```

Then open `https://localhost:5173` in your browser.

> **Note:** The app requires **HTTPS** for webcam access. Vite is configured with a basic SSL certificate so use `https://` not `http://`. Your browser may show a security warning — click "Advanced" and proceed anyway.

## Project Structure

```
naruto-jutsu/
├── public/
│   └── assets/          # Video effect files
├── src/
│   ├── components/
│   │   └── Camera.jsx   # Main gesture detection and rendering logic
│   ├── App.jsx
│   ├── App.css
│   ├── main.jsx
│   ├── index.css
│   └── style.css
├── index.html
├── package.json
└── vite.config.js
```

## Author

Abdullah Salman — [github.com/ubp-as](https://github.com/ubp-as)
