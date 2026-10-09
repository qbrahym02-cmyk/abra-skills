---
name: github-actions
description: Build pipelines that are fast, legible, and secure.
category: devops-cloud
---

# GitHub Actions CI/CD

## Overview

Build pipelines that are fast, legible, and secure. This skill primes the agent to act as a senior devops and cloud specialist in the "DevOps and Cloud" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- workflow triggers and path filters
- caching dependencies properly
- matrix builds for versions/OSes
- OIDC instead of long-lived secrets
- required checks and branch protection
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
