---
name: advanced-visual-effects
description: The expensive-surface catalog with recipes and when: gooey blobs, liquid sheen, progressive blur, layered shadows, duotone, beam states.
category: frontend-craft
---

# advanced-visual-effects — قائمة طعام التأثيرات: اطلب بمعرفة، لا بجشع

The effects that make a surface feel EXPENSIVE — each with a recipe, a WHEN, and a cost. Load this when the concept calls for Rich materials (سائل، معدن، ضباب، ضوء) or when you need ONE more layer of finish. Iron rule from the design packs: a page carries AT MOST two of these families, chosen BY the concept — a page wearing all of them is a carnival.

## The menu (families, recipes, when)

1. GOOEY BLOBS (متلاصقة كالسائل): SVG filter — feGaussianBlur on two+ overlapping shapes + feColorMatrix alpha-threshold re-solidifying the blur (the gooey bridge forms where shapes approach). WHEN: organic/playful brands, hero backdrops behind type. COST: cheap (static, animatable via CSS transform on the shapes). RTL-agnostic. Keep saturation from the PALETTE; two blobs beat five.
2. LIQUID METAL / ANISOTROPIC SHEEN: a conic/linear gradient with animated background-position under a masked border or text (background-clip: text for chrome/mercury type). WHEN: premium tech accents, ONE headline or ONE border. COST: cheap. Trap: full metallic body text is unreadable — sheen belongs to short display words and hairline borders.
3. PROGRESSIVE BLUR (الضباب المتصاعد): stacked backdrop-filter layers of increasing blur toward the top (3 strips: 8px/16px/24px) so content scrolled UNDER a sticky bar melts instead of hard-cuts. WHEN: sticky headers/cards over scrolling content. COST: moderate (GPU per strip — cap 3 strips, disable below 768px). This is the single highest-value "modern iOS" upgrade.
4. LAYERED SHADOWS (الظل المصفوف): two shadows on one surface — a tight dark (0 2px 8px ink@25%) + a wide faint (0 12px 32px ink@8%) — and the SAME light direction across every elevated element on the page. WHEN: always (this replaces the default box-shadow everywhere). COST: free.
5. DUOTONE IMAGES (الصورة بلونين): grayscale(1) + a gradient map via background-blend on the image's container (ground→accent). WHEN: unifying mixed-quality photography into ONE brand treatment — the fastest «curated» upgrade there is. COST: free. Apply to ALL images or NONE.
6. BEAM & GLOW STATES (الأشعة والتوهج): a rotating conic-gradient border on interactive cards (border-image or a padded background-clip trick) + a soft accent glow beneath. WHEN: ONE hero card or the active state of a primary control. COST: cheap-moderate. Trap: glows on every card = neon soup; also re-verify text contrast over the glow.
7. HALFTONE/DITHER TEXTURE: CSS repeating-radial dots or a tiny generated noise PNG tiled at 3–6% opacity over flat fills. WHEN: print/editorial concepts — instant «مادة ورقية». COST: free. (Animated version lives in webgl-backgrounds' dither species — static here.)

## The ordering discipline

- Read the CONCEPT (awwwards-site-quality phase 1) → name the ONE material world (ورق؟ معدن؟ سائل؟ ضوء؟) → pick the family that says it → apply at the two touchpoints where it matters most (hero surface + one recurring component) → STOP.
- Each chosen effect must re-use the token system (the gooey blobs are palette colors, the sheen is ink+accent, the duotone is ground→accent). An effect introducing a foreign color is a bug.
- Contrast re-check AFTER applying (duotone and glow both can push text under 4.5:1 — measure over the composited result, per webgl-backgrounds' probe method).
- Feature safety: backdrop-filter and background-clip:text need a graceful fallback (solid tint / plain color text) — write the fallback line, it is one line.

## Verify

browser_open → browser_screenshot each effect's touchpoint at 1× and, for blur/sheen, with browser_eval a scroll to see progressive blur actually progress → contrast probe over the treated areas → 360px (strips disabled gracefully? metallic type still legible?) → fix → re-shoot.

## Done when
At most two families ship, both concept-justified and token-colored, every treated surface passes contrast, fallbacks exist, and the touchpoint screenshots are attached.
