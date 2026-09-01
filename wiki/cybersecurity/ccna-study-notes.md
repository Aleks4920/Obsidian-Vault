---
tags: [cybersecurity, networking, ccna, cisco]
notion_source: "https://www.notion.so/e10ccbd3dd5e42688a9199729535f65a"
last_synced: "2026-04-12"
---

# CCNA Study Notes

Networking concepts for the Cisco CCNA exam. Related topics: [[cybersecurity-notes]], [[devsecops]].

## Spanning Tree Protocol (802.1D STP)

- STP **stops loops** in switched Layer 2 architectures
- Without STP, broadcast storms can bring down a network
- Combines the **disabled**, **blocking**, and **listening** states into a single **discarding** state (in RSTP / 802.1w)

## Collision Domains

- A **single switch port** equals a **single collision domain**
- **Collision domain**: a network segment where packets transmitted by two devices can collide with each other
- Switches break up collision domains; hubs do not

## DNS

- DNS uses **both TCP and UDP**
  - **UDP (port 53)** — standard queries and responses (fast, lightweight)
  - **TCP (port 53)** — zone transfers and responses exceeding 512 bytes

## BGP (Border Gateway Protocol)

- BGP is the routing protocol of the internet, used to exchange routing information between **Autonomous Systems (AS)**
- When two routers share the **same BGP AS number**, they are **iBGP (internal BGP)** neighbors
  - iBGP is used for routers **within the same AS** to exchange routing information with each other
- When two routers have **different AS numbers**, they are **eBGP (external BGP)** neighbors
