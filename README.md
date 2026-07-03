# 🔤 gravity-typography

> Matter.js 기반 알파벳 중력 비(rain) 물리 시뮬레이션

수천 개의 알파벳 문자가 화면 상단에서 중력의 영향을 받아 비처럼 쏟아져 내리고, 각각의 글자가 독립적인 물리 바디로 바닥·벽에 부딪혀 쌓이며 언덕을 이룹니다. 마우스로 쌓인 글자들을 휘저으면 폭발하듯 사방으로 흩어지는 60fps 인터랙티브 물리 텍스트 효과입니다.

[🇰🇷 한국어 (기본)](#) · [🇺🇸 English](./README.en.md)

---

## 🎬 라이브 데모 (Live Demo)

> **👉 [https://gravity-typography.vercel.app/](https://gravity-typography.vercel.app/)** — 브라우저에서 바로 실행 (60fps)

| | |
|---|---|
| ![Demo](https://img.shields.io/badge/Live-Demo-7C3AED?style=for-the-badge&logo=vercel&logoColor=white) | [![Repo](https://img.shields.io/badge/GitHub-sigco3111%2Fgravity--typography-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sigco3111/gravity-typography) |
| ![Status](https://img.shields.io/badge/Status-Live-22C55E?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Matter.js-009688?style=flat-square) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-1_CDN-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |

### 🎮 빠른 사용법
1. 위 데모 링크 클릭 → 브라우저에서 페이지 열기
2. 잠시 관전 — 화면 상단에서 알파벳 비가 떨어져 바닥에 쌓이는 모습 감상
3. **마우스 드래그** — 쌓인 글자들을 휘저어 흩어지게 만들기
4. **마우스 클릭** — 커서 주변 글자들이 폭발하듯 사방으로 분산

---

## 🤖 생성 정보 (Attribution)

이 프로젝트의 코드는 아래 모델과 프롬프트를 이용해 **자동으로 생성**되었습니다.

| 항목 | 값 |
|---|---|
| **모델** | MiniMax-M3 |
| **실행 환경** | OpenCode CLI |
| **저장소** | [`sigco3111/gravity-typography`](https://github.com/sigco3111/gravity-typography) |
| **라이선스** | MIT |
| **의존성** | Matter.js 0.19.0 (CDN, 단일 HTML) |

### 📝 사용된 프롬프트 (원문)

```
화면 상단에서 수천 개의 알파벳 문자 비가 쏟아져 내리는데, 각 글자 하나하나에 물리 엔진(Matter.js 등 활용 가능)을 적용하여 바닥에 쌓이고 구르며 언덕을 이루는 모습을 구현하고, 마우스로 쌓인 글자들을 휘저으면 폭발하듯 흩어지는 역동적인 물리 텍스트 효과를 만들어줘.
Implementation Advice: Use Matter.js for the 2D physics simulation. Each letter can be a rectangular body or a circle approximation. Render the letters using HTML5 Canvas (syncing position with the physics body). 모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## ✨ 주요 특징 (Features)

- 🌧️ **알파벳 비 (Letter Rain)** — A–Z, a–z, 한글 음절의 무작위 비가 화면 상단에서 중력의 영향을 받아 떨어짐
- ⚛️ **Matter.js 물리 시뮬레이션** — 각 글자 = 1개의 Matter rectangle body, 최대 ~1,600개 동시 시뮬레이션
- 📐 **Canvas 동기 렌더링** — HTML5 Canvas 2D Context로 매 프레임 물리 바디 위치·각도와 동기화
- 🏔️ **자연스러운 적층** — friction 0.55 / restitution 0.12 / frictionStatic 0.9 설정으로 진짜 모래처럼 쌓임
- 💥 **폭발 인터랙션** — 마우스 드래그/클릭 시 커서 주변 글자들이 반경 내 impulse로 폭발적 분산
- 🎨 **Hue 시프트** — 글자마다 무지개 색상 분포(속도·수명에 따른 HSL 보간)
- ⏱️ **60fps 안정** — `requestAnimationFrame` 루프 + 물리 timestep 정규화
- 📦 **단일 HTML** — 모든 의존성을 CDN 임베드 + 코드 1개 파일에 완결 (Matter.js 0.19.0만 외부 로드)
- 🔒 **온디바이스** — 모든 렌더링·물리가 브라우저 안에서 처리 (서버 통신 없음)

---

## 🚀 실행 방법 (Quick Start)

### 방법 1: 라이브 데모 (Vercel) — 가장 간단
👉 [https://gravity-typography.vercel.app/](https://gravity-typography.vercel.app/) — 별도 설치 없이 바로 실행됩니다.

### 방법 2: 그냥 브라우저로 열기
```bash
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```
**인터넷 연결 필요** — Matter.js 0.19.0을 `cdnjs.cloudflare.com`에서 로드합니다.

### 방법 3: 로컬 서버 (권장)
```bash
python3 -m http.server 8000
# → http://localhost:8000
```

---

## 🎮 조작법 (Controls)

| 입력 | 효과 |
|---|---|
| **관전 (기본)** | 화면 상단에서 알파벳 비가 떨어져 바닥·벽에 부딪히며 자연스럽게 쌓임 |
| **마우스 드래그** | 커서가 스치는 글자들이 폭발하듯 사방으로 흩어짐 |
| **마우스 클릭 (홀드)** | 클수록 강한 폭발 impulse — 글자들이 멀리 날아감 |
| **마우스 떼기** | 글자들이 다시 중력의 영향을 받아 바닥에 떨어짐 |

---

## 🛠️ 기술 스택 (Tech Stack)

| 영역 | 사용 기술 |
|---|---|
| **물리 엔진** | Matter.js 0.19.0 (CDN, `cdnjs.cloudflare.com`) |
| **렌더링** | HTML5 Canvas 2D Context + `requestAnimationFrame` |
| **마우스 인터랙션** | `mousedown` / `mousemove` / `mouseup` 이벤트 → impulse 적용 |
| **글자 생성** | `spawnLetter()` — 한글 음절 + A–Z + a–z 균등 분포 |
| **충돌 바디** | 1 글자 = 1개의 `Bodies.rectangle` (`LETTER_W=17`, `LETTER_H=23` px) |
| **스폰 간격** | 28ms (마우스 다운 시) / 42ms (기본값) |
| **물리 속성** | friction 0.55 / frictionStatic 0.9 / restitution 0.12 / gravity y=1 |
| **최대 글자 수** | 1,600개 동시 시뮬레이션 |
| **언어** | Vanilla JavaScript (ES2020+) |
| **번들** | 모든 의존성을 단일 `index.html`에 임베드 (Matter.js만 CDN) |

---

## 📂 프로젝트 구조

```
gravity-typography/
├── index.html          # 단일 HTML (Matter.js CDN + Canvas + Physics + JS)
├── README.md           # 한국어 (기본)
├── README.en.md        # English version
├── LICENSE             # MIT
└── .gitignore          # Node/IDE/OpenCode 임시 파일 제외
```

---

## 🎨 디자인 결정 (Design Choices)

브레인스토밍 단계에서 내린 결정:

| 결정 포인트 | 선택 | 이유 |
|---|---|---|
| **물리 엔진 선택** | Matter.js | 2D 강체 시뮬레이션 표준, 단일 파일 임베드 가능, 임펄스 API 노출 |
| **렌더링 동기** | Canvas 2D 직접 그리기 | DOM 노드 1,600개 안 만들고 캔버스 1개로 합성 |
| **글자 → 바디 매핑** | Rectangle body | 동그라미(O, 0)도 회전·회전을 자연스럽게 흡수 |
| **최적화 전략** | 최대 1,600개 캡 | 데스크탑 브라우저에서 60fps 안정 (모바일은 ~600 권장) |
| **컬러 시스템** | HSL Hue 시프트 | 충돌/이동에 따른 시각 피드백 강화 |
| **마우스 충돌** | 충돌 쿼리 + impulse | `Query.point` 로 즉시 인접 바디 선택 → `Body.applyForce` |

### 직접 커스터마이즈하고 싶다면

`index.html` 상단의 상수를 조정하면 분위기를 바꿀 수 있어요:

```js
const LETTER_W      = 17;        // 글자 폭 (px)
const LETTER_H      = 23;        // 글자 높이 (px)
const MAX_LETTERS   = 1600;      // 최대 동시 시뮬레이션 개수
const spawnInterval = 42;        // 기본 스폰 간격 (ms)
const SPAWN_BURST   = 4;         // 한 프레임에 스폰되는 글자 수
// 폭발 강도는 `explode(x, y, strength)` 의 strength 파라미터 (0~1)
```

---

## 📜 License

MIT © 2026 sigco3111

---

## 🙏 Acknowledgments

이 프로젝트는 [MiniMax-M3](https://example.com) 모델과 OpenCode CLI 환경에서 생성되었습니다. 프롬프트 엔지니어링과 디자인 결정은 저장소 소유자가 직접 수행했습니다.

---

> 🤖 *이 README 구조는 검증된 [neon-fluid](https://github.com/sigco3111/neon-fluid) 미션 형식을 차용했습니다.*
