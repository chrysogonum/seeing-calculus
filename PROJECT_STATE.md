# Project State — Seeing Calculus
*Last updated: 2026-06-29*

## Current Status
Live and shared. A single-page interactive calculus site is built, pushed to GitHub, and published via GitHub Pages. The public live URL serves HTTP 200.

- **Live site:** https://chrysogonum.github.io/seeing-calculus/
- **Repo:** https://github.com/chrysogonum/seeing-calculus (public)
- **Local:** `/Users/peterrepetti/calculus/index.html` (self-contained, no build step, no dependencies beyond Google Fonts)

## What this is
A personal project: an interactive site that teaches calculus visually, built as a thank-you to former Penn State math professor James Diskin. The whole point is that nothing is static — every diagram is moved by the reader (slider or cursor-drag). Five interactive moments:
1. The question — what speed at a frozen instant could mean (the 0/0 paradox)
2. The limit — secant pivots onto the tangent as the gap h → 0
3. The derivative — sweeping a sine wave traces out cos as a second curve
4. The integral — Riemann rectangles (1→160) converging to true area, error shown falling
5. The Fundamental Theorem — slope of the area-curve equals the height of the rate-curve

Design: dark indigo "notebook at night" theme, luminous cyan curves, amber tangent, handwritten margin notes in the professor's voice. Fonts: Fraunces / Spectral / IBM Plex Mono / Caveat.

## Known Issues / Blockers
- Could not visually verify in-browser this session — the Claude Chrome extension was not connected. The JS was syntax-validated by parsing (clean) and the live URL returns 200, but the interactive diagrams have not been confirmed by eye/screenshot. Worth a manual look.
- Hero ambient animation respects `prefers-reduced-motion` (renders one static frame in that case) — untested visually.

## Key Files
- `index.html` — the entire site (HTML + CSS + vanilla-JS canvas widgets inline). ~34 KB.

## Next Steps
- Manually confirm the five diagrams render and respond to input across desktop + mobile.
- Optional sixth section requested-as-offer: a real-world "why it matters" example (falling object, profit curve, population) to sit beside the beauty.
- To update: edit `index.html`, then `git add -A && git commit && git push`. Pages redeploys ~1 min after push.

## Decisions this session
- Published as a **public** GitHub Pages repo (free Pages requires public; user wants to share the link). Repo named **seeing-calculus**.
- Dedication to Prof. Diskin and the closing personal note are visible to anyone — kept intentionally, since the piece is meant to be shared.
