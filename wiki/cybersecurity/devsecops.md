---
tags: [cybersecurity, devsecops, devops, security, cicd]
notion_source: "https://www.notion.so/2abfe6aa14b98024a7c7ff83341bb669"
last_synced: "2026-04-12"
---

# DevSecOps

**DevOps with a lens on Security.** The practice of integrating security concerns into every stage of the software development and delivery lifecycle, rather than treating security as a final gate. Related topics: [[cybersecurity-notes]], [[sentinel]], [[git]], [[ccna-study-notes]].

## Benefits

| Benefit | Description |
|---------|-------------|
| **Observability** | Know what is happening between and at each step of application delivery |
| **Traceability** | Know which user stories are being deployed into the RTE (Run Time Environment), and be able to prove it |
| **Confidence** | The business needs to trust IT in what is being delivered — traceability and testing provide this |
| **Compliance** | Must be built in from the start, not retrofitted at the end |

## Requirements / Practices

- **TDD (Test Driven Development)** — write tests before code to ensure functionality is verifiable from the outset
- **Pair Programming** — two developers working together catches issues earlier
- **Linting** — code is standardized and style violations are caught automatically
- **Scanning** — automated scanning for infinite loops, known vulnerabilities (CVEs), and misconfigurations
- **Notary** — ensures images being deployed are the same ones produced by the build process (image signing); relates to [[cybersecurity-notes]] SLSA concepts
- **Mutation Detection** — ensures containers do not break expected behavior after deployment

## Use Cases

- Need **visibility** into what is running and how it was built
- **Audit compliance** — demonstrate to auditors that security controls were applied throughout delivery
- **Unified Governance** — a single, consistent framework for security policy applied across all teams and pipelines
