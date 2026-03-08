# 📷 PHOTO BOOTH

A vibecoded real-time WebGL photo booth that runs entirely in the browser. No installs, no backend.

**[Try the live demo →](https://ctborg.github.io/bmt/)**

---

## Filters

| Filter | Description |
|--------|-------------|
| 🎥 Passthrough | Clean mirrored live feed |
| 💥 Comic Book | Sobel edge detection + quantized palette |
| ❄️ Snowfall | Accumulating snow sim with surface detection and hand-blown dust |
| 👽 The Alien | Mouse-driven fisheye bulge with green tint |
| 🌡️ Thermal | Luminance-mapped heat palette |
| 🪞 Quad Mirror | Four-way kaleidoscope |
| ⚡ Neon Glitch | RGB chromatic split, random scanline glitching, neon bloom |
| 🎞️ Vintage Film | Sepia tone, grain, vignette, flicker |
| 👾 Pixelate | 10px block quantization |
| 🎨 Oil Paint | Kuwahara filter with saturation boost |
| 🤏 Head Squish | Pinch your fingers over your head to squish it via MediaPipe Hands |
| 💭 Deep Thinker | Scratch your head to make thought bubbles appear above you |

## Controls

- **Arrow keys** or the **◀ / ▶ buttons** to cycle filters
- **Space / Enter** or the **shutter button** to capture a photo
- Captured photos appear in the gallery strip — tap to view or download

## How It Works

Filters are GLSL fragment shaders running on a WebGL canvas fed by the webcam. Two filters use [MediaPipe Hands](https://google.github.io/mediapipe/solutions/hands) for gesture detection: Head Squish tracks pinch distance; Deep Thinker detects lateral wrist movement near the top of the frame.

Everything is a single self-contained `index.html` — no build step, no dependencies to install.

## Usage

`getUserMedia` requires a [secure context](https://developer.mozilla.org/en-US/docs/Web/Security/Secure_Contexts) — the page must be served over **HTTPS** or from **localhost**. Opening `index.html` directly as a `file://` URL won't work in most browsers.  For easy local testing, use a local websever. If you have python installed, try this: 

```bash
# Quick local server (Python)
python -m http.server 8080
# then open http://localhost:8080
```
