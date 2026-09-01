---
tags: [cybersecurity, smartcards, cryptography, authentication, pki]
notion_source: "https://www.notion.so/322fe6aa14b980f081e7c0c8db5bc89f"
last_synced: "2026-04-12"
---

# SmartCards

Related topics: [[cybersecurity-notes]], [[sentinel]].

## Overview

- Credit-card sized device containing a **microprocessor**
- Provides strong **2FA**: something you have (the card) + something you know (PIN)
- A **digital signature** is issued to the card using PKI (Public Key Infrastructure)
- Minimum of **2 PINs**: a user PIN and an admin PIN
- **CAD (Card Acceptance Device)** — the reader/terminal that interacts with the card

## Common Uses

- Windows smartcard login
- Secure VPN access
- Email signing and encryption
- Disk encryption
- Modern payment systems (credit/debit cards)

## Security

### Naive Approach (Vulnerable)

The card holds an ID number; the reading device simply checks it. This is vulnerable to replay attacks — anyone who captures the ID can reuse it.

### Challenge-Response Cryptosystem (Better)

1. The device sends the card a **challenge**
2. The card completes the challenge using its secret key
3. The device uses the ID number to look up the matching secret key and verify the response
4. **NONCE**: the device sends a NONCE (number used once) to the card; the card returns `Hash(secret_key + NONCE)` — this prevents replay attacks since the NONCE changes each time

## PKCS #11

A platform-independent API standard for interacting with cryptographic tokens such as smartcards and HSMs.

| Term | Definition |
|------|------------|
| **Token** | A hardware device that performs cryptographic operations (the card itself) |
| **Slot** | The physical interface where the token is inserted (the card reader) |
| **Session** | A new communication channel opened with a token |

- All cryptographic operations and key storage are attached to the **token**
- Almost every PKCS #11 function requires an open **session**
- Multiple concurrent sessions are possible in multi-threaded environments

## Java Card

A platform for running Java applications on smartcards.

### Java Card Runtime Environment (JCRE)

Consists of three components:

1. **Java Card VM (JCVM)** — a subset of the Java language with a VM optimized for smart card hardware
2. **Java Card Framework / APIs** — core libraries
3. **Extension APIs** — additional optional libraries

### Architecture

- A **card applet** behaves as a server and is **passive** — it responds to commands, it does not initiate them
- The CAD (terminal) acts as the client and drives the interaction

### Link Protocols

| Protocol | Type |
|----------|------|
| **T=0** | Byte-oriented |
| **T=1** | Block-oriented |
| **T=USB** | USB alternative |
| **T=RF** | Contactless / radio-frequency alternative |

### APDU (Application Protocol Data Unit)

- The logical data packet exchanged between the **CAD** and the **Java Card Framework**
- Commands flow from CAD to card (C-APDU); responses flow back (R-APDU)
