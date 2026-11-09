---
name: scroll-storytelling
description: Turn scroll into a timeline: a 3–5 beat storyboard, one pinned container, scrubbed progress, clean beat hand-offs, mobile fallback.
category: frontend-craft
---

# scroll-storytelling — القصة يقرؤها الإصبع

The visitor's scroll becomes the film's timeline: each pixel of scroll advances a scripted visual story (a product's anatomy, a process, a journey). Load this for «قصة بالتمرير»، «سينمائي مع السكرول»، «المشاهد تتغير أثناء النزول». It rides ON motion-systems (load it first — the clock, the easing family) and composes with threejs-worlds for camera journeys.

## Step 1 — Storyboard before code (the beat sheet)

Write the beats as scroll ranges:

    0–10%  HOOK:   full-viewport pinned scene, title set, world visible
    10–35% BEAT 1: the subject assembles / camera pushes in — text 1 fades
    35–60% BEAT 2: second angle or exploded layer — text 2
    60–85% BEAT 3: the payoff moment (everything connects / the reveal)
    85–100% REST → release the pin, normal document flows again (CTA)

Rules for beats: 3–5 beats max (beyond 5 nobody remembers); each beat has ONE sentence of text (not paragraphs — the visuals speak); the LAST beat always resolves tension before the release (a story that ends mid-scene exhausts).

## Step 2 — The pinning mechanics (GSAP ScrollTrigger, pinned correctly)

- ONE pinned container per story (multiple overlapping pins = the classic scroll-jail bug). Pin the SECTION, animate INSIDE it.
- Progress mapping: scrub: 0.5–1 (a half-second of smoothing — raw scrub feels twitchy, scrub:2 feels drunk); animate transforms/opacity only.
- Text beats: fade+rise in at their range, fade OUT at the next beat's start — beats hand off cleanly instead of stacking.
- Camera/3D journeys: map progress to the path t (threejs-worlds phase 4) — the SAME smoothed value drives DOM and canvas (one source of truth, no fighting).
- A thin progress indicator (a growing line on the edge / step dots) when the story exceeds 2 viewports — orientation is kindness. RTL: progress fills right→left.

## Step 3 — The scroll FEEL (when the story deserves polish)

Lenis-style smooth scrolling (CDN pinned, or ~40 lines of lerp yourself) ONLY for story pages — never on content/admin pages where users scroll to FIND, not to FEEL. Wire it as the single scroll source (ScrollTrigger.update on its rAF). Keep native scrollbar behavior (no hijacked wheel multipliers > 1.2 — hijacked scroll is how demos become unusable).

## Step 4 — The performance contract

- Pinning creates large fixed surfaces: the story section's content must be composited (transform/opacity), never layout-animating.
- Off-screen beats: elements not yet reached stay will-change: auto (set will-change only DURING their active range — permanent will-change on 30 elements is a memory leak).
- Mobile: pinning on touch is fragile — EITHER ship a simplified alternate (beats as stacked snap-scroll sections with the same content) OR test carefully; never let the mobile story pin-jitter. Decide explicitly, say it in the delivery.
- prefers-reduced-motion: the full story still READS — beats become instantly-visible stacked sections (scroll-snap optional), nothing hidden.

## Step 5 — Verify (walk it like a viewer, not a builder)

browser_open → browser_scroll slowly through the WHOLE story → browser_screenshot each beat's hold moment (5 shots) → check: does each beat hand off cleanly? any flash of unstyled elements mid-scrub? does the pin release exactly at 85–100% with no jump? → scroll back UP (reverse behavior sane?) → fast flick scroll (smoothing absorbs it?) → 360px if mobile story shipped → fix → re-shoot.

## Done when
The beat sheet exists (and matches what ships); each beat tells its one sentence visually; hand-offs are clean in both scroll directions; the pin releases without a jump; the mobile path is deliberate; and the five beat screenshots are attached.
