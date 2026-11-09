---
name: threejs-scene-craft
description: A correct scene from the first run: 3-point lighting, ACES tone mapping, DPR caps, one rAF loop, offscreen pause, and full dispose.
category: frontend-craft
---

# threejs-scene-craft — مشهد صحيح، لا مشهد يعمل بالكاد

Load this BEFORE writing any Three.js scene (a 3D hero, product view, data sculpture, game-ish canvas). «يعمل» ليس المقياس؛ المقياس: يبدو مادياً حقيقياً، يجري بسلاسة، ويُنظّف بعد نفسه. Version rule from frontend-stack-map applies: pin the CDN build and web_read the CURRENT docs when unsure of an API — Three.js renames things between releases.

## The skeleton (never improvise the order)

    import-or-cdn → renderer → scene → camera → lights → objects → controls
    → resize handler → animate loop → dispose on teardown

- RENDERER: antialias on, alpha only when the canvas composites over page ground, setPixelRatio(Math.min(devicePixelRatio, 2)) — unbounded DPR is the #1 laptop-killer. outputColorSpace = SRGBColorSpace and toneMapping = ACESFilmic with exposure ~1.0–1.2 for anything wanting photographic depth.
- CAMERA: fov 35–50 (not 75 — wide fov flattens and screams "default"). Position it, then LOOK at the subject's center; add OrbitControls (damping on, enablePan false for hero objects, minDistance/maxDistance clamped so users cannot get lost).
- LIGHTS — the difference between «بلاستيكي» و«سينمائي»:
  1 key light (DirectionalLight, warm or cool per concept), 1 fill (softer, from opposite side, ~1/3 intensity), 1 rim from behind for silhouette separation. Ambient only as a floor (≤0.4).
  MeshStandardMaterial everywhere (or Physical for glass/metal); NEVER Basic/Lambert for anything lit.
  Optionally one large soft «studio» feel via hemisphere light (sky = page background hue, ground = ink hue).

## Geometry & material craft

- Segments budget: cylinders/spheres need 48–64 radial segments to catch light smoothly; torus knots and lathe surfaces read beautifully at low cost. Reuse geometries and materials across instances.
- The 3-shape rule for abstract heroes: one hero geometry + one support (ring/stand) + atmosphere (particles or fog). More shapes without hierarchy reads as clutter in 3D even faster than in 2D.
- Color: pick the palette from the page tokens — the object should feel NATIVE to the site, not a demo reel. Ground contact: a subtle shadow (a blurred radial-gradient plane texture, or renderer shadows with one shadow-casting light at 1024 map) sells physicality more than any post effect.
- Fog (scene.fog matched to background) is the cheapest depth cue and hides pop-in at edges.

## The loop and the budget

- ONE rAF loop (motion-systems' orchestrator rule); pause it when the canvas is offscreen (IntersectionObserver) and when document.hidden — a burning GPU on a scrolled-past canvas is how users learn to hate your pages.
- Idle motion: slow rotation (0.1–0.3 rad/s) + a breath (position.y sine, ±2% scale) reads alive; anything faster reads nervous.
- DPR, particle count, and shader complexity down-tier for mobile (matchMedia('(max-width:768px)')): half the particles, DPR ≤ 1.5.

## Interaction (when the user wants it, not always)

- Pointer parallax: rotate the hero ±5° toward cursor (lerp toward target each frame — never snap). In RTL keep spatial logic identical (it is not directional text).
- Click states: raycast against the hero mesh to trigger one deliberate reaction (scale pulse + accent emissive flash) — tie it to MEANING (a section jump), not decoration.
- Drag-to-rotate already covered by OrbitControls; do not stack custom drag handlers on top of it.

## The verify loop (this engine's advantage)

browser_open the file → browser_eval window errors + a presence probe (!window.THREE means the CDN tag is wrong) → browser_screenshot TWO moments (initial + after browser_click on the canvas or a few seconds of motion) → LOOK: is it lit like photography? is the background seamless with the page? is anything floating without contact shadow? Fix → re-shoot.

## Dispose (the grown-up detail)

If the page can navigate away or the canvas unmounts: cancelAnimationFrame, renderer.dispose(), geometry.dispose(), material.dispose(), controls.dispose(). A leaky WebGL context crashes the SECOND page view.

## Done when
The scene renders with ACES tone mapping and 3-point lighting, DPR-capped, pausing offscreen; two screenshots prove it (rest + interacting); zero console errors in browser_eval; and the object's palette is visibly the PAGE's palette.
