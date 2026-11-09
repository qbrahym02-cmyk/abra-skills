---
name: css-craft-details
description: The CSS moves that read as deep craft: honest gradient borders, alpha masks, background grids, optical alignment, matching focus rings.
category: frontend-craft
---

# css-craft-details — الحرفة الدقيقة التي تفرّق بين مصمم ومنسّق

The small CSS moves that read as deep craft — used by the best sites, fumbled by generated ones. Load this during any build's polish phase (after visual-polish's structural pass) or when a design calls for precise edge/mask/grid details.

## The recipes

1. GRADIENT BORDERS, honestly:
   - Hairline version (the premium one): border: 1px solid transparent; background: linear-gradient(var(--ground),var(--ground)) padding-box, linear-gradient(135deg, ink@20%, accent@40%, ink@20%) border-box; — a subtle gradient edging a solid card.
   - Animated beam version lives in advanced-visual-effects (beam states) — do not double-implement.
   - RTL: 135deg angles are direction-neutral; if the design says «الضوء من اليمين», mirror to 225deg consciously.
2. ALPHA MASKS (mask-image): fading an image's edge into the ground — mask-image: linear-gradient(to bottom, black 60%, transparent 100%); -webkit-mask-... for the Chromium reality (the engine's browser is Chromium: the -webkit- prefix is REQUIRED in practice — test it, do not trust memory). WHEN: hero images meeting text zones, marquee edges fading instead of clipping.
3. BACKGROUND GRID: the technical drawing ground — background-image: linear-gradient(ink@6% 1px, transparent 1px), linear-gradient(90deg, ink@6% 1px, transparent 1px); background-size: 32px 32px; — with a radial mask fading the grid out from the content focus. WHEN: engineering/infra brands, blueprint concepts. Grid spacing from the SPACE token multiples.
4. OPTICAL ALIGNMENT: icons and geometric glyphs (triangles, quotes, parentheses) get transform: translate(±0.5–1px) nudges to sit OPTICALLY centered against adjacent text — mathematical centering of a play-triangle or a closing-quote is visibly WRONG to every eye.
5. TEXT EDGE CRAFT: hanging punctuation in Arabic pull-quotes (the opening « sits outside the text block via text-indent tricks or a positioned ::before); balanced headlines with text-wrap: balance; tabular-nums on every numeric table/price (font-variant-numeric).
6. FOCUS RING THAT MATCHES: :focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; border-radius inherits } — the two-line upgrade that makes keyboard use feel designed instead of default-blue.
7. SCROLLBAR STYLING (Chromium ::-webkit-scrollbar): thin, ink@25% thumb, transparent track — the default scrollbar is the loudest «آلة» on otherwise-polished dark pages. Six lines.
8. SELECTION COLOR: ::selection { background: accent@25%; } — one line, instant «مصمم كان هنا».

## Discipline

- Each recipe used must serve the declared system (grid spacing from tokens, ring in the accent, nudge ≤ 1px) — craft is CONSISTENCY, not cleverness.
- Prefix reality: verify each modern property in the engine's Chromium via browser_eval getComputedStyle — support, not memory.
- Progressive enhancement order: craft details are layered ON a working layout; if any recipe breaks the layout at 360px, it is disabled by media query, not forced.

## Verify

browser_open → browser_screenshot a treated card / masked image / gridded hero at desktop + 360px → browser_eval probe: computed mask-image and focus ring on a focused element (browser_click a control then read its outline) → check selection by browser_eval a Selection API set + shot → fix → re-shoot.

## Done when
Every recipe applied survives computed-style verification, looks identical-quality at 360px (or gracefully degrades), uses only token values, and the treated-surface screenshots are attached.
