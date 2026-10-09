---
name: domain-driven-design
description: Model software around the business domain with a shared language.
category: software-architecture
---

# Domain-Driven Design

## Overview

Model software around the business domain with a shared language. This skill primes the agent to act as a senior software architecture specialist in the "Software Architecture" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- ubiquitous language with domain experts
- entities, value objects, aggregates
- aggregate boundaries and consistency
- bounded contexts and maps
- anti-corruption layers at edges
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
