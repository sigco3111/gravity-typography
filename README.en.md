# 🔤 gravity-typography

> Alphabet rain from the top of the screen — letters with Matter.js physics tumble, pile up into hills, and explode outward when you sweep them with your mouse

Thousands of alphabet characters fall under gravity, each rendered as an independent physics body. They collide with the floor and walls, pile up on each other, and scatter explosively when disturbed by mouse interaction. 60fps interactive physics typography demo.

[🇰🇷 한국어 (기본)](./README.md) · [🇺🇸 English](#)

---

## 🎬 Live Demo

> **👉 Coming soon (Work in progress)** — `MiniMax-M3` is working on it via OpenCode

| | |
|---|---|
| ![Status](https://img.shields.io/badge/Status-In_Development-F59E0B?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-Matter.js_CDN-009688?style=flat-square) |

---

## 🎮 Quick Controls (planned)
1. Open the page
2. Watch — letters rain from the top and pile up at the bottom
3. **Mouse drag** — sweep through the pile to scatter them
4. **Chaos effects** — letters explode outward in all directions

---

## 🤖 Attribution

This project's code is **auto-generated** using the following model and prompt.

| Field | Value |
|---|---|
| **Model** | MiniMax-M3 |
| **Environment** | OpenCode CLI |
| **Repository** | [`sigco3111/gravity-typography`](https://github.com/sigco3111/gravity-typography) |
| **License** | MIT |
| **Dependencies** | Matter.js (CDN, embedded in single HTML) |

### 📝 Prompt Used

```
화면 상단에서 수천 개의 알파벳 문자 비가 쏟아져 내리는데, 각 글자 하나하나에 물리 엔진(Matter.js 등 활용 가능)을 적용하여 바닥에 쌓이고 구르며 언덕을 이루는 모습을 구현하고, 마우스로 쌓인 글자들을 휘저으면 폭발하듯 흩어지는 역동적인 물리 텍스트 효과를 만들어줘.
Implementation Advice: Use Matter.js for the 2D physics simulation. Each letter can be a rectangular body or a circle approximation. Render the letters using HTML5 Canvas (syncing position with the physics body). 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## 🛠️ Tech Stack (planned)

- **Physics** — Matter.js (CDN)
- **Rendering** — HTML5 Canvas 2D Context
- **Language** — Vanilla JavaScript (zero local dependencies)
- **Bundle** — Single `index.html` with all dependencies embedded

---

## 📂 Project Structure

```
gravity-typography/
├── index.html          # Single HTML file (Matter.js CDN + Canvas + Physics)
├── README.md           # Korean (default)
├── README.en.md        # English version
├── LICENSE             # MIT License
└── .gitignore          # Excludes Node/IDE temp files
```

---

## 🚀 Run Locally

```bash
git clone https://github.com/sigco3111/gravity-typography.git
cd gravity-typography
open index.html        # macOS
# or open index.html in any browser directly
```

**Internet connection required** — Matter.js is loaded from CDN (`cdn.jsdelivr.net`).

---

## 📜 License

MIT License — use, modify, and distribute freely.

---

> 🤖 *This README structure is adapted from the verified [neon-fluid](https://github.com/sigco3111/neon-fluid) mission template.*
