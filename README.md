# About

Battleship game against a computer opponent.

> **Try it live:** [**https://ngocphat003.github.io/Battleship/**](https://ngocphat003.github.io/Battleship/)


---



## Features

- **Classic 10×10 Battleship** with the canonical five-ship fleet (**17 total cells**)
- **Hunt-and-target computer AI** (parity hunting + line-extension targeting) that reliably beats random play
- **Drag-and-drop or click-to-place** fleet setup, with live placement preview, rotation (**R**), randomize, and reset
- **Origin-shifted ship sprites** (one frame per cell) rendered on individual board cells
- **Background music & sound effects** (fire / hit / miss), unlocked on first interaction
- **Enemy fleet kept hidden** until game over — then *both* fleets are revealed so it's clear each side fielded the same five ships
- **Click-safe turns** — a shot fired while the computer is thinking is queued and delivered on your next turn, never silently lost
- **ES modules + webpack 5**, Jest-tested game logic, deployed automatically to GitHub Pages in one command


## Testing

- **Unit tests** cover `Ship`, `Board`, and `Game` (placement, attacks, win/loss).
- **AI tests** (`tests/computerAI.test.js`) verify parity hunting, adjacent targeting, line extension, no-wasted-shots, and that smart beats random.
- **Integration** (`tests/gameflow.test.js`) covers the Start-Battle flow; `tests/DOM.test.js` covers board rendering and the game-over fleet reveal.

```bash
npm run test:ci   # 7 suites, all passing with coverage
```



