# 🔤 gravity-typography

> Matter.js-powered alphabet gravity rain physics simulation

Thousands of alphabet characters fall under gravity from the top of the screen. Each letter is an independent physics body that collides with the floor and walls, piles up into natural hills, and explodes outward when you sweep them with your mouse. 60fps interactive physics typography.

[🇰🇷 한국어 (기본)](./README.md) · [🇺🇸 English](#)

---

## 🎬 Live Demo

> **👉 [https://gravity-typography.vercel.app/](https://gravity-typography.vercel.app/)** — Run it directly in your browser (60fps)

| | |
|---|---|
| ![Demo](https://img.shields.io/badge/Live-Demo-7C3AED?style=for-the-badge&logo=vercel&logoColor=white) | [![Repo](https://img.shields.io/badge/GitHub-sigco3111%2Fgravity--typography-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sigco3111/gravity-typography) |
| ![Status](https://img.shields.io/badge/Status-Live-22C55E?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Matter.js-009688?style=flat-square) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-1_CDN-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |

### 🎮 Quick Start
1. Click the demo link above → page opens in your browser
2. Watch — letters rain from the top and pile up at the bottom
3. **Mouse drag** — sweep through the pile to scatter them
4. **Mouse click** — letters near the cursor explode outward in all directions

---

## 🤖 Attribution

This project's code is **auto-generated** using the model and prompt below.

| Field | Value |
|---|---|
| **Model** | MiniMax-M3 |
| **Environment** | OpenCode CLI |
| **Repository** | [`sigco3111/gravity-typography`](https://github.com/sigco3111/gravity-typography) |
| **License** | MIT |
| **Dependencies** | Matter.js 0.19.0 (CDN, single HTML) |

### 📝 Prompt Used

```
화면 상단에서 수천 개의 알파벳 문자 비가 쏟아져 내리는데, 각 글자 하나하나에 물리 엔진(Matter.js 등 활용 가능)을 적용하여 바닥에 쌓이고 구르며 언덕을 이루는 모습을 구현하고, 마우스로 쌓인 글자들을 휘저으면 폭발하듯 흩어지는 역동적인 물리 텍스트 효과를 만들어줘.
Implementation Advice: Use Matter.js for the 2D physics simulation. Each letter can be a rectangular body or a circle approximation. Render the letters using HTML5 Canvas (syncing position with the physics body). 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## ✨ Features

- 🌧️ **Alphabet Rain** — random letters from A–Z, a–z, and Korean Hangul syllables fall under gravity
- ⚛️ **Matter.js Physics** — each letter = one Matter rectangle body, up to ~1,600 bodies simulated simultaneously
- 📐 **Canvas-synced Rendering** — HTML5 Canvas 2D Context redraws every frame, synced with body positions and angles
- 🏔️ **Natural Pile-up** — friction 0.55 / restitution 0.12 / frictionStatic 0.9 give a real sand-like stacking feel
- 💥 **Explosion Interaction** — mouse drag/click triggers an impulse on nearby bodies, scattering them explosively
- 🎨 **Hue Shifting** — each letter gets a rainbow color (HSL interpolation by velocity/age)
- ⏱️ **Stable 60fps** — `requestAnimationFrame` loop with framerate-independent physics timestep
- 📦 **Single HTML** — all code in one file, only Matter.js is loaded from CDN
- 🔒 **On-Device** — all rendering & physics runs in the browser (no server communication)

---

## 🚀 Run It

### Option 1: Live Demo (Vercel) — easiest
👉 [https://gravity-typography.vercel.app/](https://gravity-typography.vercel.app/) — works out of the box.

### Option 2: Open Locally
```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```
**Internet required** — Matter.js 0.19.0 is loaded from `cdnjs.cloudflare.com`.

### Option 3: Local Server (recommended)
```bash
python3 -m http.server 8000
# → http://localhost:8000
```

---

## 🎮 Controls

| Input | Effect |
|---|---|
| **Idle (default)** | Letters rain from the top, collide with floor & walls, and pile up |
| **Mouse drag** | Letters swept by the cursor explode outward in all directions |
| **Mouse click (hold)** | Stronger explosion impulse — letters fly far |
| **Mouse release** | Letters fall back under gravity and re-stack |

---

## 🛠️ Tech Stack

| Domain | Technology |
|---|---|
| **Physics engine** | Matter.js 0.19.0 (CDN, `cdnjs.cloudflare.com`) |
| **Rendering** | HTML5 Canvas 2D Context + `requestAnimationFrame` |
| **Mouse interaction** | `mousedown` / `mousemove` / `mouseup` → impulse applied |
| **Letter generation** | `spawnLetter()` — Korean syllables + A–Z + a–z uniform distribution |
| **Collision body** | 1 letter = 1 `Bodies.rectangle` (`LETTER_W=17`, `LETTER_H=23` px) |
| **Spawn interval** | 28ms (while mouse held) / 42ms (default) |
| **Physics params** | friction 0.55 / frictionStatic 0.9 / restitution 0.12 / gravity y=1 |
| **Max letters** | 1,600 bodies simulated simultaneously |
| **Language** | Vanilla JavaScript (ES2020+) |
| **Bundle** | single `index.html` with embedded code (only Matter.js on CDN) |

---

## 📂 Project Structure

```
gravity-typography/
├── index.html          # Single HTML (Matter.js CDN + Canvas + Physics + JS)
├── README.md           # Korean (default)
├── README.en.md        # English version
├── LICENSE             # MIT
└── .gitignore          # Node/IDE/OpenCode temp file exclusion
```

---

## 🎨 Design Choices

Decisions made during brainstorming:

| Decision | Choice | Rationale |
|---|---|---|
| **Physics engine** | Matter.js | 2D rigid-body standard, single-file embed, exposes impulse API |
| **Rendering strategy** | direct Canvas 2D draw | avoid 1,600 DOM nodes; one canvas composites everything |
| **Letter → body mapping** | rectangle body | rotation of round shapes (O, 0) absorbs cleanly |
| **Optimization** | 1,600-body cap | stable 60fps on desktop browsers (mobile recommended: ~600) |
| **Color system** | HSL hue shift | enhanced visual feedback from collisions & movement |
| **Mouse collision** | query + impulse | `Query.point` for instant adjacent body, `Body.applyForce` for push |

### Customize It Yourself

Tune the constants at the top of `index.html` to change the vibe:

```js
const LETTER_W      = 17;        // letter width (px)
const LETTER_H      = 23;        // letter height (px)
const MAX_LETTERS   = 1600;      // max simultaneous bodies
const spawnInterval = 42;        // default spawn interval (ms)
const SPAWN_BURST   = 4;         // letters spawned per frame
// explosion strength is the 3rd arg of explode(x, y, strength) — range 0..1
```

---

## 📜 License

MIT © 2026 sigco3111

---

## 🙏 Acknowledgments

This project was auto-generated by the [MiniMax-M3](https://example.com) model in the OpenCode CLI environment. Prompt engineering and design decisions were made by the repository owner.

---

> 🤖 *This README structure is adapted from the verified [neon-fluid](https://github.com/sigco3111/neon-fluid) mission template.*
