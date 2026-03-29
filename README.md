# ConfidenceCalibration: Adversarial Near-Miss Metacognition Benchmark

**Track:** Metacognition  
**Event:** Kaggle × Google DeepMind AGI Hackathon 2026

## Overview

`ConfidenceCalibration` is a benchmark designed to evaluate whether large language models know when they might be wrong.

Many frontier models can produce answers that sound convincing even when incorrect. This benchmark focuses on **adversarial near-miss questions** — prompts where there is a highly plausible wrong answer that often triggers **overconfidence**.

The core goal is not just to measure whether a model gets the answer right, but whether its **confidence matches reality**.

---

## Core Research Question

When a model answers incorrectly:

- Does it show uncertainty?
- Or does it remain highly confident in the wrong answer?

This benchmark measures that behavior directly.

---

## Why This Benchmark Matters

Traditional benchmarks mostly evaluate **accuracy**.  
But for real-world AI systems, that is not enough.

A wrong answer with low confidence is less dangerous than a wrong answer with very high confidence.

This benchmark helps measure:

- **Metacognition** — whether the model knows what it knows
- **Calibration** — whether confidence aligns with correctness
- **Overconfidence risk** — whether the model sounds certain when it should not

This is especially useful in high-stakes domains like:

- healthcare
- law
- finance
- education
- decision-support systems

---

## Benchmark Design

The dataset contains **12 adversarial near-miss questions**.

Each question is designed with the following principles:

1. **Verifiable ground truth**  
   Every item has a deterministically checkable answer.

2. **Near-miss trap**  
   Each question includes a plausible, commonly believed wrong answer.

3. **Explicit confidence elicitation**  
   The model must provide both:
   - an answer
   - a confidence score from 0 to 100

4. **Deterministic grading**  
   No LLM-as-judge is used.  
   All correctness is evaluated using rule-based checkers.

---

## Example Question Format

The model is prompted in this strict structure:

```text
ANSWER: [your answer here]
CONFIDENCE: [integer from 0 to 100]
