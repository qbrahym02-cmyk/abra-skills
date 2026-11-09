---
name: webgl-backgrounds
description: Living backgrounds that serve the foreground: gradient blobs, grain fields, flow particles, structural grids — contrast-safe and pointer-transparent.
category: frontend-craft
---

# webgl-backgrounds — خلفية تُحسّ ولا تُلاحظ

A living background is AMBIANCE: a slow, subtle, full-bleed layer behind content that makes a flat page feel physical. Load this for «خلفية متحركة»، «أجواء حية»، «بدل اللون الثابت». The prime directive: it serves the FOREGROUND — the moment it competes with content it becomes noise (design-quieter's budget applies to canvases too).

## The species (pick by the concept, one per page)

- DRIFTING GRADIENT / MESH: 2–4 huge soft blobs of the palette's deep hues slowly orbiting (classic aurora/mesh feel). Best for dark grounds; keep luminance spread LOW (all blobs within ±15% of ground) so text stays ≥4.5:1 everywhere — recheck against the actual text zones.
- GRAIN/DITHER FIELD: animated ordered-dither or film-grain shader — instant «مادة» على أي لون، cheapest of all, near-zero GPU. The default upgrade when the concept says film, print, or texture.
- FLOW FIELD / NOISE FLOW: curl-noise carrying sparse particles (≤1500 desktop) along invisible currents — organic, alive, still quiet at low opacity.
- GRID/STRUCTURE: a perspective grid or dotted lattice drifting one direction — for technical concepts (fintech, infra, terminals); keep line contrast ≤ 12% over ground so it whispers.
- RIPPLE/INTERACTIVE: reacts to pointer (a soft ripple or spotlight following the cursor) — only when the page wants playfulness; the reaction must be gentle (radius decay, 1–2s half-life).

## The shader discipline (write it small, pin it)

One fragment-shader quad, uniforms in, color out — the whole background is usually <80 lines:

    precision → uv → time-based field (noise/sin mix) → map to 2–3
    palette colors → subtle dither/grain mask (kills banding) → output

- BANDING is the amateur tell: always add a tiny blue-noise/grain term (even ±1/255) to smooth dark gradients.
- TIME-SAFE: fract/wrap your fields so the pattern at t=0 equals t=T (or drifts so slowly nobody sees the seam) — an 8-second visible loop restart reads as a glitch.
- FPS CAP ~30 for backgrounds (they are ambiance; use an accumulator in the rAF) — halves GPU cost for zero perceptible loss. Pause fully offscreen/hidden (the orchestrator rule).

## Integration rules

- z-index UNDER everything; pointer-events none; the canvas NEVER intercepts clicks — verify with a browser_click on a link that sits above it.
- Content protection: a scrim (radial/linear overlay of the ground color at 40–70% behind the text column) when text sits over busy areas — readability wins, the background yields (contrast floors re-measured OVER the actual composited pixels).
- Respect prefers-reduced-motion: render ONE beautiful static frame (t fixed at a chosen value) and stop — not a black rectangle.
- Mobile: static frame at ≤768px is a legitimate and often correct choice (battery); decide by concept and say so in the delivery.

## Verify loop

browser_open → let it run 20 seconds → browser_screenshot at 0s / 10s (change visible but subtle?) → browser_click a link over it (events pass through?) → browser_eval a contrast probe on a text element over the busiest zone (getComputedStyle + a manual ratio from the two sampled colors) → fix scrim until ≥4.5:1 → re-shoot.

## Done when
The background changes the FEEL (side-by-side with a static ground proves it) without changing the READABILITY (contrast passes over live areas), passes pointer-events through, honors reduced-motion with a designed static frame, and the two timestamped shots are attached.
