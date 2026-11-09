---
name: pointer-ambient-motion
description: The page feels the cursor: light-follow glow, trails, click ripples, particle lean — one species per page under one budgeted rAF loop.
category: frontend-craft
---

# pointer-ambient-motion — الصفحة تشعر بإصبعك

Ambient pointer motion: the page subtly responds where the cursor is — a light-follow, a trail, a ripple, particles that lean toward the hand. Load this for «آثار الماوس»، «المؤشر يضيء»، «جزيئات تتفاعل»، or when a hero needs one more layer of life. It is the MOST-abused effect family online — this pack's job is doing it TASTEFULLY and CHEAPLY.

## The species (pick exactly ONE per page)

1. LIGHT FOLLOW (the default recommendation): a large soft radial glow (600–900px, palette accent at 4–8% opacity) lerping slowly toward the cursor over the hero — «شمعة في الغرفة». Zero DOM thrash (one element, transform only), instantly premium, never annoying.
2. TRAIL: a chain of 6–12 fading dots/blobs following with decreasing lerp speed (each chases the previous). Playful brands only; keep count low, life ≤ 600ms.
3. RIPPLE: click (not move) spawns ONE ripple ring at the point — feedback, not decoration; pairs with micro-delight.
4. PARTICLE LEAN: an EXISTING particle field (webgl-backgrounds flow field) gets a gentle attractor/repulsor at the cursor — only when particles already exist for concept reasons; never add particles JUST to react to the mouse.
5. TILT: hero CARD tilts ±3–5° toward cursor (perspective transform, lerp-damped) — only on the ONE card that matters; full-page tilt = seasickness.

## The performance contract (non-negotiable)

- ONE rAF loop (motion-systems orchestrator); the pointer handler only RECORDS the target (e.targetX/Y) — all reading and writing happens in the frame, and the element writes ONE transform string.
- LERP factor 0.06–0.12 (slow chase = elegance; 1:1 tracking = nervous and cheap).
- pointermove on window with passive:true; NO work on pointerover of children; no layout reads in the loop (cache rects on resize, debounced).
- Touch: disable trail/tilt species (fingers ARE the cursor — a trail under a thumb is noise); light-follow may map to the last touch point gently, or simply ship static on touch — decide and say.
- prefers-reduced-motion: all species off (the glow parks center at low opacity, particles drift without pointer term).

## Craft rules

- Subtlety budget: if a visitor NOTICES the effect on arrival (before moving the mouse), it is too strong — ambient means discovered, not announced.
- Color: the glow/ripple/tilt-highlight comes from the accent at LOW alpha — introducing a new hue for the cursor effect breaks the token system.
- Size coupling: the light-follow radius scales with the hero's diagonal (never fixed px across breakpoints).
- One species per page — a trail AND a tilt AND a lean on the same hero is a circus.

## Verify

browser_open → browser_eval dispatch synthetic pointermoves across the hero → browser_screenshot at two positions (glow visibly relocated, everything else unmoved?) → browser_eval the FPS probe while wiggling programmatically for 2s (no frame collapse) → touch-emulation check (species disabled gracefully) → reduced-motion override → static confirmation → fix → re-shoot.

## Done when
Exactly one species ships, it is discovered-not-announced (subtle at rest), the single-loop/fps probe holds under sustained wiggle, touch and reduced-motion paths are deliberate, and the two glow-position screenshots are attached.
