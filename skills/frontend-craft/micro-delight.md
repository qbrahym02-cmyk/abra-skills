---
name: micro-delight
description: Feedback within 100ms for every touch: press states, working states, success moments, list changes — informative, never confetti.
category: frontend-craft
---

# micro-delight — لحظات صغيرة تصنع شعور «مصنوع بعناية»

Delight is FEEDBACK, not confetti: the interface quietly acknowledging every human action. Load this when the user asks اجعل التفاعل ممتعاً / أضف تفاصيل حية, or after visual-polish when the page is correct but dead in the hands. One rule above all: delight that costs a frame or misleads a user is deleted.

## Where delight lives (map ALL before writing any code)

- CURSOR & TARGET: buttons acknowledge approach (hover lift 1px / color step within 100ms) and PRESS (scale .97 or darken, 80ms) — the press state is the most-forgotten and most-felt.
- INPUT: fields glow their border on focus (the real ring, not default blue), validate softly as you type (green tick fade-in on valid — never red while the user is STILL TYPING), and animate label/placeholder transitions.
- SUBMIT: buttons enter a visible working state (spinner or morphing label «جارٍ الحفظ…») — blind 2-second freezes are where trust dies.
- SUCCESS: the one moment worth celebrating — a 400ms checkmark draw, a subtle background flash of the good-state color, the new item sliding into the list at its exact final height. Short, then stop.
- FAILURE: shake the wrong field (±4px, 3 cycles, 300ms) + a message that names the fix — never just red text appearing.
- LIST CHANGES: add/remove/reorder animate (height + opacity, 200ms) — items teleporting is the cheapest tell of machine work.
- SCROLL & NAV: active section indicator follows scroll with a smooth slide; back-to-top appears only when it means something.
- EMPTY→FIRST-DATA: the moment the first real data lands deserves care (a gentle reveal), because it is the moment the product proves itself.

## The craft rules

- FAST: interaction feedback ≤ 100ms to START. Delight is never a delay — if a user must WAIT to see cuteness, it is annoyance.
- SHORT: 120–400ms. Anything past 500ms for feedback reads as lag, not charm.
- INFORMATIVE BEATS CUTE: animate the CHANGE (what appeared, what moved where), not the ambient decoration. If two states look identical without the animation, the animation is confetti.
- ONE ORCHESTRATOR: batch every rAF loop you write; never one loop per widget (see pointer-ambient-motion for the pattern). Test on a slow mindset: would this still hit 60fps on a 5-year-old laptop?
- prefers-reduced-motion honored ALWAYS — the two-line media query: feedback becomes instant (duration 0) while STATE still communicates (color/label changes stay).
- SOUND: off by default, and if the user asks, one tiny click — never auto-playing audio.
- RTL: directional micro-motion (slides, shakes, progress) mirrors logically — a "next" slide enters from the LEFT in Arabic.

## Method
1. List the page's interaction points from the map above; mark which currently give ZERO feedback.
2. Cover the zero-feedback points FIRST (a plain button that responds beats a plain one that sparkles).
3. Implement with CSS transitions where possible (transform + opacity only), JS only for state or choreography.
4. Verify IN THE BROWSER: browser_open → perform each interaction (browser_click / browser_type) → browser_read the DOM state → browser_screenshot the mid-animation moment if needed. A delight you did not FEEL in your own browser does not exist.
5. Ask of each one: does the user SMILE or just notice? Keep the smiles; cut the noise.

## Done when
Every primary interaction gives feedback within 100ms, success/error/working states are all visibly alive, reduced-motion is honored, and the page still runs smooth in the agent browser.
