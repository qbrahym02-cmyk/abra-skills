---
name: app-monetization
description: Wire in-app purchases and ads that respect users and pass review.
category: mobile-apps
---

# App Monetization

## Overview

Wire in-app purchases and ads that respect users and pass review. This skill primes the agent to act as a senior mobile apps specialist in the "Mobile Apps" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- store product config and receipts
- subscription lifecycle and entitlements
- paywall UX and trials
- ad formats and mediation basics
- restore purchases and edge cases
- Design for the worst network and the oldest supported device, not the flagship.
- Respect platform conventions - users bring habits from every other app on their phone.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Define the flow and navigation map before building any single screen.
3. Build one screen end-to-end (state, UI, error states) as the pattern, then replicate.
4. Test on a real low-end device before declaring done.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- Cold start, scroll and tap latency feel instant on a mid-range phone.
- Every state is handled: loading, empty, error, offline, permission denied.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
