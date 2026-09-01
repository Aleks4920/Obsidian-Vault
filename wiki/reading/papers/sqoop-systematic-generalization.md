---
tags: [papers, machine-learning, neural-module-networks, generalization]
notion_source: "https://www.notion.so/27bfe6aa14b980ab8e12fe4546b03ddc"
last_synced: "2026-04-13"
authors: "Dzmitry Bahdanau, Shikhar Murty, Michael Noukhovitch"
status: Done
keywords: [Machine Learning]
---

# Systematic Generalization: What Is Required and Can It Be Learned?

**Authors:** Dzmitry Bahdanau, Shikhar Murty, Michael Noukhovitch  
**Topic:** Systematic generalization in neural networks using Visual QA  
**Related:** [[nmn-paper-notes]], [[sqoop-systematic-generalization]], [[combining-induction-transduction]]

---

## Summary

Investigates whether neural models can achieve **systematic generalization** — the ability to reason about all possible combinations of concepts, even if only a subset was seen during training. Uses Visual QA (VQA) as the testbed, introducing the **SQOOP dataset**.

## The SQOOP Dataset

- Images: 64×64 pixels with 5 randomly placed symbols (A–Z, 0–9)
- Questions: Binary (Yes/No) of form `X R Y` where R ∈ {LEFT OF, RIGHT OF, ABOVE, BELOW}
- Challenge: Train on a small subset of object pairs, test on all 5040 pairs
- Difficulty controlled by `#rhs/lhs` — lower values (e.g., 1) are hardest

## Models Compared

**Generic VQA:**
- CNN+LSTM, FiLM, Relation Networks (RelNet), Memory-Attention-Control (MAC)

**Modular (NMN):**
- NMN-Tree (tree-structured layout)
- NMN-Chain and NMN-Chain-Shortcut (sequential layouts)
- End-to-end variants: Stochastic N2NMN, Attention N2NMN

## Key Findings

- **NMN-Tree generalizes best** — near-perfect accuracy even on hardest splits (#rhs/lhs = 1)
- Generic models (FiLM, MAC) fail dramatically on harder splits (FiLM error ≈ 35%)
- **Layout matters more than parameterization** — tree layout is crucial, not just modularity
- End-to-end learning struggles — fails to consistently discover optimal tree layout
- Stochastic N2NMN required strong initialization to perform well

## Broader Implications

- Modularity + explicit structure **enhance systematic generalization**
- Replacing hard-coded components with learnable ones is insufficient without structural priors
- Insights from SQOOP inform how to build systems that generalize from biased/limited data

## See Also
- [[nmn-paper-notes]] — detailed Q&A study notes on this paper
