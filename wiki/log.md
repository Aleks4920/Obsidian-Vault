# Wiki Log

Chronological record of all wiki operations.

## [2026-04-13 auto] sync | Incremental sync

**Inbox sorted:** 0 items (inbox was empty)
**Pages updated:** 0 (no Notion pages updated since last sync)
**New pages created:** 0
**Attachments downloaded:** 0

---

## [2026-04-13] ingest | Full papers & books sync — expanded wiki

**Operation:** Deep re-crawl of all Notion Papers and Books databases after initial sync missed content

**Pages created (34 new):**

*Papers — Machine Learning & AI (15):*
- sqoop-systematic-generalization, combining-induction-transduction, chain-of-thought-prompting, towards-understanding-cot, intelligence-edge-of-chaos, reduce-reuse-recycle, spatial-reasoning-denoising, mvot-multimodal-visualization, seal-self-adapting-lm, product-of-experts-arc, compositional-visual-generation, test-time-training, requirements-engineering-ml, attention-is-all-you-need, sensory-order

*Papers — Cybersecurity & Systems (7):*
- reflections-trusting-trust, heckler, trust-vlm, docker-hub-security, password-meters, pci-dss-survey, delegating-computation

*Papers — Cryptography (2):*
- quantum-cryptography, post-quantum-cryptography

*Books (8):*
- psychology-of-money, manufacturing-consent, skunk-works, propaganda, benjamin-franklin-autobiography, tender-is-the-flesh, the-creative-act, the-secret-history

*Updated existing pages (3):*
- wiki/reading/papers.md — full indexed table of all 26 papers
- wiki/reading/books.md — full table of all 8 books
- wiki/index.md — expanded to 65 total pages with all new entries

**Images pending download:** S3-signed image URLs found in Compositional Visual Generation, Reflections on Trusting Trust, Quantum Cryptography, Self-Adapting Language Models — need re-fetch for fresh URLs before downloading.

---

## [2026-04-12 15:30] ingest | Initial full sync from Notion

**Operation:** Full initial sync — Notion workspace → Obsidian wiki

**Pages created (31):**
- *Cybersecurity (5):* cybersecurity-notes, sentinel, smartcards, ccna-study-notes, devsecops
- *Development (1):* git
- *Work (2):* tasks, orbital-hardware-request-form
- *Academics (6):* school, courses-s2026, exams, linguistics, nmn-paper-notes, paper-and-article-notes
- *Language Learning (4):* language-learning, language-learning-goals, language-learning-activities, dictionaries
- *Reading (5):* reading, books, book-notes, papers, quotes
- *Personal (8):* personal-hub, quick-notes, k-and-f-notes, to-be-sorted, finance-tracker, workout-planner, my-tasks
- *Root (2):* index.md, log.md

**Attachments downloaded to raw-sources/ (4):**
- cybersecurity/cyber-kill-chain.png, cybersecurity/gdpr-diagram.png
- cybersecurity/sentinel-incidents.png, cybersecurity/sentinel-definitions.png

**Notion improvements:**
- Renamed "rrr" → "🔐 PGP Key - Uni Bern"; renamed "K&F notes" → "📅 K&F Work Notes"
- Added Key Words to 7 Notes DB entries; fixed typos across 7 pages
- Improved descriptions on Git, DevSecOps, CCNA, Quick Notes, SmartCards
- Added inbox notice to "To be sorted"; added placeholder to empty Politics page

**Sync schedule:** Hourly at :08 past the hour (task: notion-obsidian-sync)
