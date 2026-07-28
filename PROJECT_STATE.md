# Project State — Seeing Calculus
*Last updated: 2026-06-29*

## Current Status
Live and shared. A single-page interactive calculus site is built, pushed to GitHub, and published via GitHub Pages. The public live URL serves HTTP 200.

- **Live site:** https://calculus.ppr3.com — moved 2026-07-28 from
  `https://chrysogonum.github.io/seeing-calculus/`, which now redirects here
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

## Deployment — recorded 2026-07-28

- **Live site: https://calculus.ppr3.com** — GitHub Pages, published from branch `main` at the repo root.
- **`git push` IS the deploy.** There is no build step and no wrangler command. Pages rebuilds on
  push and the new bytes are live in about a minute.
- ⚠ GUARD: **do not delete the `CNAME` file at the repo root.** It contains `calculus.ppr3.com` and is what
  binds the subdomain. GitHub wrote it on 2026-07-28 when the custom domain was set — it was not
  there before, so it can easily read as stray. **Deleting it unbinds the domain** and the site
  falls back to `chrysogonum.github.io/seeing-calculus/`.
- The old `chrysogonum.github.io/seeing-calculus/` address **301-redirects** here, so links held from before
  the move still work. Verify at `calculus.ppr3.com`, not at the github.io address.
- ⚠ Because GitHub committed that `CNAME` file itself, the remote moved ahead of local `main`
  without anyone committing. If a push is rejected with `! [rejected] (fetch first)`, rebase onto
  `origin/main` — nothing is wrong.
