---
name: threejs-worlds
description: Build coherent 3D worlds: a five-line world bible, terrain and sky without seams, instanced set dressing, and a scroll-driven camera journey.
category: frontend-craft
---

# threejs-worlds — عالَم واحد متصل، لا مجموعة ديوراما

Load this when the ask is a WORLD: مشهد طبيعي، مدينة، صحراء تحت نجم، متحف افتراضي، مشهد معماري — an environment the visitor moves THROUGH (usually scroll- or drag-driven), not an isolated object (that is threejs-scene-craft). The bar: standing anywhere in it, the world agrees with itself — one light, one era, one weather.

## Phase 1 — The world bible (decide once, obey everywhere)

Write five lines BEFORE modeling:
- PLACE & TIME: «صحراء الجزائر شروقاً»، «مدينة مطر ليلي»، «قاعة مكتبة خشبية بنور جانبي».
- PALETTE: 3 atmospheric bands (sky / horizon / ground) + ONE accent that exists in-world (a lantern, signage, a door) — the accent must be an OBJECT, not a tint.
- SCALE UNIT: fix meters-per-world-unit and human eye height (~1.6m) — every model, camera height, and fog distance derives from it. Mixed scale is the tell of assembled demos.
- WEATHER & LIGHT: one sentence («غبار ذهبي، شمس منخفضة من اليسار، ضباب أزرق في العمق») — it decides fog color, sun color/angle, and every material's roughness.
- THE ROUTE: the visitor's path through it (scroll journey? orbit? free walk?) — this decides composition, not the other way around.

## Phase 2 — The terrain and sky

- TERRAIN: plane + vertex noise (simplex) displaced, or a composed heightfield for authored landmarks. Keep a flat corridor along the route. Low-poly aesthetic is legitimate — then COMMIT (flat shading, faceted, consistent) — the sin is accidental low-poly from lazy segments.
- SKY: a big inverted sphere with a vertex-gradient shader (or scene.background color + fog doing 80% of the work). Match the horizon band to the fog color EXACTLY — a visible seam between sky and fog is the classic amateur line.
- ATMOSPHERE: fog density set so the FARTHEST landmark is ~60% veiled (depth story) and the route never fully fogged. Dust motes / rain / snow as one instanced particle system max (threejs-scene-craft budget rules: capped counts, mobile down-tier).

## Phase 3 — The set dressing (architectural elements)

- HERO LANDMARKS: 2–3 authored structures on the route (a tower, an arch, a monolith) at true scale, each placed to be SEEN from a composed angle (walk the route yourself in preview and re-place).
- REPETITION with variation: rocks/columns/trees as instanced meshes with per-instance scale/rotation jitter and a seeded RNG — the SAME rock at the same rotation twice reads as a stamp.
- GROUND DETAIL: scattered elements near the camera only (visitors never see far-away gravel — do not render it).

## Phase 4 — The camera journey

- SCROLL-DRIVEN (most Abra cases): one camera path (CatmullRom curve of 5–8 waypoints), scroll progress maps to path t (scroll-storytelling for the wiring). Look-at targets interpolate between authored interest points — the eye should arrive AT each landmark as it passes, with a half-second of hold.
- Smoothness: lerp/damp the camera toward the path point (never hard-set), and clamp scroll velocity so a fast flick becomes a fast-but-smooth dolly, not a teleport.
- ORBIT/DRAG variant: threejs-scene-craft controls; free-walk (WASD) only when the user asks — it demands collision care and stays niche.

## Phase 5 — Living details (choose 2, never all)

- wind on grass/flags (vertex shader sway or per-instance rotation sine)
- drifting clouds (2–3 soft billboard sprites)
- a day cycle ONLY if the content needs it (slow sun+sky hue shift)
- a single animated creature/vehicle crossing at one moment of the journey (the thing they REMEMBER)
- sound off by default (engine policy).

## Verify loop

browser_open → browser_scroll the full journey end-to-end slowly → browser_screenshot at 5 checkpoints (start, each landmark, end) → check the bible: same light? same weather? scale consistent? seams between sky/fog? → fix → re-shoot. On a weak machine profile via a quick rAF-FPS probe (browser_eval counting frames over 2s) — if under ~45fps desktop, cut particle counts and far dressing before shipping.

## Done when
The five-line bible exists and is obeyed in every screenshot; the journey passes each landmark with composed angles; sky/fog/ground bands agree; and the full scroll-through runs smooth in the agent browser — evidenced by the 5 checkpoint shots.
