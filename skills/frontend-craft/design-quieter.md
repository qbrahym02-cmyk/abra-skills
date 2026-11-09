---
name: design-quieter
description: Subtract visual noise: budget attention-callers to three per viewport, gray the non-essential ink, let whitespace do the luxury work.
category: frontend-craft
---

# design-quieter — صهّت حتى يُسمع الجوهر

When a design is LOUD and tired — too many gradients, badges, borders, icons, shadows, animations competing — the fix is subtraction. Load this when the user says مرتاح أكثر / نظيف أكثر / فيه زحمة / مبالغ فيه, or your critique counted five things fighting per viewport. Quieter is not empty; it is EVERYTHING REMOVED EXCEPT THE MEANING.

## The quieting pass — in order of yield

1. COUNT the attention-callers per viewport: borders, colored fills, badges, icons, gradients, shadows, animations, ALL-CAPS labels, numbers-as-decoration. Write the number. Set a budget of 3. Cut from the top of the list until you meet it.
2. GRAY THE SPECTRUM: push every non-essential ink toward the background (a 3-step ink ramp: ink / 60% ink / 35% ink). Most text on most pages should be quiet ink; the LOUD 5% (the primary action, the key number) keeps full contrast. Contrast is a BUDGET you spend, not a default.
3. FLATTEN competing surfaces: two neighboring cards both with shadow+border+radius+hover-glow? Choose ONE differentiator (border only) and let grouping do the rest. When everything is emphasized, nothing is.
4. RETIRE decorative gradients and glows — keep gradient ONLY where it represents data or a real light source. Replace decorative washes with a flat tint of your ground one step off.
5. SHRINK the furniture: chrome (navs, footers, filter bars) drops to small sizes and quiet ink — CONTENT gets the mass and the contrast. Navigation should be findable, not famous.
6. SLOW the motion: durations up (240→400ms), easings softened, parallax reduced or removed, stagger delays compressed (long stagger parades read as noise). One entrance, choreographed.
7. SPACE as the luxury: double the whitespace around the hero content before touching anything else — expensive emptiness IS the quiet luxury signal. Then verify hierarchy still reads (quiet must not become FLAT).

## The traps

- Quiet ≠ gray mush: if after quieting the page has NO full-contrast moment, you over-did it — restore one LOUD point (the CTA, the headline, the key number).
- Quiet ≠ unfinished: alignment and states still perfect (visual-polish still runs after).
- Do not remove MEANING: a status color, an error red, a chart legend are information — noise is decoration competing with information. If removing it loses information, RESTYLE it quieter (smaller dot, thinner border) instead of deleting it.
- Arabic body text needs its line-height room even in a tight quiet layout — compressing leading to «look minimal» breaks diacritics.

## Method
1. Screenshot before. Count attention-callers.
2. Apply passes 1–7. Screenshot after.
3. Squint test: blur your eyes at the after shot — does the ONE key action/element still pop? If no, restore its contrast. If yes, ship.
4. Offer the user the before/after pair.

## Done when
Per viewport there are ≤3 attention-callers, exactly ONE full-contrast moment exists, the squint test passes, and the page still passes design-critique.
