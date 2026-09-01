---
tags: [papers, machine-learning, diffusion-models, spatial-reasoning]
notion_source: "https://www.notion.so/2c3fe6aa14b980f282abc3407fe1d271"
last_synced: "2026-04-13"
authors: "Unknown"
status: Not started
keywords: []
---

# Spatial Reasoning with Denoising Models

**Topic:** Using DDPM to learn spatial constraints for Sudoku-like reasoning tasks  
**Related:** [[reduce-reuse-recycle]], [[compositional-visual-generation]]

---

## Summary

Tests whether **Diffusion Denoising Probabilistic Models (DDPM)** can learn spatial constraints purely from training examples, without being given explicit rules. Uses a toy spatial reasoning task with Sudoku-like constraints.

## Experiment (Figure 2)

- Train a standard unconditional DDPM on **valid spatial configurations only**
- No explicit conditioning information or rules provided
- Model must learn structure implicitly from the data distribution
- Demonstrates the model can learn to generate valid spatial arrangements

## Why Standard Conditional DDPM Fails on Sudoku

- Diffusion training noise **breaks discrete structure** — even small denoising errors produce invalid digits or repeated digits, violating combinatorial constraints
- Diffusion models excel at smooth, continuous domains; Sudoku is discrete and constrained

## Proposed Fix

- Smaller sequential steps
- Only allow valid digits at each step (filtered view)
- Introduce t_i as a noise generator with per-patch loss weighting to address sampling bias

## Datasets

The paper introduces three datasets for testing spatial reasoning constraints (details not noted in Notion page).

## Status

Paper is marked "Not started" in Notion — minimal notes available.
