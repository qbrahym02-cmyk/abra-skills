---
name: landing-page-craft
description: Persuasion engineering for landing pages: a 5-second fold, a doubt-ladder section sequence, and exactly one primary action.
category: frontend-craft
---

# landing-page-craft — صفحة تُصنع ليتخذ زائرها قراراً

A landing page has ONE job: move a specific visitor from «سمعت به» إلى فعل واحد (تسجيل، شراء، تواصل). Load this whenever the deliverable is صفحة هبوط / صفحة تسويقية / صفحة منتج — and treat it as persuasion engineering, not layout assembly. (For pricing sections specifically, also skill_read pricing-page-craft; for general quality, design-critique at the end.)

## Step 1 — The conversion brief (answer before any design)

- WHO lands here, from WHERE (an ad? a recommendation? a search?) — arrival context sets their patience (ad traffic: 5 seconds, no mercy).
- The ONE action this page exists for. Exactly one primary CTA; a secondary text-link at most.
- The visitor's current DOUBT (هل يعمل مع حالتي؟ هل يستحق؟ هل يثق بهم؟) — the page's sections are ordered to KILL that doubt in the visitor's own asking order.

## Step 2 — The 5-second fold (above the line)

The fold must answer, in one glance: ما هذا + لمن + الفعل. Craft:
- HEADLINE = the outcome in the visitor's language («اكتشف تسريبات المبيعات قبل نهاية الشهر» — not «حلول تحليلات متقدمة»). One line. Subject-verb-object. Arabic: full natural sentence, not clipped keywords.
- SUBHEAD: one line adding the how/for-whom the headline implied.
- PRIMARY CTA: a button whose label is the VERB of the outcome («ابدأ التتبع مجاناً»), visually the single loudest element in the viewport (the only full-saturation spot — see design-quieter's contrast budget).
- PROOF SPARK: one credential near the CTA (logo strip / number / rating) — small, quiet, instant.
- VISUAL: the product's REAL face (screenshot, the artifact itself, or the signature object — see webgl-hero-object) — not an abstract stock illustration of "teamwork".

## Step 3 — The persuasion sequence (below the fold)

Ordered by the visitor's doubt ladder, each section ONE idea with ONE job:
1. THE MECHANISM — how it actually works (3 steps max, numbered honestly, with the real interface or artifact shown).
2. THE DIFFERENCE — why this and not the alternative (feature-as-benefit table or a sharp before/after — NOT a 12-item feature dump; three differences that MATTER beat twelve that don't).
3. THE PROOF — social proof with SPECIFICS («خفّضنا زمن الرد من 6 ساعات إلى 40 دقيقة في متجر X») — vague quotes with initials are worth nothing; numbers and named cases are.
4. THE OBJECTION KILLER — the visitor's real hesitation answered head-on (سعر؟ خصوصية؟ تعقيد؟ الفصل العربي للأسعار والتواصل إن كان الجمهور عربياً).
5. THE DECISION — the CTA repeated with reduced friction (قائمة فارغة تُطلب فيها فقط البريد، لا نموذج من 8 حقول) + final reassurance line underneath (ضمان/إلغاء/لا بطاقة).

## Craft rules

- EVERY section ends in the visitor's mind answering «وماذا يخصني؟» — cut any section written for the CLIENT's pride (founder's philosophy paragraphs die here).
- Consistent CTA identity: same label, same color, same shape every appearance — recognition compounds.
- White space is confidence; a landing page that SCREAMS everything converts nothing.
- RTL: the reading sequence (and any step-arrows, progress metaphors) mirrored; the CTA verb leading from the RIGHT.
- Test the fold at 360×640 — the majority of Arab-region landing traffic is mobile; if the fold buries the CTA under an image on mobile, you lost the page's purpose on most visitors.

## Ship loop

browser_open → browser_scroll the full page → read it as the DOUBTING VISITOR, not the proud builder («هل أقنعني هذا القسم؟ أم أرى مجرد شكل جميل؟») → browser_screenshot fold + one proof + CTA + mobile fold → design-critique pass → fix → attach shots.

## Done when
A stranger reading only the headline+CTA can say what to do and why; every section survives «ما الشك الذي يقتله؟»; the page passes design-critique at desktop and 360px; and the primary CTA is the single loudest element on every viewport it appears in.
