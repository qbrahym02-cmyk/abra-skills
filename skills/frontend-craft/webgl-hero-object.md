---
name: webgl-hero-object
description: One meaningful 3D subject inside a normal page: generated or compressed GLTF, brand-native materials, tactile interaction, performance floors.
category: frontend-craft
---

# webgl-hero-object — شيء واحد ثلاثي الأبعاد في مكانه الصحيح

The hero-object pattern: ONE meaningful 3D subject living inside an otherwise normal page (product shot, logo sculpture, mascot, data object) — interactive, integrated, and FAST. Load this for «أضف شيئاً 3D فوق الهيرو»، «اعرض المنتج مجسماً»، «لوغو ثلاثي الأبعاد». It composes with threejs-scene-craft (load that for lighting/material skeleton) — this pack adds the HERO-specific contract.

## The hero contract (break one rule and it becomes a gimmick)

1. MEANINGFUL: the object IS the subject (the product, the brand mark, the data) — never «مجسم تجريدي مبهرج» pasted over an unrelated business. If the subject has no natural 3D artifact, do NOT force one (typography or webgl-backgrounds instead).
2. INTEGRATED: sits in the page's composition — same palette tokens, contact/ambient shadow matching the page light direction, and its background either fully transparent (alpha canvas) or a seamless page-ground gradient. The tell of pasted demos: a rectangle of «مركز عرض» around the object.
3. RESPONSIVE-BOUNDED: canvas sized to its layout slot (not fullscreen unless it IS the hero), DPR-capped, and the object reframed per aspect (on 360px: closer camera, subject vertical).
4. TACTILE: pointer parallax (±4–6° lerp) as the floor; drag-to-rotate when inspection matters (OrbitControls, pan off); one click reaction when the object names something (see threejs-scene-craft interaction). For a PRODUCT: drag beats parallax (they want to turn it).

## Getting the mesh (in preference order)

1. GENERATE when the subject allows (logo → extruded/beveled shape from its SVG path; data object → parametric geometry; abstract-but-brand sculpture → lathe/knot with brand proportions). Zero bytes downloaded, infinite resolution.
2. GLTF/GLB when the user provides one (uploads/) or a real asset is required: use ONLY assets the user owns or verified-free licenses — never rip marketplace/free-packs of unclear origin. Load via GLTFLoader (CDN path pinned per frontend-stack-map).
3. COMPRESS whenever a GLB ships: run_command gltf-transform optimize per the library's CLI (dedup, weld, prune, draco or meshopt quantize) — a hero mesh should land ≤ ~1.5MB; verify the decoded size and that Draco/Meshopt decoder scripts are pinned alongside the loader. If the toolchain is unavailable on the machine, fall back to meshopt or plain quantize — and report the size honestly.

## Material & light for heroes

- Physical materials, roughness 0.3–0.7 for most surfaces (full gloss only for actual glass/metal subjects), clearcoat for lacquered product feel.
- 3-point light per threejs-scene-craft with the KEY angled to match the page's own visual light (if the page's shadows say «نور من فوق يسار», the object's key comes from above-left too).
- Contact shadow (blurred radial plane) always; environmental reflection via a small generated PMREM room (RoomEnvironment) when the material is glossy — reflections of NOTHING read dead.

## Performance floor (the hero tax)

- First paint with the object (or a stylized placeholder frame) under ~1.5s on warm cache; show a quiet loading shimmer sized to the slot if the GLB is real — layout must not jump on arrival (reserve the aspect box).
- rAF paused offscreen (IntersectionObserver) and on document.hidden; DPR ≤ 2 (≤1.5 mobile).
- No postprocessing chains for heroes — bloom/god-rays belong to full-scene work (threejs-worlds); a hero gets light and shadow right INSTEAD of post.

## Verify loop

browser_open → browser_eval (errors + presence probe + load timing via performance marks you added) → browser_screenshot rest / cursor-hover parallax state (dispatch a pointermove via browser_eval then shot) / after a drag arc → LOOK: integration honest? palette native? shadow grounded? → fix → re-shoot both desktop and 360px.

## Done when
The object demonstrably belongs to the page (same palette/light/shadow language), is tactile and responsive-bounded, loads within the floor with reserved layout, pauses offscreen, and the rest/hover/drag screenshots are attached as evidence.
