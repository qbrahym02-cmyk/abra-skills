---
name: text-motion-reveal
description: Headline choreography: masked word staggers (Arabic-safe splitting on spaces), line reveals, clip wipes, scrub highlights, seamless marquees.
category: frontend-craft
---

# text-motion-reveal — الكلمة تدخل كما تدخل الممثلة: في لحظتها

Text is the page's voice — HOW it arrives matters as much as what it says. Load this for any headline/section-title motion: staggered word reveals, masked line reveals, character cascades, marquee strips, scroll-scrubbed word highlights. Rides on motion-systems (the declared language). The trap it exists to kill: the generic "fade-in-up-everything" parade that makes every AI page look identical.

## The reveal vocabulary (choose per role, one family per page)

1. WORD STAGGER (the workhorse): split headline into word spans; translateY 110%→0 inside an overflow:hidden line box (the MASK is what makes it feel premium — words arrive FROM somewhere), stagger 40–60ms, ease-out-quint, 400–600ms each. Arabic: split on SPACES ONLY (never characters — connected script!), and keep each word intact inside its mask (letter-spacing/kashida must not clip).
2. LINE REVEAL: paragraphs split by line (measure client rects, wrap) — lines rise 24px + fade, stagger 80ms. For body copy this beats word-level (readers scan lines, not letters).
3. CLIP REVEAL: a solid ink-colored panel wipes (scaleX origin-RTL-aware) revealing the word beneath — editorial, works beautifully in Arabic display type. One per page max.
4. SCRUB HIGHLIGHT (scroll-tied): words of a long statement start at 30% ink opacity; as scroll progress crosses each word's offset, it fills to 100% (the «reading karaoke» effect) — scrubs beautifully with ScrollTrigger or view-timeline CSS. Use for manifesto/mission text, one per site.
5. MARQUEE (the honest kind): infinite loop strip for logos/keywords — duplicate the track, animate translateX with the EXACT track half-width loop (measure after fonts load!), linear, 20–40s, pause on hover when items are interactive, and RTL runs the mirrored direction. A marquee with a visible seam restart is worse than no marquee.

## Craft rules

- ONE family per page (all word-stagger OR all line-reveal…); mixing three reveal styles in one viewport is the noise this pack exists to prevent.
- Reserve the STRONGEST treatment for the hero headline; section titles get the QUIETER sibling (half the distance, half the duration).
- SPLIT SAFELY: build spans in JS at load (never hand-authored markup), preserve inter-word spaces, and re-split on resize when the wrap changes (debounced). Test the LONGEST realistic Arabic line — a mask that clips a descender (ـي، ـج) is a broken build, not a style.
- Fonts must LOAD before measuring (document.fonts.ready gate) — measuring with the fallback face then animating with the real one is the classic 1-frame jump.
- Accessibility: the pre-split text stays in the DOM semantics (aria-label the original on the container, spans aria-hidden) — screen readers read the SENTENCE, not "word… word… word".
- prefers-reduced-motion: reveals become instant (opacity only), marquee holds a static row.

## Verify

browser_open → browser_screenshot mid-reveal (stagger visible, masks clipping correctly?) → browser_scroll to a scrub-highlight section and screenshot at 30%/60% progress (words filling in order?) → check the marquee across a 15-second browser_wait for seam-jump → longest-Arabic-line check → 360px (re-split reflowed?) → fix → re-shoot.

## Done when
One declared reveal family ships across the page; the hero moment is the strongest; the Arabic longest line clips nothing; the split is semantic and resize-safe; the marquee (if any) has no seam; and the mid-reveal + scrub screenshots are attached.
