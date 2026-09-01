---
tags: [papers, cybersecurity, cryptography, quantum]
notion_source: "https://www.notion.so/114fe6aa14b9804ba9f1f9d1bed3daf7"
last_synced: "2026-04-13"
authors: "Sherdel A. Käppler, Bettina Schneider"
status: Done
keywords: [Quantum, Quantum Cryptography]
year: 2022
---

# Post-Quantum Cryptography: An Introductory Overview and Implementation Challenges of Quantum-Resistant Algorithms

**Authors:** Sherdel A. Käppler, Bettina Schneider  
**Topic:** Overview of post-quantum cryptographic algorithms and their implementation challenges  
**Related:** [[quantum-cryptography]], [[cybersecurity-notes]], [[smartcards]]

---

## Summary

Introductory overview of post-quantum cryptography (PQC) — algorithms designed to be secure against attacks from quantum computers, intended for use on classical hardware.

## Notes

- References the **McCumber Cube** model (limited notes taken)
- Minimal content recorded in Notion — primary reference is the paper itself

## Context

Post-quantum cryptography is motivated by Shor's algorithm, which can break RSA and Diffie-Hellman on a sufficiently powerful quantum computer. PQC alternatives include:
- Lattice-based cryptography
- Hash-based signatures
- Code-based cryptography
- Multivariate polynomial cryptography

NIST selected several PQC algorithms for standardization (finalized 2024), including CRYSTALS-Kyber (now ML-KEM) and CRYSTALS-Dilithium (now ML-DSA).

## See Also

- [[quantum-cryptography]] — QKD and quantum principles
