# 🎬 Hiya Loom

A fully browser-based screen recorder — single `index.html` file, no frameworks, no backend.

## Features

- **Capture sources** — Full screen, specific window, or browser tab (via `displaySurface`)
- **Webcam PiP** — Circular draggable bubble composited onto the recording via Canvas
- **Audio mixing** — System audio + microphone blended with Web Audio API
- **Recording controls** — Pause/resume, live timer, pulsing status dot
- **Document Picture-in-Picture** — Floating mini control bar that stays visible over other apps
- **3-second countdown** before recording starts
- **Post-recording preview** — Watch before you download
- **WebM download** — Instant, no processing
- **MP4 export** — In-browser transcoding via FFmpeg.wasm (no server needed)

## Usage

Just open `index.html` in a Chromium-based browser (Chrome / Edge).

> No installation, no dependencies, no build step.

1. Choose a capture source: **Screen**, **Window**, or **Browser Tab**
2. Optionally enable **Webcam** (picture-in-picture) and/or **Microphone**
3. Click **Start Recording** → 3-second countdown → recording begins
4. Use the floating control bar to **pause/resume** or **stop**
5. Preview the recording, then **Download WebM** or **Export MP4**

## Browser Support

| Feature | Chrome | Edge | Firefox | Safari |
|---|---|---|---|---|
| Screen capture | ✅ | ✅ | ✅ | ⚠️ limited |
| Webcam PiP | ✅ | ✅ | ✅ | ✅ |
| Document PiP | ✅ | ✅ | ❌ | ❌ |
| MP4 export | ✅ | ✅ | ✅ | ✅ |

> Document PiP is Chrome/Edge only — falls back gracefully in other browsers.

## Tech Stack

- `getDisplayMedia` — screen capture
- `getUserMedia` — webcam & microphone
- `MediaRecorder` — WebM recording (VP9/VP8 + Opus)
- `Web Audio API` — audio mixing
- `Canvas 2D` — webcam compositing at 20fps
- `documentPictureInPicture` — floating mini window
- `FFmpeg.wasm` — client-side WebM → MP4 transcoding
- Pointer Events API — cross-device drag support
