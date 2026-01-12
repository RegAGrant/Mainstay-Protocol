spec-v0.1.md

# Mainstay Protocol Specification — v0.1

Status: Draft Standard  
Classification: Normative

This document defines the minimum requirements for a protocol that cryptographically anchors Kaspa’s historical state to the Bitcoin blockchain.

Any implementation claiming compatibility with Mainstay v0.1 MUST conform to this specification.

---

## 1. Purpose

Mainstay exists to provide verifiable proof that a given Kaspa state existed at or before a specific Bitcoin block height.

Mainstay does not:

- move assets  
- custody funds  
- issue tokens  
- alter consensus rules  
- provide execution or governance  

Mainstay records history only.

---

## 2. Scope

This specification defines:

- checkpoint selection rules  
- Kaspa state root construction  
- Bitcoin commitment format  
- anchor validation rules  
- verification procedures  

This specification explicitly excludes:

- incentive mechanisms  
- token economics  
- governance models  
- scheduling policy  
- implementation details  

---

## 3. Terminology

**Checkpoint**  
A Kaspa block considered final under deterministic rules and selected for anchoring.

**Kaspa State Root**  
A cryptographic hash representing the deterministic Kaspa state at a checkpoint.

**Anchor**  
A Bitcoin transaction containing a commitment to a Kaspa State Root.

**Anchor Interval**  
A deterministic period during which anchors may be created.

---

## 4. Checkpoint Selection

### 4.1 Determinism

Checkpoint selection MUST be deterministic and reproducible.

Valid rules include:

- every N Kaspa blocks  
- every T minutes based on Kaspa timestamps  

Checkpoint selection MUST NOT depend on:

- governance decisions  
- manual triggers  
- external signals  

---

### 4.2 Finality

Only Kaspa blocks considered final under Kaspa consensus rules MAY be used as checkpoints.

Anchoring non-final state is forbidden.

---

## 5. Kaspa State Root Construction

### 5.1 Inputs

The Kaspa State Root MUST be derived from:

- block headers up to the checkpoint  
- DAG parent relationships  
- cumulative proof-of-work metadata  

### 5.2 Serialization

State serialization MUST be:

- deterministic  
- versioned  
- publicly documented  

### 5.3 Hashing

The serialized state MUST be hashed using a fixed cryptographic hash function producing a single fixed-length output.

This output is the Kaspa State Root.

---

## 6. Bitcoin Commitment

### 6.1 Commitment Method

Anchors MUST be published using:

- OP_RETURN output  
  or  
- provably unspendable output  

No Bitcoin output MAY be spendable by Mainstay.

---

### 6.2 Commitment Payload

The payload MUST contain:

- protocol version identifier  
- Kaspa State Root  
- optional verification metadata  

The payload MUST comply with standard Bitcoin relay limits.

---

### 6.3 Non-Interference Principle

Mainstay MUST NOT:

- lock BTC  
- wrap BTC  
- issue claims on BTC  
- require Bitcoin script changes  

Bitcoin remains sovereign and unaffected.

---

## 7. Anchor Creation

### 7.1 Open Participation

Any party MAY create and broadcast anchors.

No privileged operator exists.

---

### 7.2 Canonical Anchor

For a given checkpoint:

- the earliest valid anchor confirmed on Bitcoin is canonical  
- later anchors are non-canonical but verifiable  

No dispute mechanism exists beyond Bitcoin consensus ordering.

---

## 8. Verification Procedure

To verify a Kaspa state:

1. Reconstruct the Kaspa State Root at the checkpoint  
2. Locate the Bitcoin anchor containing that root  
3. Verify Bitcoin inclusion and block height  
4. Confirm timestamp ordering  

If all conditions hold, the Kaspa state is proven to have existed at or before that Bitcoin block.

---

## 9. Invalid Anchors

Anchors MUST be ignored if they:

- reference non-final Kaspa state  
- violate serialization rules  
- contain malformed payloads  

---

## 10. Versioning

All anchors MUST include a protocol version identifier.

Backward verification MUST be preserved where possible.

---

## 11. Upgrade Discipline

Protocol changes MUST:

- be publicly documented  
- preserve verification compatibility where possible  
- avoid automatic enforcement  

Mainstay favors stability over evolution.

---

## 12. Security Model

Mainstay assumes:

- Bitcoin immutability  
- Kaspa consensus correctness  
- cryptographic hash integrity  

No additional trust assumptions are introduced.

---

## 13. Explicit Non-Goals

Mainstay is not designed to:

- optimize transaction throughput  
- reduce fees  
- provide financial services  
- enable cross-chain execution  
- compete with Layer-2 systems  

---

## 14. Design Rule

> If a feature is not required to anchor Kaspa history to Bitcoin, it must not be added.

This rule supersedes all others.

---

## 15. Closing Statement

Mainstay is not a platform.  
Mainstay is not a network.  
Mainstay is not a market.

Mainstay is a cryptographic record.

