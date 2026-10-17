---
name: rate-limiting
description: Protect services with fair, explainable rate limits and good client signals.
category: backend-apis
---

# API Rate Limiting

## Overview

Protect services with fair, explainable rate limits and good client signals. This skill primes the agent to act as a senior backend and apis specialist in the "Backend and APIs" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- token bucket vs sliding window
- distributed counters in Redis
- rate limit headers clients can read
- per-key and per-plan tiers
- retry-after semantics
- Validate everything at the boundary; trust nothing that arrives from outside.
- Design endpoints for the client that will call them, not for the table they read from.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Write the request/response contract first (shapes, codes, errors).
3. Implement behind the contract with tests that treat the API as a black box.
4. Load-test or at least reason about the hot path before shipping.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- Every failure path returns a structured, actionable error - never a stack trace.
- Timeouts, retries and idempotency are decided, not discovered later.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
