---
tags: [papers, machine-learning, llm, prompting, reasoning]
notion_source: "https://www.notion.so/29ffe6aa14b98039ad24f3efdd3de8e0"
last_synced: "2026-04-13"
authors: "Jason Wei, Xuezhi Wang, Dale Schuurmans et al."
status: Done
keywords: [Machine Learning]
year: 2022
---

# Chain-of-Thought Prompting Elicits Reasoning in Large Language Models

**Authors:** Jason Wei, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Brian Ichter, Fei Xia, Ed H. Chi, Quoc V. Le, Denny Zhou  
**Topic:** Few-shot prompting with intermediate reasoning steps improves LLM performance  
**Related:** [[towards-understanding-cot]], [[test-time-training]], [[seal-self-adapting-lm]]

---

## Summary

Introduces **Chain-of-Thought (CoT) prompting** — providing a few exemplars that include step-by-step reasoning traces in the prompt. Shows that this elicits multi-step reasoning in large language models, especially on math word problems, commonsense reasoning, and symbolic manipulation.

## Key Concepts

- **CoT vs. Standard Few-Shot:** Standard few-shot treats all questions equally; CoT can allocate more computation to harder multi-step problems by generating more tokens
- **Emergent capability:** CoT gains only appear in large models (~100B+ parameters); small models show no improvement or slight decrease
- **Interpretability:** CoT provides a window into model behavior (though it doesn't prove "true reasoning")

## Main Findings

1. **Large models benefit greatly** — Figure 4 shows small models unchanged or decrease; large models show dramatic gains
2. **CoT-after-answer performs same as baseline** — the model must depend on the generated chain to answer correctly
3. **No loss on generalized models** — Figure 8: small models stay same, large models get huge increases
4. **Works across task types** — math word problems, commonsense reasoning, symbolic manipulation

## Compute Allocation Hypothesis

CoT allows models to "think longer" on harder problems. Tested via ablation:
- Basic CoT vs. Variable compute only vs. CoT-after-answer
- More tokens allocated → better results on harder problems

## Limitations

- CoT **doesn't prove** the model is actually reasoning (may simulate it)
- Manual annotation of CoT exemplars is costly for fine-tuning (fine in few-shot)
- No guarantee of correct reasoning paths
- Token-hungry — requires more compute per query

## See Also

- [[towards-understanding-cot]] — ablation study on what components of CoT matter
- [[test-time-training]] — combining CoT with test-time parameter updates
