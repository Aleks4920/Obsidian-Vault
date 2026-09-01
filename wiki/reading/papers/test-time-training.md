---
tags: [papers, machine-learning, llm, test-time-training, arc]
notion_source: "https://www.notion.so/292fe6aa14b9803bbf30cdb414c3097f"
last_synced: "2026-04-13"
authors: "Ekin Akyurek, Mehul Damani, Adam Zweiger, Linlu Qiu, Han Guo, Jyothish Pari, Yoon Kim, Jacob Andreas"
status: Done
keywords: [Machine Learning, AI]
year: 2025
---

# The Surprising Effectiveness of Test-Time Training for Few-Shot Learning

**Authors:** Ekin Akyurek, Mehul Damani, Adam Zweiger, Linlu Qiu, Han Guo, Jyothish Pari, Yoon Kim, Jacob Andreas  
**Topic:** Combining ICL with gradient-based test-time parameter updates for few-shot reasoning  
**Related:** [[seal-self-adapting-lm]], [[chain-of-thought-prompting]], [[combining-induction-transduction]]

---

## Summary

Shows that combining **In-Context Learning (ICL)** with **Test-Time Training (TTT)** — temporarily updating model parameters during inference using test examples — significantly improves performance on difficult reasoning tasks (ARC and BIG-Bench Hard).

## Key Definitions

**ICL (In-Context Learning):**
- Model learns task without parameter updates by conditioning on few input-output examples in the prompt
- "In-context learning is a powerful means of adaptation without parameter updates"

**TTT (Test-Time Training):**
- Temporarily updates model parameters during inference using information from test examples
- Starting from initial parameters θ₀, for each test input d: generate temporary training dataset D_TTT → minimize loss → use updated model

## TTT Dataset Variants (Figure 2, Row 1)

- **Leave-one-out:** Remove one demonstration → treat as test, others as in-context. Can permute for multiple small tasks. Preserves task structure.
- **Direct I/O:** Treat each (x_k, y_k) pair independently as training instance. No in-context formatting — simpler but loses task structure.

## Loss Variants (Figure 2, Row 2)

- **All Outputs:** Train only on output tokens (standard approach)
- **Inputs + Outputs:** Also train on input tokens — learns task structure but risks noise

## Self-Consistency for ARC

ARC outputs are 2D color grids → standard text self-consistency doesn't apply. Instead:
1. Apply invertible geometric transformations (rotation, flip, transpose) to input grids
2. Generate predictions for each transformed version
3. **Hierarchical voting:** First within each transformation, then across all transformations → top-2 outputs
- Cannot apply to BBH (text answers) → use greedy decoding there

## Results

- **ARC (Figure 5):** FT+TTT achieves 6× improvement over FT baseline; using in-context tasks + augmentations + per-task adapters = highest gains
- **BBH (Figure 7/8):** Sharing adapters across BBH tasks helps transfer learning; hierarchical voting nears oracle performance
- **Shared TTT does well:** Unlike ARC, BBH has no conflicting input structure → sharing parameters improves generalization
