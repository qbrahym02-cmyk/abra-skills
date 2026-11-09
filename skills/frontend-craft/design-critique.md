---
name: design-critique
description: Run a seven-lens critique (hierarchy, alignment, contrast, rhythm, crowding, edge cases, RTL) on any interface before delivery, then fix what the shots reveal.
category: frontend-craft
---

# design-critique — انقد قبل أن تسلّم

You are your own harshest reviewer. Run this pass on ANY interface you built (or inherited) BEFORE calling it done — the difference between "generated" and "designed" is one honest critique loop.

## WHEN to load this
Before delivering any site, page, app shell, dashboard, or component set — and whenever the user says «التصميم سيئ» or asks لماذا يبدو عام/رديئاً. Also load it after finishing a frontend-design pass.

## The method — look, list, fix, re-look

1. OPEN AND SCREENSHOT: browser_open on the file (or forge-preview:// URL for the project), then browser_screenshot. Critique the SHOT, not your memory of the code — your memory is optimistic, pixels are not.
2. Read the shot against the seven lenses below. Write down every flaw you SEE, phrased concretely («العنوان والمقدمة بنفس الوزن فلا يعرف العين أين تذهب أولاً» — not «الهرمية ضعيفة»).
3. Rank the flaws: BLOCKERS (wrong/broken/clipped) before STRUCTURE (hierarchy, alignment) before TEXTURE (spacing, contrast) before CHARM (delight).
4. Fix the top 3–7 in one pass. Re-screenshot. Compare. Repeat until the shot survives the lenses.
5. Attach the final shot in your delivery — evidence, not claims.

## The seven lenses

- HIERARCHY: close your eyes, open them on the shot — where did the eye land FIRST? If the answer is «nowhere in particular», the hierarchy failed. One dominant element per viewport; everything else recedes in steps.
- ALIGNMENT: pick the left edge of the first three elements — do they share a line? Check center-lines of centered elements too. Misalignment of 2–3px reads as «آلة صنعته».
- CONTRAST: for the text pairs you ACTUALLY used — body ≥ 4.5:1, large headings ≥ 3:1. Then contrast of WEIGHT (are two neighboring elements really different, or the same size in different clothes?), of SIZE (real steps, not 16px vs 17px), and of COLOR (does the accent ACCENT anything or just decorate?).
- SPACING RHYTHM: spacing should come from your base unit's multiples (8/16/24/32…). Run your finger down the gaps — an unexplained 13px or 27px hole is a bug. Related things sit CLOSE together; unrelated things sit FAR apart — if everything is equidistant, grouping communicates nothing.
- CROWDING / NOISE: count the competing calls-to-attention per viewport (badges, borders, gradients, icons, animations). More than ~3 and the eye has no rest — cut until each survivor earns its place. Every decorative element must be answerable: what would we LOSE if deleted?
- EMPTY STATES & EDGE: zero-data screen, one-item list, longest possible text, Arabic string 40% longer than the English you styled for, 360px viewport, :focus ring, disabled button. Un-styled edges are where «سيئ» lives.
- RTL SPECIFICS (Arabic UIs): dir=rtl actually set; icons that mean direction (arrows, "next", progress) mirrored LOGICALLY not just positionally; numerals policy chosen once; no clipped diacritics at line-height < 1.6 for body.

## Output format to the user (and to yourself)

A short numbered list, each item: [lens] the flaw in one sentence → the fix in one sentence → done/not-done. No essay. Then the before/after shots if the conversation allows.

## Rules
- Critique the RENDERED page, never the source alone — CSS lies less than HTML but screenshots don't lie at all.
- Fix before philosophizing: a 10-minute fix beats a paragraph of justification.
- Never defend the flaw to yourself with «هذا أسلوب» — style is a REPEATED decision, not an accident.
- Cap: 2 critique cycles max, then ship with the honest list of what remains.

## Done when
The latest screenshot survives all seven lenses with no BLOCKERS and no STRUCTURE flaws, and the delivery names what you fixed — with the shot attached.
