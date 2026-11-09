---
name: interactive-globe
description: The globe as a story device: dotted or wireframe sphere, clickable markers, drawn arcs, idle rotation that yields to the user hand.
category: frontend-craft
---

# interactive-globe — الكوكب كواجهة

The globe is a STORY device: «موقعنا في 40 دولة»، «رحلات خطوطنا»، «شبكة خوادمنا». Load this for أي كرة أرضية / خريطة تفاعلية / أقواس رحلات. The bar: it must SAY the sentence it exists to say — a spinning ball with random dots is a screensaver, not content. (Scene skeleton from threejs-scene-craft applies: pinned CDN, DPR cap, one loop, offscreen pause.)

## The anatomy (build in this order)

1. THE SPHERE: pick ONE representation and commit:
   - DOTS/particles globe (points sampled on land masses) — modern, light, brandable; land data from a compact encoded source the user's project provides, or a small image-based sampling trick you can regenerate (never a multi-MB geo dataset for a hero).
   - WIREFRAME/hologram sphere — technical brands, cheapest.
   - TEXTURED globe (real Earth imagery) — only when geography is the CONTENT (tourism, aviation); license-clean imagery only, and it drags you toward «مظهر خرائط جوجل» — offset with strong brand post-tinting (duotone to the palette).
2. THE MARKERS: the real locations from the brief, as small accent points with soft glow sprites — SIZED by meaning (count? importance?) if the data says so, and each clickable (raycast) to a small popup card (city + the fact). «قابلة للنقر» هو الفرق بين ديكور ومحتوى.
3. THE ARCS: connections between related markers (routes, coverage, dependencies): quadratic bezier lifted above the surface, drawn progressively (shader or geometry with an animated draw range) in the accent color, ≤ 8 simultaneous — a sky full of arcs is noise.
4. THE MOTION: slow idle rotation (west→east, ~0.05–0.15 rad/s); initial camera framing that puts THE STORY REGION front-center at load (an Arabic product's globe opens on the Arab world, not the Atlantic); markers pulse gently in sequence — the eye follows the story.

## Interaction contract

- DRAG to rotate (OrbitControls: rotate only, damping, no pan, clamped polar so users cannot view the pole-on void).
- HOVER a marker → its label; CLICK → the card (positioned in DOM over the canvas, RTL-aware, keyboard-reachable — the card is a page element, not a canvas drawing).
- Auto-rotate pauses while the user interacts (resume after 3s idle) — fighting the user's hand is the most-felt flaw in globe demos.
- A region-jump row (chips: «الخليج · أوروبا · آسيا») that tweens the globe to face each cluster — the cheapest way to make it CONTENT-driven.

## Craft & performance

- Palette: sphere in deep ground tones, markers/arcs in the single accent; ocean-vs-land contrast readable but quiet (the globe is the SUBJECT, not a traffic light).
- Glow via additive sprite textures (tiny radial PNG you generate), never full-screen bloom.
- Point budget: ≤ 12k dots for the dotted globe (mobile ≤ 6k), instanced; arcs as merged line geometry animated by ONE uniform clock.
- The globe canvas is a bounded hero card (webgl-hero-object contract): background transparent into the page ground, contact shadow optional, pauses offscreen.

## Verify loop

browser_open → browser_screenshot initial frame (story region centered?) → browser_click a marker (card appears, readable?) → browser_drag across the globe (rotation smooth, auto-rotate yields and resumes?) → browser_screenshot mid-drag + the open card → 360px frame check (globe reframed, card fits) → fix → re-shoot.

## Done when
The first frame already tells the story sentence (region centered, markers visible); markers are clickable with real cards; drag/hover/pause all behave; the budget holds (dots capped, one clock, offscreen pause); and the interaction screenshots are attached.
