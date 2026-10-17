---
name: cli-mastery
description: Live in the terminal: coreutils, pipes, and modern CLI tools.
category: automation-scripting
---

# Command Line Mastery

## Overview

Live in the terminal: coreutils, pipes, and modern CLI tools. This skill primes the agent to act as a senior automation and scripting specialist in the "Automation and Scripting" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- pipes and redirection fluency
- find/grep/rg/sed/awk core moves
- xargs and parallel execution
- process management and jobs
- dotfiles and shell config
- Automate the boring AND the error-prone; humans are bad at repetitive precision.
- Every automation needs a dry-run mode and a log of what it did.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Do the task manually once and note every step and exception.
3. Script it defensively: validate inputs, handle the top failure modes, log outcomes.
4. Schedule it, monitor it, and give it a way to yell for help.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- The script is idempotent - running twice does the same as once.
- A failure leaves a clear log and a safe state.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
