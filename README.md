# 🔤 gravity-typography

> 화면 상단에서 쏟아지는 알파벳 비 — Matter.js 물리 엔진으로 바닥에 쌓이고, 마우스로 휘저으면 폭발하듯 흩어지는 역동적인 텍스트 효과

수천 개의 알파벳 문자가 중력의 영향을 받아 화면 상단에서 비처럼 떨어지며, 각각 개별 물리 바디로 시뮬레이션됩니다. 바닥과 벽에 부딪히고 서로 쌓이며 언덕을 이루고, 마우스로 쓸면 폭발적으로 사방으로 흩어지는 60fps 인터랙티브 데모입니다.

[🇰🇷 한국어 (기본)](#) · [🇺🇸 English](./README.en.md)

---

## 🎬 라이브 데모 (Live Demo)

> **👉 곧 공개됩니다 (Work in progress)** — OpenCode에서 `MiniMax-M3` 모델이 작업 중

| | |
|---|---|
| ![Status](https://img.shields.io/badge/Status-In_Development-F59E0B?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-Matter.js_CDN-009688?style=flat-square) |

---

## 🎮 빠른 사용법 (예정)
1. 페이지 열기
2. 잠시 관전 — 화면 상단에서 알파벳 비가 떨어져 쌓이는 모습 감상
3. **마우스 드래그** — 쌓인 글자들을 휘저어 흩어지게 만들기
4. **특수 효과** — 글자들이 폭발하듯 사방으로 분산

---

## 🤖 생성 정보 (Attribution)

이 프로젝트의 코드는 아래 모델과 프롬프트를 이용해 **자동으로 생성**됩니다.

| 항목 | 값 |
|---|---|
| **모델** | MiniMax-M3 |
| **실행 환경** | OpenCode CLI |
| **저장소** | [`sigco3111/gravity-typography`](https://github.com/sigco3111/gravity-typography) |
| **라이선스** | MIT |
| **의존성** | Matter.js (CDN, 단일 HTML 임베드) |

### 📝 사용된 프롬프트 (원문)

```
화면 상단에서 수천 개의 알파벳 문자 비가 쏟아져 내리는데, 각 글자 하나하나에 물리 엔진(Matter.js 등 활용 가능)을 적용하여 바닥에 쌓이고 구르며 언덕을 이루는 모습을 구현하고, 마우스로 쌓인 글자들을 휘저으면 폭발하듯 흩어지는 역동적인 물리 텍스트 효과를 만들어줘.
Implementation Advice: Use Matter.js for the 2D physics simulation. Each letter can be a rectangular body or a circle approximation. Render the letters using HTML5 Canvas (syncing position with the physics body). 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## 🛠️ 기술 스택 (예정)

- **물리 엔진** — Matter.js (CDN)
- **렌더링** — HTML5 Canvas 2D Context
- **언어** — Vanilla JavaScript (zero local dependencies)
- **번들** — 모든 의존성을 단일 `index.html`에 임베드

---

## 📂 프로젝트 구조

```
gravity-typography/
├── index.html          # 단일 HTML 파일 (Matter.js CDN + Canvas + Physics)
├── README.md           # 본 문서 (한국어)
├── README.en.md        # English version
├── LICENSE             # MIT License
└── .gitignore          # Node/IDE 임시 파일 제외
```

---

## 🚀 로컬 실행

```bash
git clone https://github.com/sigco3111/gravity-typography.git
cd gravity-typography
open index.html   # macOS
# 또는 브라우저에서 index.html 직접 열기
```

**인터넷 연결 필요** — Matter.js를 CDN (`cdn.jsdelivr.net`)에서 로드합니다.

---

## 📜 라이선스

MIT License — 자유롭게 사용, 수정, 배포하세요.

---

> 🤖 *이 리드미의 README 구조는 [neon-fluid](https://github.com/sigco3111/neon-fluid) 미션의 검증된 형식을 차용했습니다.*
