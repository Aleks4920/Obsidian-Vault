---
tags: [papers, machine-learning, multimodal, reasoning, visualization]
notion_source: "https://www.notion.so/2aefe6aa14b98000882ce7640ea5916b"
last_synced: "2026-04-13"
authors: "Chengzu Li, Wenshan Wu, Huanyu Zhang, Yan Xia, Shaoguang Mao, Li Dong, Ivan Vulic, Furu Wei"
status: Done
keywords: []
year: 2025
---

# Imagine while Reasoning in Space: Multimodal Visualization-of-Thought (MVoT)

**Authors:** Chengzu Li, Wenshan Wu, Huanyu Zhang, Yan Xia, Shaoguang Mao, Li Dong, Ivan Vulic, Furu Wei  
**Topic:** MLLMs that generate intermediate visual images as reasoning steps  
**Related:** [[compositional-visual-generation]], [[spatial-reasoning-denoising]]

---

## Summary

Proposes **Multimodal Visualization-of-Thought (MVoT)** — a reasoning paradigm where MLLMs generate **interleaved text and image tokens** as reasoning steps, rather than text-only chain-of-thought. Demonstrates on three spatial reasoning tasks.

## Key Concepts

**MLLM (Multimodal Large Language Model):**
- Combines vision and language — processes and generates both text and images
- Single autoregressive transformer over unified sequence of text tokens + image tokens

**VoT (Visualization of Thought):** Prior work — builds visualizations via text proxies. MVoT extends this to *real image generation*.

**MVoT:** Each reasoning step alternates:
1. Text: "Go left. Go up. …"
2. Image: Visualization of updated state after those actions
3. Next text step is conditioned on previous text + images

## Architecture Components

- **Text tokenizer:** raw text → discrete text tokens (subword IDs)
- **Image tokenizer (VQ-VAE-style):** image → discrete image tokens from learned codebook
- Both concatenated into unified transformer sequence
- **Token discrepancy loss:** extra loss on image tokens to align LM embeddings with visual codebook embeddings — critical for image quality

## Three Spatial Reasoning Tasks

1. **MAZE:** Given grid maze image + action sequence, identify final destination (A–D)
2. **MINIBEHAVIOR:** Agent with objects on a table; given layout + actions, predict outcome category (Action Success / Drop Error / Pick Up Error / Missing Key Objects)
3. **FROZENLAKE:** Elf agent navigating a frozen lake; predict if agent reaches gift, falls in hole, or ends safe but short

## Results

- MVoT is more robust than CoT-with-layout for complex tasks (Table 2)
- Token discrepancy loss improves FROZENLAKE from 0.7260 → 0.8560
- CoT with layout may outperform on simpler tasks

## Limitations

- Generated visualizations often reconstruct task-irrelevant details (e.g., background patterns)
- Explicit image generation introduces **computational overhead** at inference
