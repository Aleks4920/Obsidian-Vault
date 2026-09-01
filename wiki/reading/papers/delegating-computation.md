---
tags: [papers, cryptography, interactive-proofs, verifiable-computation]
notion_source: "https://www.notion.so/2a6fe6aa14b9804c8e1df0b24af8d11c"
last_synced: "2026-04-13"
authors: "Shafi Goldwasser, Yael Tauman Kalai, Guy N. Rothblum"
status: Done
keywords: []
year: 2008
---

# Delegating Computation: Interactive Proofs for Muggles

**Authors:** Shafi Goldwasser, Yael Tauman Kalai, Guy N. Rothblum  
**Topic:** Interactive proof system allowing a weak verifier to delegate computation to a powerful prover  
**Related:** [[cybersecurity-notes]], [[quantum-cryptography]]

---

## Summary

Provides a **public coin interactive proof** for any language computable by a log-space uniform boolean circuit, enabling a computationally weak verifier to outsource computation to a powerful prover while efficiently checking the result.

## Main Technical Theorem

For any language computable by a **log-space uniform boolean circuit** with:
- Depth: d
- Input length: n

The proof system achieves:
- **Verifier complexity:** time O((n+d)·polylog(n)), space O(log n)
- **Communication complexity:** d·polylog(n)
- **Prover complexity:** poly(n)

## Key Properties

- **Public coin:** The verifier's randomness is public (Arthur-Merlin protocol style)
- **Designated verifier certificates:** Each certificate is tailored to the verifier's public key
- **Quasi-linear verification:** Certificates can be verified in quasi-linear time

## Significance

Foundational result for **verifiable computation** and **outsourced computation** — a client can delegate expensive computation to an untrusted cloud/server and efficiently verify the result is correct, without redoing the computation.
