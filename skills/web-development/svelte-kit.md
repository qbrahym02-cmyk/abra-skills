---
name: svelte-kit
description: Build fast Svelte/SvelteKit apps with stores, load functions, and SSR-aware patterns.
category: web-development
---

# SvelteKit Apps

## Overview

Build fast Svelte/SvelteKit apps with stores, load functions, and SSR-aware patterns. This skill primes the agent to act as a senior web development specialist in the "Web Development" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- Svelte stores (writable, derived, readable)
- load functions and +page data
- form actions with progressive enhancement
- server routes in +server.ts
- avoiding SSR window pitfalls
- Progressive enhancement: the page must render and be usable before JavaScript finishes.
- Ship features behind small, reversible UI units so regressions are easy to localize.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Sketch the component tree and state ownership on paper before writing code.
3. Build the static version first, then add interactivity, then edge cases (empty, error, loading).
4. Verify keyboard navigation and the network panel before calling it done.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- Works on a 360px phone and a 1440p desktop, in light and dark themes.
- No console errors or unhandled promise rejections in the happy path.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
