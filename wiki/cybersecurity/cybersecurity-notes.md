---
tags: [cybersecurity, security, fundamentals]
notion_source: "https://www.notion.so/146fe6aa14b9801dbb05c73fc25b6e6b"
last_synced: "2026-04-12"
---

# Cybersecurity Notes

Core concepts and frameworks in cybersecurity. Related topics: [[sentinel]], [[smartcards]], [[devsecops]], [[ccna-study-notes]].

## CIA Triad

The three pillars of information security:

- **Confidentiality** — ensuring data is accessible only to authorized parties
- **Integrity** — ensuring data is accurate and has not been tampered with
- **Availability** — ensuring data and systems are accessible when needed

## DAD (Opposite of CIA)

The threat model that maps to each CIA property:

- **Disclosure** — opposite of Confidentiality
- **Alteration** — opposite of Integrity
- **Destruction / Denial** — opposite of Availability

## Security Models

### Bell-LaPadula Model

Focused on **confidentiality**. Governs how subjects access objects across security levels.

- **Simple Security Property (No Read Up)** — a subject cannot read data at a higher classification level
- **Star Security Property (No Write Down)** — a subject cannot write data to a lower classification level
- **Discretionary-Security Property** — uses an access matrix to control permissions

### Biba Model

Focused on **integrity**. The inverse logic of Bell-LaPadula.

- **Simple Integrity Property (No Read Down)** — a subject cannot read data at a lower integrity level
- **Star Integrity Property (No Write Up)** — a subject cannot write data to a higher integrity level

### Clark-Wilson Model

Also focused on **integrity**, using a transaction-based approach.

- **CDI (Constrained Data Item)** — data whose integrity must be preserved
- **UDI (Unconstrained Data Item)** — data not subject to integrity constraints (e.g. raw user input)
- **TPs (Transformation Procedures)** — the only operations allowed to modify CDIs
- **IVPs (Integrity Verification Procedures)** — procedures that verify CDIs are in a valid state

## ISO/IEC 19249

### 5 Architectural Principles

1. **Domain Separation** — separate components into distinct domains to limit blast radius
2. **Layering** — stack security controls in layers
3. **Encapsulation** — hide internal implementation details
4. **Redundancy** — eliminate single points of failure
5. **Virtualization** — isolate environments using virtual boundaries

### 5 Design Principles

1. **Least Privilege** — grant only the minimum permissions necessary
2. **Attack Surface Minimisation** — reduce the number of exposed entry points
3. **Centralized Parameter Validation** — validate all input in one place
4. **Centralized General Security Services** — consolidate security logic rather than duplicating it
5. **Preparing for Error and Exception Handling** — design systems to fail securely

## Cyber Kill Chain

A framework describing the stages of a cyberattack. The goal is to **defend and detect at all parts** of the chain — not just the perimeter. Interrupting any stage can stop an attack.

## Developing Governance Documents

Standard lifecycle for security policies and governance documentation:

1. Identify scope and purpose
2. Research
3. Draft
4. Review and approval
5. Implementation and communication
6. Review and update

## GDPR

- Applies to **any data associated with an individual that can identify them**
- Stringent regulation with significant penalties for non-compliance
- Companies need a **legitimate reason** to collect personal data
- Individuals have rights including access, erasure, and portability

## SLSA (Supply-chain Levels for Software Artifacts)

- A framework of standards for hardening the **security posture of software supply chains**
- Files produced by a build process are called **artifacts**
- Levels (1–4) describe increasing degrees of build integrity and provenance guarantees
- Relevant to [[devsecops]] pipelines where build provenance and image integrity matter
