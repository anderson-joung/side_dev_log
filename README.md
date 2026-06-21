# SJ Applied Tech Tycoon

Korean manufacturing survival tycoon prototype.

A browser-based survival incremental game about running a small manufacturing company under cashflow pressure. The current prototype is a single-page HTML/CSS/JavaScript game.

## Current Direction

- Cute cat, dog, and owl workers
- Korean MCT/CNC manufacturing company
- SMT screen printer assembly line
- Four room structure:
  - 현장
  - 조립실
  - 사무실
  - 설계실
- Bright UI with black-comedy survival pressure
- Cashflow, AR, AP, debt, burn rate, pressure, safety, morale, reputation, and legal risk systems

## How to Run

Open `index.html` in a browser.

No install step is required.

## GitHub Pages

This repository can be published as a GitHub Pages static site.

Recommended settings:

- Repository: private while prototyping
- Pages source: `main` branch, root folder
- Entry file: `index.html`

## Folder Map

```text
index.html
assets/
  rooms/
  characters/
  icons/
  machines/
  raw/
docs/
prompts/
AI_HANDOFF.md
```

## Current Status

Prototype stage.

The current build uses AI-generated art assets and temporary fake character movement. Some raw assets are included for reference and should not be treated as final release assets.

## Important Notes

- Keep room backgrounds and character sprites separate in future versions.
- For final release, use watermark-free and rights-cleared assets.
- Do not rewrite the game as a central dashboard. The core direction is room-based company survival.
