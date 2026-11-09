---
name: reference-analysis
description: Learn from references honestly: capture evidence, extract an explicit directive, build an original, and pass the side-by-side originality audit.
category: frontend-craft
---

# reference-analysis — تعلّم من المرجع دون أن تنسخه

When the user shows you SOMETHING to learn from — «أعجبني هذا الموقع»، «خذ روح هذا الفيديو»، «مثل صفحة X لكن لمطعمنا» — your job is two moves: ANALYZE it into an explicit design directive, then BUILD an original that passes an originality audit. Load this whenever a reference (URL, HTML file, screenshots, a screen recording) enters the conversation.

## Phase 1 — Capture the evidence properly

- LIVE SITE: browser_open the URL → browser_read (structure + copy patterns) → browser_screenshot the hero, one content section, one interactive state, and a 360px frame → for interaction details, browser_scroll through and note WHAT MOVES and WHEN (the interaction grammar is half the reference's quality).
- HTML FILE (uploads/ or project): read_file for structure, browser_open for the living rendering, both screenshots and the actual CSS values.
- VIDEO / SCREEN RECORDING: describe its beats from playback (if the engine can preview it) or ask the user for the 3 moments they loved — never fake analysis you did not see.
- SCREENSHOTS: read what is IN them; do not hallucinate what is plausibly around the edges.

## Phase 2 — The directive extraction (turn looking into writing)

Produce a written SUPERPROMPT — the reference reduced to explicit, buildable instructions (this becomes the brief for the new build):

    SUBJECT FIT    : what this reference's grammar would mean for OUR subject
    STRUCTURE      : layout skeleton, section rhythm, container policy
    SYSTEM         : palette roles + ratios, type scale + setting, space unit,
                     radius/border/shadow policy  (→ design-system-extraction
                     values, measured not guessed)
    MOTION GRAMMAR : what animates, what triggers it, durations/feel, what
                     stays STILL (the stillness is a choice too)
    SIGNATURE      : the 1–2 moves that make this reference memorable —
                     stated as mechanism, not as pixels
    WHAT WE DON'T TAKE: the parts tied to THEIR brand/subject, not ours

Measure where you can (browser_eval getComputedStyle on the live page for real font sizes, colors, gaps — numbers, not impressions). The directive is INVENTORY, not yet a plan.

## Phase 3 — The original build (where copying dies)

- Run the directive THROUGH the new subject (awwwards-site-quality phase 1): the reference's GRAMMAR with OUR vocabulary — their grid discipline + our palette; their motion restraint + our artifacts. Where the two subjects genuinely differ, the NEW subject wins (a reference's dark-drama does not transplant onto a children's brand — note the divergence instead of forcing it).
- The signature moves are RE-EXPRESSED, not replicated: if theirs is «counter animates as you scroll», ours can be «the counter animates as you scroll with OUR unit and OUR rhythm» — mechanism shared, execution ours.
- ZERO transplant of: their copy, their logo/wordmark, their imagery/illustrations, their exact hero composition (same layout + same type + same colors = a copy even with different words), their icon set, their code.

## Phase 4 — The originality audit (before delivery)

Side-by-side the two screenshots (theirs, ours) and answer honestly:
1. Would the reference's designer recognize their WORK in ours? (grammar: probably yes — that is the homage) their EXPRESSION? (must be NO — layout-for-layout, line-for-line, or their exact signature reproduced verbatim = restart the diverging parts).
2. Three things ours does differently — named in the delivery.
3. If the user asked for «نفس الشيء بالضبط» for a LOOK they don't own: build the original-spirit version and say why (identity theft of design has the same failure mode as copied code — and their brand benefits from not being a clone).

## Done when
A written directive exists (with measured values), the build passes the audit's three questions, the side-by-side pair is attached, and the delivery names what was taken (grammar) vs. consciously diverged (expression).
