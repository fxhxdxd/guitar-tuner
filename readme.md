# Online Tuner

A small browser-based musical tuner (guitar tuner) implemented with JavaScript and the pitch detection library.

Live UI and core pieces:
- [app/index.html](app/index.html)
- [app/style.css](app/style.css)
- [app/app.js](app/app.js)

Features
- Real-time pitch detection using microphone input (Web Audio API + aubiojs).
- Visual meter and frequency histogram.
- Play standard note tone (oscillator).
- Auto mode (detect & highlight detected note) and manual note playback.
- Persistent A4 tuning reference stored in localStorage.

How to run
1. Open [app/index.html](app/index.html) in a modern browser that supports Web Audio and getUserMedia (Chrome, Firefox, Edge).
2. Grant microphone access when prompted.
3. The app uses CDN-hosted libraries (aubiojs and SweetAlert2) via script tags in [app/index.html](app/index.html).

Compatibility & limitations
- Requires a browser with Web Audio API and microphone permissions.
- Aubio pitch detection runs in the main thread via the included aubiojs build; for heavier use moving it to a worker would improve responsiveness.
- No build step — this is a static app.

Quick local server with npm + http-server:
- Start server with Python:
  - Python 3: cd app && python3 -m http.server 8080
  - Open http://localhost:8080

