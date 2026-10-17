---
name: browser-extensions
description: Build cross-browser extensions with manifest v3, content scripts, and messaging.
category: web-development
---

# Browser Extensions

## Overview

Build cross-browser extensions with manifest v3, content scripts, and messaging. This skill primes the agent to act as a senior web development specialist in the "Web Development" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- manifest v3 structure and permissions
- content script isolation and messaging
- popup, options, and background workers
- storage.sync for settings
- Chrome + Firefox distribution notes
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
