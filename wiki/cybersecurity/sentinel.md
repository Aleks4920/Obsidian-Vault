---
tags: [cybersecurity, siem, microsoft-sentinel, incident-response]
notion_source: "https://www.notion.so/320fe6aa14b980e5a37ad6fc3cdd5a34"
last_synced: "2026-04-12"
---

# Sentinel

Microsoft Sentinel is a cloud-native SIEM (Security Information and Event Management) and SOAR platform. Related topics: [[cybersecurity-notes]], [[devsecops]].

## Incidents

- An **incident** is defined as a series of events (alerts) that may compromise an organization
- Can be created manually using **Bookmark**
- Contain evidence and information gathered during investigation
- Can trigger **automation** (playbooks, Logic Apps) for response workflows

## Definitions

| Term | Definition |
|------|------------|
| **Security Event** | A change in any node or device that can indicate risk |
| **Security Alert** | A collection of events that together signal a potential threat |
| **HVT (High Value Target)** | IP addresses, important devices, or user accounts that are priority assets |
| **PII (Personal Identifiable Information)** | Any data that can be used or linked to identify an individual — see also [[cybersecurity-notes]] |
| **SLO (Service Level Object)** | Things that must be defended and reported; part of the broader SLA |

## Assessment and Containment

Containment decisions require careful judgment. Rushing can destroy evidence or cause additional damage.

### Guiding Questions

Before containing an incident, work through these questions:

1. Is the incident still ongoing?
2. What is the business impact?
3. Is important or sensitive data exposed?
4. Will containment stop critical processes or destroy evidence?
5. What is the intended duration of the containment solution?

### Principles

- **Never rush into containment** if it is not immediately necessary
- The **incident manager or client** makes the final containment decision — not the analyst alone
- **Gather as much information as possible** before taking action
- Some attacks may cause **extra damage when contained** (e.g. destructive malware triggered by network isolation)
- Maintain efforts to **preserve evidence integrity** throughout
