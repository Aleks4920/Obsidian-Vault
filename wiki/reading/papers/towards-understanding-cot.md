---
tags: [papers, machine-learning, llm, prompting, reasoning]
notion_source: "https://www.notion.so/2a7fe6aa14b980d1b9bac1b71fa29488"
last_synced: "2026-04-13"
authors: "Boshi Wang, Sewon Min, Xiang Deng, Jiaming Shen, You Wu, Luke Zettlemoyer, Huan Sun"
status: Done
keywords: [Machine Learning]
---

# Towards Understanding Chain-of-Thought Prompting: An Empirical Study of What Matters

**Authors:** Boshi Wang, Sewon Min, Xiang Deng, Jiaming Shen, You Wu, Luke Zettlemoyer, Huan Sun  
**Topic:** Ablation study identifying what components of CoT actually matter  
**Related:** [[chain-of-thought-prompting]], [[test-time-training]]

---

## Summary

Empirically investigates **which parts of Chain-of-Thought prompting actually matter** by ablating different properties of CoT rationales and measuring impact. Key finding: **relevance and order** are the dominant factors — valid reasoning isn't strictly necessary.

## CoT Components Identified

- **Bridging objects:** Key intermediate entities/numbers the model must traverse to reach the answer
  - Arithmetic: numeric parts (numbers & equations)
  - Factual QA: subject & object entities
- **Language templates:** Textual hints and relations/predicates guiding the model to derive bridging objects; connect the reasoning steps

## Main Findings

1. **Relevance > Coherence for bridging objects** — being relevant to the query is more important than logical validity
2. **Language coherence matters for templates** — the connective language must be coherent
3. **Invalid reasoning still works** — prompts with *invalid* reasoning still reach **80–90%** of CoT performance
4. **Relevance of bridging objects is crucial** — using irrelevant numbers/entities kills performance far more than wrong reasoning order

## Surprising Result (Figure 2)

- Invalid reasoning **outperforms standard CoT at reasoning depth of 1**
- Performance drop with invalid reasoning is small and consistent
- Suggests: the LLM may not be "following" the reasoning but using it as a structured hint toward relevant data

## Evaluation Metric

**Intermediate (Inter.) Recall/F1** — measures whether the model generates the correct bridging objects in its rationale, beyond just answer accuracy.

## Implications

LLMs with invalid CoT still output correct answers → the CoT may function as a **structured relevance signal** rather than explicit logical derivation. The model may be using training data knowledge, not following the chain.
