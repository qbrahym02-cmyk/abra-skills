---
name: shell-scripting
description: Write safe shell scripts with quoting, traps, and set -euo pipefail.
category: devops-cloud
---

# POSIX Shell Scripting

## Overview

Write safe shell scripts with quoting, traps, and set -euo pipefail. This skill primes the agent to act as a senior devops and cloud specialist in the "DevOps and Cloud" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- quoting and word-splitting rules
- set -euo pipefail and traps
- mktemp over /tmp races
- portable flags across GNU/BSD
- arg parsing and --help hygiene
- Everything reproducible from version control - infrastructure, config, dashboards.
- Automate the second time you do anything; document the first.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Reproduce the problem or requirement in a disposable environment first.
3. Change one layer at a time: code, config, or infrastructure - never mixed.
4. Verify with dashboards and logs what you changed, then clean up the scaffolding.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- The change survives a disaster drill: rebuild from scratch works.
- No manual step is required between commit and production.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
