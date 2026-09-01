---
tags: [papers, machine-learning, diffusion-models, compositional-generation, ebm]
notion_source: "https://www.notion.so/2bcfe6aa14b9802dbc75cb4d174c7b74"
last_synced: "2026-04-13"
authors: "Unknown"
status: Done
keywords: []
---

# Reduce, Reuse, Recycle: Compositional Generation with Energy-Based Diffusion Models and MCMC

**Topic:** Composing pretrained diffusion models using EBM interpretation and MCMC sampling  
**Related:** [[compositional-visual-generation]], [[spatial-reasoning-denoising]], [[mvot-multimodal-visualization]]

---

## Summary

Shows that pretrained diffusion models can be **composed** to model new distributions by treating them as energy-based models (EBMs). Demonstrates that failures in compositional generation are primarily due to the **sampler**, not the underlying models. Proposes annealed MCMC as the fix.

## Key Insight: Diffusion Models as EBMs

- Diffusion models are trained via **denoising score matching** at multiple noise levels
- This is equivalent to training EBMs — just in a different parameterization
- Enables composing diffusion models by composing their energy functions

## Three Compositional Operators

1. **Product (AND):** Sum the scores from individual diffusion models — high probability only where ALL components assign high probability
2. **Mixture (OR):** High probability where ANY component assigns high probability (union of concepts)
3. **Negation (NOT):** Given base distribution q₀ and unwanted distribution q₁ → combine to suppress q₁

## The Core Mistake (Prior Work)

Prior work composes diffusion models by **adding scores and running reverse diffusion** — implicitly assuming this samples from the product distribution. This is wrong.

## Proposed Fix

Treat the composed distribution as a target for **annealed MCMC** instead of naive reverse diffusion.

**Evidence from experiments:**
- Simply adding more timesteps doesn't fix compositional sampling
- Keeping models fixed and only changing the sampler significantly improves results
- More MCMC steps + Metropolis adjustment → more accurate generations

## Practical Limitations

- MCMC samplers take **5× longer** than standard diffusion sampling
- Requires backward pass through model → **2× memory and compute** vs. score-parameterized models
