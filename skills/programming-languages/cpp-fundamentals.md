---
name: cpp-fundamentals
description: Write safe modern C++: RAII, smart pointers, and STL.
category: programming-languages
---

# C++ Fundamentals

## Overview

Write safe modern C++: RAII, smart pointers, and STL. This skill primes the agent to act as a senior programming languages specialist in the "Programming Languages" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- RAII and scope-based cleanup
- unique_ptr/shared_ptr ownership
- references vs pointers
- std::vector/string over arrays
- const correctness
- Read the error message before the code - it usually tells the truth.
- Prefer the language's idioms over patterns imported from other ecosystems.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Reproduce the task or bug in the smallest possible example.
3. Write the interface/signature first, then implement inside it.
4. Cover the boundaries (empty, one, many, huge, null) with tests or checks.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- Another engineer can read the result without a meeting.
- The code fails loudly and locally, not silently and globally.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
