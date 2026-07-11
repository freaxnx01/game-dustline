# DUSTLINE — Playable Slice (publish package)

A top-down vertical-scroll helicopter shooter, built as a self-contained HTML prototype in the DUSTLINE art direction (desert sector). This package is ready to publish as a static site on GitHub Pages.

## What's in here

- `index.html` — **the deliverable.** Fully self-contained bundle (fonts, runtime, game code inlined). Works offline, no build step, no server-side anything. This is what gets served.
- `source/DUSTLINE Playable.dc.html` — the original authored source (template + game logic class). Reference only; it requires `support.js` next to it to run.
- `source/support.js` — the design-component runtime the source file loads.

**Do not edit `index.html` directly** — it is compiled output. Treat `source/` as the source of truth; small tweaks (tuning constants, copy, colors) can be made there and re-bundled, or simply patched in both places if trivial.

## Task for Claude Code: publish to GitHub

1. Create a new public repo (suggested name: `dustline`).
2. Commit this folder's contents with `index.html` at the repo root.
3. Enable GitHub Pages: Settings → Pages → Deploy from branch → `main`, root (`/`). Or add the one-line `.github/workflows` static-pages action if preferred.
4. Verify the published URL loads, shows the DUSTLINE title screen, and the game starts on Enter.
5. Use the "Game" section below for the repo README.

No build tooling, package.json, or dependencies are needed — resist adding any.

## Game

**DUSTLINE — Sector 01: Open Desert.** Fly the AH-7 Kestrel gunship up a scrolling desert battlefield, break four waves of armor (tanks, AA quad emplacements, escort jeeps), and destroy the GORGON land dreadnought — turret, then AA quads, then exposed core.

Controls (keyboard required):
- **WASD / Arrows** — fly
- **Guns** — auto-fire
- **X / Space** — homing rocket (limited; resupply crates drop by parachute)
- **P** pause · **M** sound · **R** restart · **Enter** launch
- **H** — debug hitbox overlay

Features: chain-multiplier scoring with persistent best score (localStorage), hull damage states with smoke/fire, supply drops (hull repair / rockets), procedural desert terrain (craters, roads, scrub, tire tracks), WebAudio synth SFX (rotor, guns, explosions, alarms).

Renders at a fixed 1600×900 logical resolution, letterbox-scaled to the window. Canvas 2D for the game world; DOM overlay for HUD and menus.

## Art direction tokens

Palette: ink `#0B0D10` / `#14161A`, panel `#1B1F25`, text `#E9EDEA`, sand `#C9B180` / `#A9905E`, armor tan `#A08553`, steel `#3D4A55` / `#4C5C69`, signal yellow `#FFC43D`, alert orange `#F5551B`, cyan `#37D6E0`, tracer pink `#FF7DAD`, green `#7CC24E`.

Type: **Saira Stencil One** (display/title), **Chakra Petch** (UI), **IBM Plex Mono** (data/readouts). Angular clipped-corner panels (`clip-path` chamfers), no rounded-pill UI.

## License / attribution

All art is original vector/canvas work created for this project. Fonts are Google Fonts (OFL), embedded in the bundle.
