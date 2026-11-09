---
name: pricing-page-craft
description: Pricing as decision engineering: honest plan anatomy, a recommended plan with a reason, trust furniture, and zero dark patterns.
category: frontend-craft
---

# pricing-page-craft — اسأَل عن قرار المال بوضوح وكرامة

Pricing is a DECISION page: the visitor is already interested — your job is to make choosing EASY and trusting the number HONEST. Load this for any صفحة أسعار / باقات / خطط / اشتراكات section. Design quality still ends with design-critique; this pack handles the decision engineering.

## Step 1 — Decide the pricing MODEL before the layout

With the user's plan list in hand, name: the AXIS of the plans (by size? by feature? by audience?) — one axis only; the VALUE METRIC the customer understands (مستخدم؟ رافع؟ طلب؟) written in the customer's unit, not the internal one; and the plan COUNT (2–4; past 4 nobody reads — collapse the rest into «مخصص/Enterprise» as a quiet contact line, not a fake card).

## Step 2 — Card anatomy (per plan, honest)

- PLAN NAME: names that SELF-DESCRIBE the audience («للمتاجر الفردية» يتفوق على «الباقة الفضية» — silver/gold/platinum hierarchies say nothing about fit).
- PRICE + its unit rhythm stated in full (الشهر، تُدفع سنوياً) — toggle monthly/annual if both exist, with the annual saving shown as a number («وفّر 20%»), never hidden arithmetic.
- 4–7 line items MAX: the few differences the buyer actually weighs. Feature-parity clutter («كل شيء في الأساسي…») is noise — show the DELTA and link a full comparison table below for the rare auditor.
- ONE plan-level CTA with a verb matching commitment weight («ابدأ مجاناً» للدخول، «اختر» للمتوسط، «تواصل معنا» للمؤسسات — never «اشترك الآن» on all four).
- The recommended plan: visually RAISED (border weight or full accent frame), a label with a REASON («الأكثر اختياراً لمتاجر مثلك») — never «الأكثر شعبية» without specifics; and if you can, its price anchored BETWEEN neighbors so the middle looks reasonable.

## Step 3 — The trust furniture around the cards

- A slim comparison TABLE below the cards for the detail-minded (≤6 rows visible; the rest behind a details toggle), tabular-nums aligned columns, identical row heights.
- The FAQ kills the MONEY doubts specifically: ماذا يحدث لو تجاوزت الحد؟ هل أستطيع الإلغاء؟ ما طرق الدفع للمنطقة؟ (Arabic audience: regional payment reality — specify what the user actually supports, never invent.)
- A quiet footer line for: refund policy, VAT treatment (المنطقة العربية: الضريبة تُذكر بوضوح لا في صفحة أخرى), currencies offered.
- NO dark patterns: fake countdowns, «أقرب عرض ينتهي بعد 9:59»، pre-checked add-ons — these convert once and rot the brand forever. Honest urgency only (عرض الإطلاق حقيقي بتاريخ معلن أو لا يكون).

## Step 4 — Layout craft

- Cards equal height, the recommended one PHYSICALLY taller/raised (elevation or scale), aligned tops for the price row across all cards (ragged price lines read as sloppiness at the exact moment of trust).
- Annual/monthly toggle: the switch itself animates (micro-delight) and BOTH prices update clearly.
- On mobile (test 360px): cards stack with the RECOMMENDED first, the table collapses to per-plan accordions.
- RTL: plan order mirrored so the recommended/most-popular sits where the eye lands FIRST (right side), comparison arrows mirrored.

## Ship loop

browser_open → browser_scroll → read as a BUYER comparing two plans: «أعرف خلال 10 ثوان أي واحد لي؟» → browser_screenshot cards + table + 360px stack → design-critique → fix → attach shots.

## Done when
A target visitor picks a plan in <15 seconds without scrolling twice, every number on the page is one the user actually confirmed (no invented prices — if unknown, ask_user once and fill exactly), the recommended plan states its reason, and the page contains zero dark patterns.
