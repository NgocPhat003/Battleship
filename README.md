# ⚓ Battleship

A classic **Battleship** duel against a smart computer opponent, built as a fast, dependency-light browser game with custom ship sprites, sound effects, and background music.

> **Try it live:** [**https://sid2169.github.io/battleship/**](https://sid2169.github.io/battleship/)

[![Play Battleship](docs/screenshot-battle.png)](https://sid2169.github.io/battleship/)

---

## 🎮 Play the game

Click the screenshot above (or the link) to jump straight into the live game. The flow is:

1. **Home screen** — hit **Play**
2. **Deploy your fleet** — drag or click ships from the palette onto your 10×10 board, rotate with the **R** key, or hit **Randomize** / **Reset**
3. **Battle** — take turns firing at the enemy's hidden waters until one fleet is sunk

| Home | Setup | Battle |
| :---: | :---: | :---: |
| [![Home](docs/screenshot-home.png)](https://sid2169.github.io/battleship/) | [![Setup](docs/screenshot-setup.png)](https://sid2169.github.io/battleship/) | [![Battle](docs/screenshot-battle.png)](https://sid2169.github.io/battleship/) |

---

## ✨ Features

- **Classic 10×10 Battleship** with the canonical five-ship fleet (**17 total cells**)
- **Hunt-and-target computer AI** (parity hunting + line-extension targeting) that reliably beats random play
- **Drag-and-drop or click-to-place** fleet setup, with live placement preview, rotation (**R**), randomize, and reset
- **Origin-shifted ship sprites** (one frame per cell) rendered on individual board cells
- **Background music & sound effects** (fire / hit / miss), unlocked on first interaction
- **Enemy fleet kept hidden** until game over — then *both* fleets are revealed so it's clear each side fielded the same five ships
- **Click-safe turns** — a shot fired while the computer is thinking is queued and delivered on your next turn, never silently lost
- **ES modules + webpack 5**, Jest-tested game logic, deployed automatically to GitHub Pages in one command

---

## 🧱 Tech stack

| Concern | Tool |
| --- | --- |
| Language | Vanilla JavaScript (ES modules) |
| Bundler | [webpack 5](https://webpack.js.org/) + Babel |
| Styling | Hand-written CSS (`src/styles.css`) |
| Testing | [Jest](https://jestjs.io/) + jsdom |
| Deployment | [gh-pages](https://github.com/tschaub/gh-pages) → GitHub Pages |
| Assets | CC0 ship sprites & audio (see [`ASSETS_ATTRIBUTION.md`](ASSETS_ATTRIBUTION.md)) |

---


## Testing

- **Unit tests** cover `Ship`, `Board`, and `Game` (placement, attacks, win/loss).
- **AI tests** (`tests/computerAI.test.js`) verify parity hunting, adjacent targeting, line extension, no-wasted-shots, and that smart beats random.
- **Integration** (`tests/gameflow.test.js`) covers the Start-Battle flow; `tests/DOM.test.js` covers board rendering and the game-over fleet reveal.

```bash
npm run test:ci   # 7 suites, all passing with coverage
```



