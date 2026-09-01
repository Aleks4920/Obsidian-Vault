---
tags: [academics, learning, deep-learning, neural-networks, research]
notion_source: "https://www.notion.so/eb09466ddd65438db3f17cedd81048f6"
last_synced: "2026-04-12"
---

# Neural Module Networks (NMN) — Paper Notes

Study notes on a paper about Neural Module Networks and systematic generalization, evaluated on the SQOOP dataset.

## Main Goal & Key Contributions

Find out if models can answer yes/no questions based on images they have **not** been trained on (SQOOP dataset). The core question: can models actually think and reason about the real world, or are they just pattern-matching from training data?

## How SQOOP Probes Systematic Generalization

> "A good model should be able to reason about all possible object combinations despite being trained on a very small subset of them."

This allows a true test of a model's understanding of the real world instead of just filling in blanks from its knowledge base. SQOOP isolates compositional generalization by controlling exactly which object combinations appear in train vs. test sets.

## NMN Architectures — Layout and Parametrization

- **Layout** = how modules are connected
- **Parametrization** = how the modules are set up
- A set of modules where each is trained to do just one task (good for specific, non-general tasks)
- Three main layouts:
  - **Chain** — modules connected sequentially
  - **Tree** — modules connected in a tree structure
  - **Chain Shortcut** — chain with skip connections added

## Generalization Results (Figure 3)

- NMN-Tree generalizes perfectly at #rhs/lhs = 1
- Most models succeed or perform well at higher #rhs/lhs ratios
- Tree-structured modularity is key — the authors argue tree structure should be best

## Why NMN-Tree Generalizes Well While NMN-Chain Fails

The three NMN versions don't use a language encoder but differ in how modules are connected. Results show that for both Find and Residual module architectures, **tree layout is absolutely crucial (and sufficient) for generalization**. NMN-Chain performs barely above random chance.

## Failure Mode of NMN-Chain

NMN-Chain-Shortcut adds skip connections to partially address the failure mode of NMN-Chain. *(Details incomplete in source notes.)*

## Why Modern LLMs Generalize Compositionally

Modern LLMs succeed where the models in this paper fail, likely due to:
- Scale — vastly more parameters and training data
- Attention mechanisms allowing flexible compositional reasoning
- Massive training data providing implicit exposure to many compositional combinations

## Where Are NMNs Now?

NMNs are largely eclipsed by Transformers/LLMs. Key reasons:
- Transformers scale better
- Require less manual module design
- Achieve generalization through scale rather than hard-coded structure

Modular approaches might make a comeback in:
- Interpretability research
- Low-data settings
- Safety-critical applications requiring structured, auditable reasoning

## See Also

- [[courses-s2026]]
- [[linguistics]]
