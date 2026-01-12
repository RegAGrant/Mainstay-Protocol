
# Mainstay — Frequently Asked Questions

---

## What is Mainstay?

Mainstay is a proposed protocol that cryptographically anchors Kaspa’s historical state to the Bitcoin blockchain.

It provides verifiable proof that a given Kaspa state existed at or before a specific Bitcoin block height.

---

## Is Mainstay a blockchain?

No.

Mainstay does not maintain accounts, balances, transactions, or execution.

It only records cryptographic commitments.

---

## Does Mainstay move Bitcoin or Kaspa?

No.

Mainstay does not move, lock, wrap, or custody any assets.

It records hashes only.

---

## Is Mainstay a bridge?

No.

Mainstay does not transfer assets, messages, or execution between chains.

It records proof-of-existence only.

---

## Does Mainstay have a token?

No.

Mainstay is a protocol standard, not a monetary asset.

---

## Does Mainstay compete with Bitcoin?

No.

Bitcoin remains the settlement layer.

Mainstay references Bitcoin as the final historical record.

Bitcoin is not altered.

---

## Does Mainstay compete with Kaspa?

No.

Kaspa consensus, execution, and transaction flow are unchanged.

Kaspa does not depend on Mainstay to operate.

---

## Why is Mainstay needed?

Kaspa provides speed and scalability.

Bitcoin provides long-term immutability.

Mainstay allows Kaspa history to inherit Bitcoin’s historical finality without altering either system.

---

## Why not use Lightning or sidechains?

Lightning optimizes payments.

Sidechains introduce custody or peg risk.

Mainstay addresses historical finality only.

These systems solve different problems.

---

## Who controls Mainstay?

No one.

Any party may publish anchors.

Any party may verify anchors.

No authority assigns validity beyond Bitcoin consensus.

---

## What happens if Mainstay disappears?

All anchors already recorded on Bitcoin remain verifiable forever.

Mainstay has no central dependency.

---

## What prevents bad anchors?

Verification rules are deterministic.

Anchors that reference invalid Kaspa state or violate the specification are ignored.

No governance or dispute process is required.

---

## Can multiple anchors exist?

Yes.

Bitcoin ordering determines canonical anchors.

Later anchors remain verifiable but non-canonical.

---

## What is the business model?

There is none.

Mainstay is infrastructure, not a product.

---

## Can Mainstay evolve?

Yes, but only through documented specification revisions that preserve backward verification where possible.

Stability is prioritized over change.

---

## Is Mainstay experimental?

Mainstay is a draft standard.

It proposes rules before implementations.

---

## Who should implement Mainstay?

Anyone.

Mainstay is designed to be implemented independently by multiple parties.

---

## Why is Mainstay so minimal?

Because complexity introduces power.

Mainstay exists to record history, not to control it.

---

## Final clarification

Mainstay does not promise outcomes.

Mainstay provides structure.

