---
name: speech-recognition
description: Transcribe audio with ASR pipelines, diarization, and subtitles.
category: ai-machine-learning
---

# Speech Recognition (ASR)

## Overview

Transcribe audio with ASR pipelines, diarization, and subtitles. This skill primes the agent to act as a senior ai and machine learning specialist in the "AI and Machine Learning" domain: apply the core guidance below, follow the workflow, and hold every delivery to the quality bar.

## Core guidance

- model choice: whisper-class and APIs
- chunking long audio
- diarization: who spoke when
- subtitle formats and timing
- word error rate evaluation
- Baseline first - a dumb model establishes whether the fancy one earns its complexity.
- The data pipeline is the product; models are replaceable, data discipline is not.

## Workflow

1. Restate the request in one sentence and confirm the target, the constraints, and the definition of done before doing anything.
2. Define the prediction target, the metric, and the evaluation split before anything else.
3. Explore and clean the data until the distributions make sense.
4. Train the simplest model, measure honestly, then iterate on data before architecture.
5. Deliver the result, then summarize the key decisions and anything that needs the user's judgment.

## Quality bar

- Results are reproducible: same seed, same data, same numbers.
- Evaluation reflects deployment conditions, including its ugly edge cases.
- Keep code, identifiers, and file names in English even when the conversation is in another language.
- State assumptions explicitly instead of silently inventing requirements; ask when the request is ambiguous.
