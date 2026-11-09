---
name: visual-polish
description: The final 5% that separates designed from generated: pixel discipline, the four interactive states, edge and surface craft, type final pass.
category: frontend-craft
---

# visual-polish — آخر 5% التي تصنع كل الفرق

Polish is not decoration — it is consistency at the pixel level. Load this AFTER the layout and hierarchy are right (design-critique passes) and BEFORE you hand anything over. A page can be structurally correct and still feel cheap; this pass is why.

## The checklist — run it top to bottom, fix as you go

### 1. Pixel discipline
- Vertical rhythm: margins/paddings snapped to the token scale you declared (8/16/24/32…). Replace any leftover odd value.
- Icon–text alignment: icons optically centered against their label (optical > mathematical — a play triangle needs a nudge).
- Truncation policy decided per text slot: ellipsis with title attr, clamp to N lines, or wrap? Never accidental overflow.
- Longest-realistic-data check: put the longest realistic string in every dynamic slot (Arabic names are long; emails are longer) and re-screenshot.

### 2. The interactive states that "cheap" work forgets
Every interactive element gets FOUR looks, styled deliberately:
- rest (default)
- hover (feedback within 100ms — color shift ≥ visible step, or 1px lift, or underline; something)
- focus-visible (a REAL ring: 2px offset outline in ink or accent — never removed, never left default-blue where it clashes)
- disabled (muted AND cursor:not-allowed, not just opacity 0.4 on everything)
Plus active/pressed (scale .98 or darkened one step) for primary buttons. Write these once in your token layer, not per-component.

### 3. Edges and surfaces
- One corner-radius policy across the page — the day a 6px card sits next to a 10px chip is the day it looks assembled, not designed.
- Border weights consistent (1px hairline OR 1.5px, not a mix).
- Shadows: layered soft shadows (2 stacked: tight dark + wide faint) beat one harsh blob. Shadows imply ONE light source for the whole page — check direction consistency across cards/popovers.
- Images: object-fit + a background placeholder color so a slow image never shoves layout; alt text present.

### 4. Type final pass
- Line lengths: 45–75 characters for body (Arabic tolerates slightly less).
- Orphans/ampersands: no single word on the last line of a heading — adjust width or wording.
- Numerals in tables aligned (tabular-nums) — ragged numerals read as broken.
- Arabic: line-height 1.7–2.0 body, kashida off in UI labels, diacritics not clipped at cap-height.

### 5. Motion polish (if motion exists)
- Durations from a 3-step scale (120/240/400ms), one easing family everywhere.
- prefers-reduced-motion honored — the check is two lines and its absence is a flaw.

### 6. The delivery look
browser_screenshot one full-page shot at desktop AND one at 360px wide. If the mobile shot breaks anything, that is not polish, that is a blocker — go back.

## Rules
- Polish AFTER structure; polishing a broken layout is perfuming a fish.
- Never introduce a NEW color/font/effect in this pass — polish means perfecting the system you chose, not changing it (use design-bolder / design-quieter for that).
- Budget: this pass should cost minutes, not hours. If it wants hours, the earlier phases were skipped — go fix those.

## Done when
Every checkbox above is either true or consciously waived in the delivery note, and the two screenshots (desktop + 360px) are attached as evidence.
