---
name: elasticsearch
description: Build search with mappings, analyzers, and relevance tuning.
category: databases
---

# Elasticsearch Search

## Overview

Build search with mappings, analyzers, and relevance tuning. This skill primes the agent to act as a senior databases specialist in the "Databases" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- mapping design and dynamic mapping off
- analyzers, ngrams, and search-as-you-type
- bool queries and function scoring
- aggregations for facets
- reindex strategy for mapping changes
- Start from the queries the application runs, then design the schema around them.
- Every migration must be reversible or at least rehearsed against production-like data.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Model entities, relations and the access patterns before choosing tools.
3. Validate with realistic volumes - row counts change everything.
4. Measure with EXPLAIN or the engine's equivalent before and after changes.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- No query in the critical path without an index that serves it.
- Backups exist only if a restore has actually been rehearsed.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
