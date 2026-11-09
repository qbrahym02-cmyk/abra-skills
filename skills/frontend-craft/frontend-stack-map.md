---
name: frontend-stack-map
description: Choose the delivery lane honestly (zero-build / Vite / Next), pin CDN versions, and treat component libraries as idea catalogs, not personality.
category: frontend-craft
---

# frontend-stack-map — اختر العدة بمنطق المهمة، لا بمنطق الموضة

Before writing frontend code, choose the stack DELIBERATELY. This pack is the decision map for THIS engine's reality: single-machine delivery, files the user opens directly, no assumption of cloud deploys, and an Arabic-first audience. Wrong stack choice is why projects die at «شغّلته عند المستخدم ولم يعمل».

## The engine's three delivery lanes (choose per project, say it in the plan)

1. ZERO-BUILD LANE (the default for most Abra deliverables): plain HTML + CSS + JS, or React via CDN + Babel-standalone for genuinely component-heavy pages. Runs from a double-click, offline, forever. Choose it for: landing pages, portfolios, small apps, tools, prototypes the user must open NOW. Libraries via CDN with a real pinned version; the page must still RENDER something honest offline (progressive enhancement — no blank white void without network).
2. VITE LANE: when the project is large-and-long-lived (real SPA, many components, TS demanded): scaffold with Vite (run_command npm create vite@latest), dev via npm run dev (background:true, then shell_output for the URL), ship dist/ after npm run build. Say the build requirement to the user in the delivery.
3. NEXT LANE: only when the project genuinely needs SSR/SEO-heavy marketing + app in one (rare on a desktop agent): scaffold via run_command, run on localhost, be explicit about what hosting it eventually needs — never deliver a Next project silently when the user expects a file they can open.

Decide the lane OUT LOUD in phase 2 of the method (it is an "الأدوات" line in todo_write). When ambiguous: zero-build until the user names a scaling/server need.

## The component-library reality check

Ready-made component sets are CATALOGS OF IDEAS and accelerators, not a personality:
- shadcn/ui (Tailwind + Radix primitives, copy-into-project) — the serious baseline when you're in a React/Vite/Next lane: accessible primitives, you own the code, theme via tokens.
- Radix UI / React Aria — the a11y primitive layer underneath; use directly when you need behavior without the styling opinion.
- Aceternity UI / Magic UI / Cult UI / Origin UI / React Bits / 21st.dev — moving-parts flourishes (spotlights, aurora, border beams, tilt cards). Use as REFERENCE for one signature moment (awwwards-site-quality phase 2), read HOW they do it, then ADAPT to the project's tokens and RTL. Pasting three of their demos onto one page produces the exact same «AI site» everybody recognizes — and their components are LTR-first: mirror-test everything directional in RTL.
- Rules: never mix two component systems in one project; a pasted component must be re-tuned to the project's radius/ink/type tokens before it counts as used; and in the ZERO-BUILD lane prefer writing the 30 lines yourself over pulling a framework for one widget.

## Tailwind — yes, but as a token system

Tailwind (CDN or build) is welcome — but configure it AS the design system (frontend-design step 2): custom colors as named tokens, fontFamily as the two chosen faces, spacing on the base unit. Utility-soup without a token layer is how the "stamped" look happens. In zero-build: the CDN play-script with a tailwind.config inline is legitimate for medium pages; for tiny ones, plain CSS with custom properties is cleaner and faster.

## Version honesty (the anti-rot rule)

Every CDN script tag carries a PINNED version (never @latest), chosen from what you can verify (web_read the library's release notes when unsure — no invented APIs). When using a library whose API you may misremember (Three.js, GSAP, D3), open its CURRENT docs with web_read BEFORE writing the integration — a half-remembered API is the top cause of broken first runs.

## TypeScript

In the Vite/Next lanes: TypeScript on (types catch the agent's own mistakes). In the zero-build lane: plain JS + JSDoc comments — do not fake types via CDN hacks.

## Decision snippet (how the plan should read)

    المسار: zero-build (ملف واحد يفتح مباشرة)
    الواجهة: React 18 (CDN، مثبّت) + Babel standalone — 7 مكوّنات متكررة
    التصميم: Tailwind CDN مع tokens مخصصة + shadcn كمرجع للأزرار/البطاقات فقط
    3D: Three.js r### (CDN مثبّت) — منحنى تعلم مقبول للطلب

## Done when
The lane and each library were CHOSEN (and written in the plan) before the first code line; every dependency is version-pinned and actually loads (browser_open + browser_eval a library presence check, e.g. !!(window.THREE || window.gsap)); and the delivered artifact runs in the lane you declared — verified in the agent browser before handover.
