---
tags: [papers, machine-learning, arc, llm, product-of-experts]
notion_source: "https://www.notion.so/28bfe6aa14b980998dd9fc2f7c40b33d"
last_synced: "2026-04-13"
authors: "Daniel Franzen, Jan Disselhoff, David Hartmann"
status: Done
keywords: [Machine Learning]
---

# Product of Experts with LLMs: Boosting Performance on ARC Is a Matter of Perspective

**Authors:** Daniel Franzen, Jan Disselhoff, David Hartmann  
**Topic:** Combining multiple data augmentation perspectives via Product of Experts for ARC-AGI  
**Related:** [[combining-induction-transduction]], [[test-time-training]], [[sqoop-systematic-generalization]]

---

## Summary

Argues that LLM shortcomings on ARC-AGI stem from **suboptimal data representations**, not fundamental reasoning deficits. Proposes using **Product of Experts (PoE)** with data augmentations to combine multiple "perspectives" on the same problem.

## Core Hypothesis

> "Mounting evidence that many perceived shortcomings in large language models stem from implementation details or suboptimal data representations rather than from fundamental reasoning deficits"
>
> "Models may be aware of their mistakes without being able to correct them"

## Notation

- **P(s):** Prior over solutions — encodes how solutions are structured
- **P(s|p):** Probability of solution given problem — how well s explains observed examples
- **P(p|s):** Probability of problem given solution
- Augmentations Φ define parts of the prior P(s) by encoding expected invariances

## Method

1. **Data augmentation:** Apply multiple augmentations (rotations, flips, color permutations, etc.)
2. **Candidate generation via DFS:** Depth-first search + multinomial sampling to find high-probability solutions under single augmentations
3. **PoE scoring:** Rank candidates by product of expert scores across all augmentations
4. Alphabet simplification: Add "A...Za...z" to prompt to standardize tokens and improve positional consistency

## Theorem 4.1

KL divergence result: when logZ < 0, combining augmented experts reduces divergence from the true distribution, justifying the PoE approach.

## Failure Modes of PoE

1. **Overconfidence:** Some augmentations give near-zero probability to the correct solution → multiplicative suppression
2. **Augmentation mismatch:** Augmentations that violate task invariances mislead the product
- Safety condition: "As long as the true solution does not get zero probability under any single augmentation, it remains viable"
