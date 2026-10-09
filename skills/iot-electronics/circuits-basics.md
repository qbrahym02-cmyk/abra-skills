---
name: circuits-basics
description: Understand circuits: Ohm, dividers, and reading schematics.
category: iot-electronics
---

# Basic Electronics

## Overview

Understand circuits: Ohm, dividers, and reading schematics. This skill primes the agent to act as a senior iot and electronics specialist in the "IoT and Electronics" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- Ohm’s law as a reflex
- voltage dividers everywhere
- reading schematic symbols
- multimeter fluency
- resistor color and SMD codes
- Measure, don't guess: a multimeter and a serial log prevent most magic problems.
- Design for the power budget and the failure mode, not the happy path.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Breadboard the circuit and validate each block before wiring the whole.
3. Write firmware in small testable steps with serial logging.
4. Field-test in the real environment (temperature, distance, interference).
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- The device recovers from power loss and network loss by itself.
- Wiring is documented well enough to rebuild in a year.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
