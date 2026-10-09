---
name: hexagonal-architecture
description: Isolate business logic from frameworks and I/O with ports and adapters.
category: software-architecture
---

# Hexagonal Architecture

## Overview

Isolate business logic from frameworks and I/O with ports and adapters. This skill primes the agent to act as a senior software architecture specialist in the "Software Architecture" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- ports define intent, adapters do I/O
- frameworks as replaceable details
- test doubles at the ports
- composition root wiring
- when the ceremony is worth it
- Architecture is the set of decisions that are expensive to change - spend care only there.
- Coupling is the enemy: dependencies point toward stability, never toward churn.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. List the forces: scale, team, deadlines, existing constraints - before drawing boxes.
3. Propose two options minimum and name what each optimizes for.
4. Decide, write the decision down (context, choice, consequences), then build the thinnest slice.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- The next feature can be added without touching ten files.
- A new team member can find where anything lives within a day.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
