<div align="center">

# PHANTOM OS

**A spatial operating system controlled entirely by bare-hand gestures.**

No mouse. No keyboard. No controller. Just your hands in the air.

[![Demo](screenshots/phantom-main.png)](#demo)

</div>

---

## Overview

PHANTOM OS is a browser-based spatial computing interface that uses your webcam and MediaPipe hand tracking to create a fully interactive OS experience — controlled with nothing but your hands and voice. It runs as a **single HTML file** with zero build steps and zero local dependencies.

Open `index.html` in a browser. Allow camera access. That's it.

---

## Features

### Hand Gesture Control
| Gesture | Action |
|---------|--------|
| **Point** (index finger) | Move cursor, hover over UI elements |
| **Pinch** (thumb + index) | Click, select, type on virtual keyboard |
| **Open Palm** | Go back / return to Home |
| **Swipe** (left/right) | Navigate between modes |

### Voice Commands
Activate with the mic button or press `V`, then say:
- `"Hey Phantom"` — Wake the AI assistant
- `"Open browser"` / `"Open music"` / `"Open notes"` — Launch apps
- `"Go home"` — Return to home screen
- `"Focus mode"` / `"Light mode"` — Toggle settings
- `"Play music"` — Control music playback
- `"Premium AI"` — Switch to Qwen3-235B

### Spatial Virtual Keyboard
A full QWERTY keyboard floating in 3D space — point to hover, pinch to type, with holographic glow feedback on every key.

### AI Assistant (Qwen3)
Powered by Qwen3 models via Featherless API:
- **Qwen3-4B** — Fast everyday chat
- **Qwen3-1.5B** — Lightweight system queries
- **Qwen3-235B** — Premium quality responses

### Built-in Apps
- **Browser** — URL bar + bookmark grid (gesture-navigable)
- **Music** — Synthesized audio player with gesture-controlled playback
- **Notes** — Text editor with virtual keyboard input
- **Messages** — Chat interface with AI-powered responses

### Visual Design
- Cinematic dark theme with neon cyan/purple aesthetics
- Glassmorphism cards with backdrop blur
- Custom holographic cursor with gesture state feedback
- Radial vignette webcam overlay
- Subtle scan-line atmosphere effect
- Light theme toggle available

---

## Tech Stack

| Component | Technology |
|-----------|-----------|
| Hand Tracking | MediaPipe Hands (21 landmarks, 6 DOF) |
| Gesture Engine | Custom weighted voting stabilization (4-frame history) |
| Cursor Smoothing | Adaptive EMA with jitter suppression |
| Pinch Detection | Dual-threshold with instant override |
| AI | Qwen3 (4B / 1.5B / 235B) via Featherless API |
| Voice | Web Speech API |
| Audio | Web Audio API synthesis |
| Styling | Tailwind CSS (CDN) |
| Fonts | Space Grotesk + Plus Jakarta Sans |
| Icons | Font Awesome 6 |
| Architecture | Single HTML file, zero dependencies |

---

## Quick Start

### 1. Clone
```bash
git clone https://github.com/YOUR_USERNAME/phantom-os.git
cd phantom-os
```

### 2. Open
```bash
# Just open it in a browser — no install, no build, no server needed
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

Or serve it locally:
```bash
npx serve .
# Then visit http://localhost:3000
```

### 3. Enable Camera
Click the camera icon at the bottom center. Allow webcam access when prompted.

### 4. Interact
- Point your index finger to move the cursor
- Pinch thumb + index to click
- Open your palm to go back
- Press `V` to activate voice commands

---

## Configuration

### AI API Key
The AI assistant uses the Featherless API. If you want to use your own key, find the API configuration in the JavaScript section of `index.html` and replace the endpoint/key.

### Camera
- Works with any standard webcam (720p+ recommended)
- Best results in good lighting with a plain background
- Hand tracking runs at ~30fps on modern hardware

---

## Project Structure

```
phantom-os/
├── index.html              # The entire OS — single file
├── README.md               # This file
├── LICENSE                 # MIT License
├── .gitignore              # Git ignore rules
└── screenshots/            # Visual documentation
    ├── phantom-main.png
    ├── phantom-music-app.png
    └── phantom-browser-app.png
```

That's it. One file does everything.

---

## Browser Support

| Browser | Support |
|---------|---------|
| Chrome 90+ | Full support |
| Edge 90+ | Full support |
| Firefox 100+ | Partial (voice may differ) |
| Safari 16+ | Partial (MediaPipe performance varies) |

Requires: `getUserMedia`, `MediaPipe Hands`, `Web Speech API`, `Web Audio API`

---

## Performance Tips

- **Good lighting** improves hand tracking accuracy significantly
- **Plain background** reduces tracking noise
- Keep 1-2 feet distance from the camera for optimal tracking
- Close other camera-using apps to avoid conflicts
- Use Chrome/Edge for best MediaPipe performance

---

## License

MIT License — see [LICENSE](LICENSE) for details.

---

<div align="center">

**Built with bare hands. For bare hands.**

</div>
