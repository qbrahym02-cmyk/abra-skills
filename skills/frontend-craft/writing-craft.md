---
name: writing-craft
description: Write with purpose: the one-outcome brief, structure before prose, the harsh deletion pass, and tone calibrated to the reader.
category: frontend-craft
---

# writing-craft — اكتب بغرض، لا بكمّ

Load this for ANY writing deliverable: reports, articles, documentation, essays, announcements, scripts, UI copy — whenever the OUTPUT is words (for Arabic-specific typography and voice, pair with arabic-content). The method kills the three failure modes of generated writing: padding, structure-less drift, and tone-deafness.

## Phase 1 — The brief (answer before the first sentence)

- WHO reads it, in WHAT MOMENT (a CEO skimming on a phone? an engineer following steps hands-on? a customer deciding whether to trust?), and what they ALREADY know.
- The ONE outcome: after reading, the reader does/thinks/decides WHAT? Write it as one sentence — it is the ruler every paragraph is measured against.
- The MEDIUM and its physics: a chat message (3 lines max), a report (scannable structure), documentation (findable, stepwise), an announcement (one idea, strong verbs).
- Length from CONTENT, never from ambition: the brief names what MUST be covered; length = that content at its natural density. Empty sections are deleted, not filled.

## Phase 2 — Structure before prose

- Sketch the skeleton as headings/bullets ONLY (a reader of JUST the skeleton should get the argument). For documents: خلاصة (the answer/executive summary — 3–5 lines) FIRST, then the body in the reader's question order, then «الخطوات التالية» if actionable.
- One idea per paragraph; paragraphs 3–5 sentences; transitions that name the LOGIC («لهذا السبب»، «النتيجة العملية») not the geography («الآن سنتحدث عن»).
- Lists: parallel grammar, ordered by importance or chronology (never randomly), each item survivable alone. No list where a sentence is stronger.

## Phase 3 — The draft, then the HARSH pass

Draft fast, then edit like an enemy:
- Delete every sentence that survives the question «ماذا يفقد القارئ لو حذفتها؟» (answer: nothing → delete). Filler openings («في عالم اليوم»، «تعتبر X من أهم»), hedging clouds, summary-of-what-you-just-said closers — first against the wall.
- Prefer concrete over abstract: numbers, names, dates, mechanisms — «خفّض زمن الرد من 6 ساعات إلى 40 دقيقة» beats «تحسين كبير في الكفاءة». Where a number is unknown: say unknown, never invent (accuracy rules are absolute).
- Verbs carry the weight: active voice, subjects that act; nominalizations («القيام بتنفيذ») → verbs («نفّذ»).
- TONE calibration per brief: warm-direct (user-facing), precise-neutral (reports), plain-imperative (docs). One tone per document — shifts read as stitched.

## Phase 4 — The language realities

- Language of the USER (engine rule): Arabic request → Arabic deliverable, English → English; technical terms keep their working form (API, deployment) untranslated where the audience uses them untranslated.
- Arabic craft: natural sentence order, connected logic, real punctuation (،؛.) — not translated-English stiffness; numbers contextualized; when mixed-direction text appears (an English term inside Arabic), check rendering order, isolate LTR runs with dir spans in HTML outputs.
- English craft: consistent tense per section, defined acronyms on first use, no orphan "this" pointing at nothing.
- NEVER end documents with «وفي الختام» filler closers — a strong final substantive line (or the next steps) is the ending.

## Phase 5 — The delivery check

Re-read the whole thing AS THE READER (not the author): does the خلاصة answer the brief's outcome sentence? Is the strongest point where the skimmer will find it? Any paragraph whose removal loses nothing? Any claim without a basis? Then ship — with sources cited when facts were used (web_read URLs), and unknowns named as unknowns.

## Done when
The brief's outcome sentence, the skeleton, and the harsh-pass all happened (in that order); the piece carries zero filler sentences and zero invented facts; the tone is singular and reader-calibrated; and a skim of ONLY the headings + خلاصة delivers the core of the message.
