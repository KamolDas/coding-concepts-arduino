# Coding Concepts — Arduino Edition

Nine modules from the setup()/loop() model through digital and analog I/O, serial communication, non-blocking timing, sensors, actuators and interrupts, multi-device communication protocols, and a capstone project that combines them all.

| # | Module |
|---|--------|
| 1 | Arduino Fundamentals |
| 2 | Digital I/O |
| 3 | Analog I/O & PWM |
| 4 | Serial Communication |
| 5 | Timing & State Machines |
| 6 | Sensors & Libraries |
| 7 | Actuators & Interrupts |
| 8 | I2C, SPI & Wireless |
| 9 | Capstone Project |

Every chapter's code is real Arduino/C++ meant to run on actual hardware (or a free simulator like [Wokwi](https://wokwi.com) or Tinkercad Circuits) — each `sandboxNote` callout says what to wire up.

## Architecture

Same data-driven design as the other editions in this series: content lives in `data/*.json`, rendered by a shared `chapter.html` + `assets/app.js`.

```
index.html / chapter.html   — page shells
assets/styles.css           — shared styling
assets/app.js                — JSON-driven renderer, syntax highlighting, persistence
data/chapters.json           — nav/index summary
data/chapter1.json … 9       — full content per chapter
wrangler.toml / package.json — Cloudflare Pages config + npm scripts
```

Edit a chapter by editing its `data/chapterN.json` — no HTML/JS changes needed.

## Running locally

```bash
python3 -m http.server 8000   # fetch() needs http://, not file://
```

## Deploying

- **GitHub Pages** — push to GitHub, enable Pages on `main` / root (or drag-and-drop upload via GitHub's web UI, no git needed).
- **Cloudflare Pages (Git-connected)** — Workers & Pages → Create → Connect to Git → Build command empty, Output directory `/`.
- **Cloudflare Pages (Direct upload)** — Workers & Pages → Create → Upload assets → drag this folder in.
- **Cloudflare Pages (CLI)** — `npm install && npx wrangler login && npm run deploy`.

## Progress

Checklists and notes save to `localStorage` per chapter — nothing leaves the browser.

## Author

Kamol Das · Microbilogy, University of Chittagong
