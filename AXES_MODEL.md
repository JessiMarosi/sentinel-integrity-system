# Sentinel Integrity System (SIS)
## AXES_MODEL.md

This document defines the **axis descriptor model** used by SIS.

The purpose of this model is not to measure risk.
It is to provide a **non-scoring vocabulary** for describing when irreversibility is emerging.

SIS must remain a physics system:
- no rankings
- no scores
- no probabilities
- no confidence
- no predictive claims

Descriptors are **directional**, not quantitative.

---

## 1. Model Principle: Describe, Dont Judge

Each axis is represented by a set of **descriptors**.

Descriptors are:

- local in meaning
- non-aggregating
- non-persistent
- non-attributable
- non-actionable without human choice

Descriptors must never be combined into a numeric output.
Descriptors must never be used to infer intent, blame, or correctness.

---

## 2. Descriptor Format (Normative)

Each descriptor is a record with the following fields:

- axis  one of: Irreversibility, Opacity, Asymmetry
- descriptor  a short canonical name
- direction  one of: Increasing, Stable, Decreasing, Unknown
- horizon  one of: Immediate, Near, Deferred, Unknown
- basis  a brief, non-identifying explanation of what condition is observed
- expiry  mandatory TTL after which the descriptor is discarded

Constraints:

- No user identifiers
- No system identifiers beyond local context
- No timestamps persisted beyond expiry needs
- No cross-event linking keys

---

## 3. Axis: Irreversibility (Descriptor Set)

Irreversibility describes **reversal difficulty increasing over time**.

SIS may use descriptors such as:

### 3.1 Reversal-Cost Escalation
Observed when reversal effort increases materially between successive decision points.

Examples (non-exhaustive):
- rollback complexity increases due to dependency chains
- restore requires more steps than prior baseline
- reversal requires coordination across more parties than before

### 3.2 Point-of-No-Return Formation
Observed when a change creates a state that cannot be cleanly returned to prior form.

Examples:
- destructive migrations without reversible mapping
- irreversible key rotation without escrowed recovery path
- write-once or append-only propagation without controlled rollback gates

### 3.3 Dependency Entanglement Growth
Observed when more systems become coupled to the decision.

Examples:
- expanding integration surface area
- increasing number of consumers dependent on the new state
- expanding blast radius of rollback

### 3.4 Temporal Lock-In
Observed when time itself becomes a constraint on reversal.

Examples:
- rollback windows shrinking
- irreversible commitments occurring faster than verification cycles
- coordination delays exceeding operational tolerance

### 3.5 Restore-Integrity Degradation
Observed when restore no longer implies return to known-good.

Examples:
- restore points missing, stale, or untrusted
- configuration drift invalidates rollback assumptions
- recovery plans are no longer aligned to current reality

---

## 4. Axis: Opacity (Descriptor Set)

Opacity describes **loss of human reasonability**.

SIS may use descriptors such as:

### 4.1 Explainability Decay
Observed when fewer humans can explain the change end-to-end.

Examples:
- logic distributed across multiple teams/tools
- handoffs fragment understanding
- it works replaces we can explain why

### 4.2 Responsibility Fragmentation
Observed when accountability becomes structurally unclear.

Examples:
- ownership boundaries are ambiguous
- decision authority is delegated without matching comprehension
- operational responsibility is separated from design authority

### 4.3 Verification Lag
Observed when verification cycles cannot keep pace with change.

Examples:
- deployment frequency exceeds audit/verification bandwidth
- testing becomes nominal rather than meaningful
- review becomes rubber-stamp due to tempo

### 4.4 Hidden Coupling
Observed when system behavior depends on interactions that are not explicit.

Examples:
- emergent behavior from multiple automation layers
- undocumented dependencies
- brittle behavior due to implicit order-of-operations

### 4.5 Irrecoverable Complexity
Observed when complexity crosses the threshold where rollback is not just hard, but unknowable.

Examples:
- no one can enumerate all affected components
- recovery relies on tacit knowledge
- unknown unknowns dominate

---

## 5. Axis: Asymmetry (Descriptor Set)

Asymmetry describes **unequal distribution of consequences**.

SIS may use descriptors such as:

### 5.1 Local Benefit / Global Exposure
Observed when benefits accrue to a narrow group while exposure spans broader populations.

Examples:
- speed improvements for one team increase systemic failure impact
- feature gains accrue locally while recovery costs are externalized

### 5.2 Insulated Decision Surface
Observed when decision-makers are structurally protected from consequences.

Examples:
- operational teams bear failures caused by upstream decisions
- affected parties cannot influence the decision chain
- reversal cost is borne by those without authority

### 5.3 Externalized Recovery Burden
Observed when recovery responsibility shifts away from those who benefit.

Examples:
- downstream teams must execute rollback without agency in the original decision
- customers or users bear the remediation burden

### 5.4 Cross-Boundary Blast Radius
Observed when failure propagates across organizational, legal, or jurisdictional boundaries.

Examples:
- cascading dependencies span vendors or agencies
- recovery requires coordination across entities with misaligned incentives

### 5.5 High-Impact Minority Harm
Observed when likely impacts are uneven even if overall impact appears acceptable.

Examples:
- edge-case harm dominates moral weight
- small populations face outsized risk from systemic change

---

## 6. Convergence Rule (Non-Scoring)

SIS may only justify an advisory when all are true:

- at least one Irreversibility descriptor is Increasing
- at least one Opacity descriptor is Increasing
- at least one Asymmetry descriptor is Increasing

No advisory may be justified by a single axis.
No advisory may be justified by a single descriptor.

SIS does not quantify how much.
SIS only recognizes that **three independent directions align**.

---

## 7. Anti-Drift Constraints (Hard)

The following are forbidden:

- numeric scoring of descriptors
- ranking decisions by descriptor count
- trend aggregation across time
- cross-event correlation IDs
- attribution links to humans
- storage beyond expiry
- use of SIS outputs as evidence or compliance signals

If any of the above appear, SIS has drifted into governance or surveillance.

---

## 8. TTL and Ephemerality Requirements

Every descriptor must expire.

Expiry is mandatory because:

- persistence creates leverage
- leverage creates authority
- authority invalidates SIS

The expiry horizon is implementation-defined, but must be short enough that
a descriptor cannot become an institutional memory.

---

## Closing Statement

This axis model is designed to be **useful without becoming powerful**.

SIS must remain a system that makes denial harder,
not a system that makes enforcement easier.

If future work turns descriptors into metrics, this document is violated.
