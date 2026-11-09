---
name: awwwards-site-quality
description: The award-grade method: a subject-obsessed concept, one signature gesture, section beat rhythm, editorial craft, and a walked-through ship loop.
category: frontend-craft
---

# awwwards-site-quality — القاعدة: الصحيح لا يكفي، المميز هو المطلوب

Award-grade sites are not "more decoration". They are a SUBJECT-obsessed concept, one signature gesture, editorial-grade craft, and zero dead sections. Load this whenever the ask is a SITE (موقع شركة / معرض أعمال / منتج / حملة) — not a small tool — and the ambition is «شيء يبهر»، «احترافي جداً»، «مستوى عالمي».

## Phase 0 — Read the composing skills first
skill_read frontend-design (the token discipline + anti-stamp checklist), then design-critique (your final gate). This pack ADDS the site-level bar on top of those foundations.

## Phase 1 — The concept: steal from the SUBJECT, not from design trends

Write one paragraph naming:
1. The subject's OWN visual world — its era, materials, documents, instruments, light. (A coffee roastery: burlap, kraft paper, roast curves, morning side-light, sack stamps. A fintech API: terminals, request logs, monospace grids, latency numbers.)
2. The ONE sentence the visitor must leave with.
3. The feeling word (ثقة؟ شهية؟ دقة؟ هيبة؟).
Every later decision — palette, type, motion, imagery — must trace back to this paragraph or it is costume. THIS is the step machine-built sites skip, and why they all look alike.

## Phase 2 — The signature gesture

Choose ONE memorable move the site owns end-to-end, born from the concept:
- a typographic system where the subject's REAL artifacts become the type (roast data as hero; the code as the interface)
- a scroll narrative with one continuous spatial idea (see scroll-storytelling)
- a hero built as a living WebGL object of the subject (see webgl-hero-object / webgl-backgrounds)
- an editorial grid whose STRUCTURE diagrams the subject (a newspaper-like index for a magazine; a specimen sheet for a type foundry)
Write the gesture as one sentence in your plan. If it could be pasted onto ANY other site unchanged, it is not a signature — try again.

## Phase 3 — Section rhythm (the boring secret of great sites)

Great sites alternate TENSION and RELEASE in blocks. Sketch the sequence as beats:

    1 HERO        — the signature gesture lands the feeling instantly (≤3s)
    2 PROOF       — one line of credibility under the fold's first breath
    3 STORY I     — the subject told with mass (image-led, few words)
    4 DETAIL      — zoom-in beat: the craft close-up, interactive spec
    5 REST        — a quiet wide section (statement type on calm ground)
    6 STORY II    — second act with a DIFFERENT layout than Story I
    7 CTA         — full-bleed decision moment, one action, huge type
    (repeat/extend per content; never two same-layout sections adjacent)

Every section gets: a job (one sentence), a dominant element, and a LENGTH reason. Sections that fail «ماذا يتغير لو حذفناه؟» are cut, not styled.

## Phase 4 — Editorial craft bar

- TYPE: display face chosen FOR the subject, set BIG (hero comfortably 5–9vw), tight leading on headlines, real typographic detail (optical sizes, hanging quotes in Arabic pull-quotes, tabular numerals in data).
- IMAGERY: one consistent treatment policy across ALL images (same ratio family, same grade/treatment, same overlay) — consistency is what reads as "curated". For subjects with no photos: draw it (CSS/SVG artifacts from the subject) or use type-as-image mass instead of stock filler.
- ARABIC/RTL when the audience is Arabic: dir=rtl from line one, an Arabic display face that actually exists in heavy weights, numerals policy fixed, mirrored directionality tested (see frontend-design step 4).
- MOTION: one choreographed entrance (staggered words or a curtain lift), scroll reveals that are FAST and purposeful, one interactive flourish max (see motion-systems). Nothing idles, nothing parades.

## Phase 5 — Ship loop (the non-negotiable)

1. Build. 2. browser_open (file or forge-preview://) — WALK the whole scroll yourself with browser_scroll. 3. browser_screenshot hero + each section + 360px mobile. 4. design-critique the shots (all seven lenses). 5. Fix, re-shoot. 6. Ship with the shots and a one-line naming of the concept («الاتجاه: معرض تحميص هادئ — الضوء الجانبي والكرافت وخط بيانات التحميص»).

## Rules
- Trends are banned as STARTING points (glassmorphism/dark-acid/brutalism «because they're in») — allowed only when the SUBJECT's paragraph independently arrives there.
- Performance floor: the wow must ship inside a fast page (see motion-performance) — a beautiful janky site loses the award and the user.
- Originality audit before delivery: zero literal assets, layouts, or copy lifted from any real site the user showed you (see reference-analysis for the honest way to learn from references).
- One signature gesture, not five.

## Done when
The concept paragraph, the named gesture, and the beat map exist in your notes; the walked-through site passes design-critique at desktop AND 360px; and a stranger testing it for 10 seconds can repeat your one sentence back.
