---
name: motion-performance
description: Measure before shipping: an FPS probe in the browser, the six usual jank suspects, the repair kit, and a numbers-in-the-delivery ship gate.
category: frontend-craft
---

# motion-performance — الحركة الجميلة التي لا تتلعثم

Beauty that stutters is a failure — users feel jank as «الموقع ثقيل» before they can name it. Load this whenever a build has real motion (entrances, scroll effects, canvas, particles) BEFORE shipping — and whenever the user says يعلّق / ثقيل / بطيء / يتقطع. It pairs with motion-systems (the discipline) — this pack is the measurement and repair kit.

## Step 1 — Measure first (evidence, not vibes)

In the engine's browser:
- FPS PROBE (browser_eval):

    (new Promise(res => { let n = 0; const t0 = performance.now();
      function f(){ n++; if (performance.now() - t0 < 2000) requestAnimationFrame(f); else res(n / 2) }
      requestAnimationFrame(f) })).then(fps => window.__fps = fps)

  read window.__fps after ~2s — run it AT REST, then while SCROLLING (browser_scroll programmatically in a loop), then during the heaviest canvas interaction. Desktop floor to ship: 55fps at rest, 45fps under scroll. Below = diagnose, do not rationalize.
- LONG TASKS: browser_eval a PerformanceObserver for longtask entries > 50ms during a scripted interaction — each long task's duration and timestamp names its suspect.
- The VISUAL tell: browser_screenshot mid-animation and look for half-painted frames (torn text, half-moved elements) — jank leaves fingerprints.

## Step 2 — The six usual suspects (check in order)

1. LAYOUT-ANIMATED PROPERTIES: any transition/animation on width/height/top/left/margin/padding = reflow every frame. Convert to transform (translate/scale) + opacity, ALWAYS. The one legitimate exception: a measured height auto-expansion via a JS-tweened explicit px on the transitionend settle.
2. PROPERTY OWNERSHIP WARS: the same element's transform driven by both CSS and JS/GSAP (motion-systems' hard rule) — the stutter signature: element snaps back or jumps a frame.
3. PAINT STORMS: large blurred/glow layers repainting per frame (a 1200px blur animating its position instead of its TRANSLATION). Fix: the blur goes on a static layer, only transform moves it; or the glow is a pre-rendered PNG sprite moved by transform.
4. rAF PROLIFERATION: five independent loops (each widget spun its own) — merge into the orchestrator; and loops that never stop when offscreen — gate with IntersectionObserver.
5. SCROLL LISTENER THRASH: per-element scroll handlers doing layout reads (getBoundingClientRect) un-batched — one rAF-gated reader, one frame, all consumers.
6. CANVAS OVERSPEND: unbounded devicePixelRatio, particle counts sized to ambition not device, postprocessing chains on hero objects — apply the threejs-scene-craft budget (DPR ≤ 2, mobile down-tier, no post on heroes).

## Step 3 — The repair kit

- will-change: transform ONLY during the element's active animation window (added at trigger, removed at transitionend) — permanent will-change on many elements is memory pressure, not speed.
- content-visibility: auto on below-fold long sections (cheap scroll cost win, one line).
- FLIP technique (GSAP Flip or manual) for layout changes that must animate — measure, invert, play — instead of animating the layout properties themselves.
- Down-tier ladder when the floor still fails: particle count ÷ 2 → shadow quality down → parallax depth halved → (mobile) canvas effects → static frame. Each cut named in the delivery, not silent.

## Step 4 — The ship gate

Re-run the FPS probe after every repair until BOTH floors pass (rest + scroll). Record the numbers in the delivery («القياس: 38fps أثناء التمرير ← 57fps بعد نقل الظل إلى طبقة ثابتة ودمج الحلقات») — measured proof beats «صار أسرع».

## Done when
Both FPS floors pass with numbers attached; zero long tasks > 50ms during scripted interactions; every animated property is transform/opacity (or a justified exception, named); one orchestrator loop that sleeps; and any down-tiers shipped are listed honestly.
