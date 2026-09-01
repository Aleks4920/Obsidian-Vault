---
tags: [papers, machine-learning, arc, induction, transduction]
notion_source: "https://www.notion.so/284fe6aa14b98000ad49df517159652d"
last_synced: "2026-04-13"
authors: "Wen-Ding Li et al."
status: Done
keywords: [Machine Learning]
---

# Combining Induction and Transduction for Abstract Reasoning

**Authors:** Wen-Ding Li, Keya Hu, Carter Larsen, Yuqing Wu, Simon Alford, et al.  
**Topic:** Combining inductive program synthesis and transductive output prediction for ARC  
**Related:** [[product-of-experts-arc]], [[test-time-training]], [[sqoop-systematic-generalization]]

---

## Summary

Shows that **induction** (generating a program/function to explain examples) and **transduction** (directly predicting output) are **complementary** — combining both approaches significantly outperforms either alone on ARC reasoning tasks.

## Core Concepts

- **Induction:** Learns/generates a Python function that maps input→output from training examples. More interpretable, but sensitive to data quality and may fail if no valid program is found.
- **Transduction:** Directly predicts output distribution using beam search. No explicit function — learns patterns implicitly. Used as fallback.

## Main Findings

1. Induction and transduction solve different subsets of tasks (large non-overlap demonstrated in Figure 5 Venn diagram)
2. Only a certain number of human-generated seeds needed — once core concepts are learned, more seeds add diminishing returns
3. Induction is more sensitive to data quality than transduction
4. Humans outperform on simple tasks; model outperforms on complex tasks

## Proposed Ensembling Method

1. **Try induction first** — sample programs; if any pass all train examples, use one to produce output
2. **Fall back to transduction** if none pass — output top prediction
3. In large-compute settings: majority vote over many consistent programs + transduction with TTT and reranking

## Dataset Generation

Start with 100 human-generated seeds (NL description + Python solver + input generator), then:
1. Self-instruct-style NL descriptions via LLM
2. RAG to generate new Python code using shared domain library
3. Execute & filter (determinism, color-permutation invariance, non-triviality)

Scales to hundreds of thousands of new problems with ground-truth code.

## Scaling Insights

- Performance scales with more synthetic data per seed, but **saturates** with more human seeds
- For induction: test-time sampling budget monotonically helps; majority vote suppresses false positives (~9% rate)
