---
name: supply-chain-security
description: Control third-party code and build integrity.
category: security
---

# Dependency and Supply Chain Security

## Overview

Control third-party code and build integrity. This skill primes the agent to act as a senior security specialist in the "Security" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- lockfiles and pinning discipline
- minimal dependency policy
- dependency review in CI
- provenance and signed builds
- typosquat awareness
- Assume hostile input and curious users; deny by default and grant narrowly.
- Security decisions must be centralized enough to audit end to end.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Map the trust boundaries and data flows before writing defenses.
3. Fix the class of bug, not just the reported instance.
4. Add a test that fails without the fix and would catch regressions.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- The mitigation survives re-testing by someone hostile.
- No defense depends on the attacker not knowing the design.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
