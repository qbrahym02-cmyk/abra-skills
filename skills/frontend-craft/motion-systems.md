---
name: motion-systems
description: One declared motion language per site (duration scale, easing family, stagger law), one engine per property, one orchestrator that sleeps.
category: frontend-craft
---

# motion-systems — الحركة لغة واحدة، لا رقصات متفرقة

A page moves WELL when every motion decision comes from ONE declared system — the same way every color comes from the palette. Load this whenever a build has (or wants) more than hover transitions: page entrances, section reveals, orchestrated sequences, scroll effects. Also the base skill before scroll-storytelling / text-motion-reveal / pointer-ambient-motion.

## Step 1 — Declare the motion language (three lines, written down)

    duration scale : 120ms (micro) / 240ms (standard) / 400ms (feature) / 800ms (scene)
    easing family  : one curve family — e.g. ease-out-quint for entrances,
                     ease-in-out for moves, spring ONLY for interactive play
    stagger law     : 40–60ms per item, capped at 8 items (a 20-item parade
                     is punishment)

Write it in the project (a comment block or the tokens file). Every animation that cannot say WHICH line it comes from is a violation — and it is these undeclared ones that make pages feel assembled.

## Step 2 — Choose ONE engine (the no-mixing rule)

- CSS FIRST: entrances (with @starting-style where available), hovers, reveals via transition/animation, view-timeline scroll reveals where supported. Zero JS, free performance.
- GSAP (CDN pinned) when you need TIMELINES: multi-element choreography, sequencing with position parameters, ScrollTrigger pinning/scrubbing, FLIP layout moves. GSAP is the choice for any awwwards-site-quality build with real motion.
- Web Animations API / Motion One for React-heavy zero-build pages wanting small programmatic control.
- HARD RULE: never drive the same property of the same element from two engines (CSS transition AND GSAP on transform = the classic stutter). One owner per property.

## Step 3 — The orchestrator (one rAF to rule them all)

Every custom animation (parallax, pointer followers, particle drift) registers into ONE loop:

    const clock = { fns: new Set(), running: false }
    function frame(t) { for (const fn of clock.fns) fn(t); if (clock.fns.size) requestAnimationFrame(frame) }
    // each effect: clock.fns.add(fn) — and MUST remove itself when its
    // element leaves the viewport / the effect is destroyed

- The loop STOPS when empty (no invisible 100% GPU burn), pauses on document.hidden, and every fn reads t from the argument (no Date.now inside).
- GSAP runs its own ticker — do not wrap GSAP tweens in your clock; just never also spin a parallel loop for CSS-driven things that don't need one.
- Scroll-driven effects read scroll position ONCE per frame (no per-element scroll listeners).

## Step 4 — What moves, and how much (the taste layer)

- ENTRANCE: one choreographed moment per page (headline words stagger + hero visual rises + UI chrome fades — three groups, ONE timeline). After that: reveals are 240ms fade+12px-rise, FAST and quiet.
- SCROLL: parallax ≤ 15% of element height (subliminal), reveals on enter at 20% visibility (not 90% — reveal happening as you ARRIVE, not before).
- EXIT/UNMOUNT: undervalued craft — things LEAVE in half their entrance time (120ms), never just vanish.
- Motion that CONFIRMS (panel opens, saved flashes) is always welcome; motion that decorates dies in the first design-quieter pass.
- prefers-reduced-motion honored globally: durations → 1ms (not display:none — STATE still changes), parallax and loops off, one static frame for canvases.

## Step 5 — Verify

browser_open → walk the page: entrance moment (browser_screenshot mid-timeline if needed) → every reveal fires once and does not re-trigger upward-downward in a loop → browser_eval an FPS probe (count frames in 2s while scrolling programmatically) → jank or double-animation = property ownership violation, fix → confirm reduced-motion emulation (browser_eval matching media override) leaves a complete static page.

## Done when
The three-line language is declared in the project; one engine owns each property; one clock exists (and sleeps); the entrance reads as ONE moment; and the FPS probe + reduced-motion check passed in the agent browser.
