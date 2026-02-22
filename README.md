# DriveMad - High‑Octane Arcade Racing

<!-- MIT License -->

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)

<!-- HTML & CSS -->

[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)

<!-- Languages & Web Standards -->

[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![ECMAScript Spec](https://img.shields.io/badge/ECMAScript-262-7A0BC0?logo=ecmascript&logoColor=white)](https://www.ecma-international.org/publications-and-standards/standards/ecma-262/)

DriveMad is a lightweight, arcade‑style HTML5 racing game optimized for short, high‑energy browser play sessions. It is implemented as a static single‑page web app (Canvas/WebGL) with responsive controls and multi‑input support (keyboard, gamepad, touch).

This README is designed to be visitor‑facing and client‑ready: it documents how to play, how to run the project locally, development guidance, project layout, performance notes, and recommended next steps to make the repository impressive to potential clients and employers.

--

## Table of Contents

- Overview
- Demo & Media
- Key Features
- How to Play (Controls)
- Quick Local Run (PowerShell)
- Development & Build (recommended)
- Project Structure
- Performance Tips
- Contributing & Code Quality
- Roadmap & Changelog
- License & Contact

--

## Overview

DriveMad focuses on immediate, arcade‑style gameplay: tight steering, fast sessions, and replayable challenges. The repo currently contains a static build (single page entry) and core assets in `css/` and `js/`. There is no bundler or package manifest detected in the repository root - development instructions below include both manual and optional Node-based workflows.

## Demo & Media

- Host the repository (or the `dist/` folder if you create one) on any static host (GitHub Pages, Netlify, Vercel). For the cleanest demo experience, upload an animated gameplay GIF (5–10s) and screenshots into an `assets/` or `docs/` folder and link them here.
- Recommended banner & preview assets:
  - `assets/readme-banner.png` (1280×360) - optional hero image
  - `assets/demo.gif` (5–10s) - short gameplay loop

## Key Features

- Tight, arcade‑style driving physics
- Multiple tracks and vehicles (configurable in code)
- Input support: Keyboard, Gamepad, Touch
- Responsive UI for desktop and mobile
- Small, dependency‑free distribution (pure HTML/CSS/JS by default)

## How to Play (Controls)

Default keyboard controls (configurable in code):

- Steer: Arrow keys / A D
- Accelerate: W / Up
- Brake / Reverse: S / Down
- Boost / Nitro: Shift / Space
- Horn / Interact: H or E
- Pause / Menu: Esc

Gamepad: standard controllers map axes to steering and triggers to throttle/brake. Touch: use on‑screen virtual controls when available.

## Quick Local Run (PowerShell)

To avoid CORS and media autoplay restrictions use a local HTTP server rather than opening `index.html` directly.

PowerShell - Python's simple HTTP server (Windows):

```powershell
# From repository root, serve port 8000 and open browser
python -m http.server 8000; Start-Process "http://localhost:8000"
```

Node (if you prefer `http-server`):

```powershell
npx http-server -c-1 . -p 8000; Start-Process "http://localhost:8000"
```

Notes:

- If you later add a `dist/` folder (build output), serve `dist/` instead of the repository root.
- Some browsers block autoplay for audio; click/tap once to unlock sound.

## Development & Build (recommended)

Currently there is no `package.json` detected in the repo. For modern development, I recommend adding a minimal Node toolchain. Example `package.json` scripts below can be adapted for your preferred bundler.

Suggested quick setup (optional):

```powershell
npm init -y
npm install --save-dev vite
```

Add these example scripts to `package.json`:

```json
"scripts": {
	"dev": "vite",
	"build": "vite build --outDir dist",
	"preview": "vite preview --port 5000"
}
```

Why use a bundler?

- Faster dev server with HMR (hot module replacement)
- Easy asset pipeline and cache busting
- Production optimizations (minification, tree‑shaking)

If you prefer to keep the project dependency‑free, continue editing `index.html`, `css/styles.css`, and `js/*.js` directly and use the simple local server instructions above to preview changes.

## Project Structure (current)

```
index.html
LICENSE
README.md
css/
	styles.css
js/
	script.js
	scripts.js
```

- `index.html`: Single page entry. Inspect this file to find boot/asset paths.
- `css/styles.css`: Layout and styles.
- `js/script.js`, `js/scripts.js`: Game logic and initialization. Consider splitting larger modules and moving to `src/` if you add a bundler.

## Performance Tips

- Bundle and minify JS for production (Vite, Webpack, or Rollup).
- Combine small images into sprite atlases.
- Compress audio and use short audio sprites for SFX.
- Defer or lazy‑load large assets (music, future levels) after the main menu.
- Aim for stable 60 FPS: profile using browser devtools and optimize the game loop throttle.

## Contributing & Code Quality

If you plan to open this project to outside contributors, add these repo files:

- `CONTRIBUTING.md` - contribution workflow and PR template
- `CODE_OF_CONDUCT.md` - expected community behavior
- `ISSUE_TEMPLATE.md` / `PULL_REQUEST_TEMPLATE.md` - templates for quick triage

**Simple contributor workflow (recommended):**

1. Fork the repo and create a topic branch
2. Run the project locally and reproduce the issue or feature
3. Open a PR with a clear description, screenshots, and testing steps

Recommended linters / tools:

- ESLint for JS code quality
- Prettier for consistent formatting
- Git hooks (Husky) to run linters before commits

### Roadmap & Changelog

**Short‑term enhancements:**

- Add a polished demo GIF and README banner
- Introduce a bundler (`vite`) and `dist/` build output
- Create an options/settings screen (control remapping, audio levels)

**Medium‑term enhancements:**

- Persistent progression (localStorage or server profiles)
- Level editor and community track sharing
- Accessibility improvements and full gamepad remapping

Maintain a `CHANGELOG.md` for release notes if you publish versions.

### License

This project is distributed under the MIT License. See `LICENSE` in the repository root.

### Contact & Commercial Licensing

For client work, custom feature development, or commercial licensing inquiries, please contact the maintainer via email or GitHub.  
Commercial licensing options and custom feature development are available upon request.

---

### Next Steps / Planned Improvements

- Add gameplay demo assets (`assets/readme-banner.png`, `assets/demo.gif`) for improved preview
- Introduce a minimal build setup using Vite and generate a production `dist/` folder
- Add `CONTRIBUTING.md` and `CODE_OF_CONDUCT.md` for open collaboration
- Add additional badges (build status, demo link) to the README header

---
