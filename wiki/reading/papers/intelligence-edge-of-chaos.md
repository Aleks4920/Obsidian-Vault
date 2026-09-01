---
tags: [papers, machine-learning, complexity, cellular-automata, pretraining]
notion_source: "https://www.notion.so/2cafe6aa14b98091aa6cf931253e3e73"
last_synced: "2026-04-13"
authors: "Shiyang Zhang, Aakash Patel, Syed Rizvi, et al."
status: Not started
keywords: []
---

# Intelligence at the Edge of Chaos

**Authors:** Shiyang Zhang, Aakash Patel, Syed Rizvi, Nianchen Liu, Sizhuang He, Amin Karbasi, Emanuele Zappala, David van Dijk  
**Topic:** Pretraining GPT-2 on Elementary Cellular Automata data to study intelligence emergence  
**Related:** [[chain-of-thought-prompting]], [[seal-self-adapting-lm]]

---

## Summary

Tests the hypothesis that **intelligence can emerge from modeling simple systems as long as they exhibit complex behaviors**, even when the generative process lacks inherent intelligence. Uses Elementary Cellular Automata (ECAs) as the experimental framework.

## What Are ECAs?

- **Elementary Cellular Automata (ECAs):** 1D cellular automaton where each cell has binary state; next state determined by current cell and its two immediate neighbors
- 256 possible ECA rules (Wolfram's classification)
- Classes: I (simple/static), II (periodic), III (chaotic), IV (complex/edge of chaos)
- Generative process is deterministic, **not random**

## Experimental Setup

- Trained separate GPT-2 instances on data from individual ECAs
- Task: predict future states of the automaton
- Then evaluated on downstream **logical reasoning** and **chess move prediction** tasks

## Key Findings

**From Figure 3 (attention analysis):**
- Models on simple (Class I) rules: almost no attention on past states → trivial rule lookup
- Models on periodic (Class II) rules: attend to specific earlier time steps → cycle memorization
- Models on chaotic/complex (Class III/IV) rules: strongly attend to multiple recent past states
- Strong positive correlation (r ≈ 0.66) between data complexity and attention to historical context

**Surprising finding:**
- Models predicting **only the next step** outperformed models predicting 5 steps ahead
- Forcing multi-step prediction was hypothesized to create richer representations, but actually decreased performance

## Hypothesis Validated

Training on complex ECA data (near the "edge of chaos") produces models that learn non-trivial, history-integrating representations — correlating with better downstream intelligence.
