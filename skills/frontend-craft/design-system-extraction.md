---
name: design-system-extraction
description: Extract a working token system (color roles, type scale, space unit, shape, motion) from any reference site or file, measured not guessed.
category: frontend-craft
---

# design-system-extraction — من مرجع جميل إلى نظام قابل لإعادة الاستخدام

When the user loves an existing thing — «أحب شكل موقع X»، «خذ هوية هذا الملف»، «طبّق نفس روح صفحتنا القديمة» — do not eyeball-copy pages. EXTRACT the system underneath, write it down as tokens, and build YOUR design from it. This is the honest, reusable, original version of «imitate that site» (it also protects you from plagiarism: you take the GRAMMAR, never the sentences).

## Phase 1 — Gather evidence from the reference

- Site: browser_open the URL → browser_read (structure) → browser_screenshot key views (home, one content page, one form/control if exists). Full-page shots beat viewport shots.
- Local file / attachments: read_file / pdf_read; for images use browser_open on the file.
- Multiple references? Extract each separately FIRST, then merge — never average two systems into mush.

## Phase 2 — Extract the five token layers (write them as you find them)

1. COLOR: for each shot, list the distinct color ROLES — ground, ink, muted-ink, accent(s), state pair, image treatment (duotone? overlay?). Sample hexes via browser_eval on the live page (getComputedStyle) when possible — eyedropper guesses from screenshots lie. Keep the palette ≤ 7 roles. Note the GROUND RATIO in the design (70% ground / 25% ink / 5% accent is a different universe from 40/40/20).
2. TYPE: families used (serif? grotesk? mono where?), the actual scale steps (collect computed font-sizes — they will cluster into 5–7 steps), weights in play (is there a heavy display weight, or all-400 quietness?), line-heights, and how headlines are SET (huge+tight? centered? uppercase tracked?).
3. SPACE: the base unit (divide several observed gaps; the largest common divisor — usually 8 or 4), section rhythm (how much air between blocks), container width and margins policy.
4. SHAPE & SURFACE: radius policy, border weights, shadow style (none / hairline / soft-layered / hard-offset), texture/grain/noise presence, image treatment (rounded? full-bleed? bordered?).
5. MOTION & VOICE (if observable): do things move? how fast, how eased? And the COPY voice — formal/warm/technical — a system includes its words' attitude.

## Phase 3 — Write the extracted system (the deliverable that survives)

One file (design-tokens.md in the project, or the top of your CSS as :root custom properties):

    palette:  ground #…, ink #…, muted #…, accent #…, good #…, bad #…
    type:     display <family> <weights>, body <family>; scale 12/14/16/20/28/44/72
    space:    base 8; section-gap 96; container 1120; page-margin 24
    shape:    radius 12/999; border 1px hairline @ ink-15%; shadow none-soft
    motion:   160/320ms; ease-out-quint; entrance: fade+rise 12px, stagger 40ms
    voice:    جملة قصيرة مباشرة، مخاطبة بالمفرد، بلا مصطلحات

## Phase 4 — Build WITH it, not FROM it
Apply the tokens to the NEW content the user actually needs (their subject, their text, their images). Then run design-critique: the borrowed GRAMMAR with new WORDS should still pass every lens on its own merits.

## Rules
- Extract COMPUTED values, not guesses — browser_eval and getComputedStyle when the reference is live; pixel-measure screenshots when not.
- NEVER copy literal assets, logos, illustrations, icon sets, or long copy from the reference — roles, ratios, and rhythm only. Originality of CONTENT is non-negotiable (audit-reference originality instinct).
- Name divergences: when your subject needs something the reference lacks (an error state, an RTL flow), EXTEND the system in its own grammar and note it in the file.
- If the user gives TWO conflicting references, surface the conflict and pick per-aspect («هيكل X مع طباعة Y») — with a sentence of reasoning, before building.

## Done when
A written token file exists in the project, the new build visibly follows it (spot-check: three random components match the declared scales), and the delivery names what was extracted vs. what was consciously diverged.
