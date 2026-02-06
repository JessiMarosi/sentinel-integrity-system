# Sentinel Integrity System (SIS)
## BOUNDARIES.md

This document defines the **non-negotiable integrity boundaries** of the Sentinel Integrity System (SIS).

These boundaries are not implementation preferences.
They are **structural constraints** that define what SIS is allowed to be.

Any system, component, extension, or future work that violates these boundaries is **not SIS**, regardless of intent.

If a conflict arises between implementation convenience and this document, **this document wins**.

---

## 1. Purpose of Boundaries

SIS exists to surface conditions of **irreversible integrity risk** before harm occurs, without:

- policing humans
- enforcing outcomes
- assigning blame
- generating evidence
- participating in governance

Boundaries exist to ensure SIS cannot driftaccidentally or intentionallyinto domains that would invalidate its core function.

SIS is not neutral infrastructure.
It is **deliberately constrained infrastructure**.

---

## 2. Domain Boundary: What SIS Is Allowed to Observe

SIS may observe **trajectory**, not state.

SIS may reason about:
- direction of change
- convergence of risk conditions
- temporal proximity to irreversibility

SIS must not reason about:
- intent
- correctness
- compliance
- justification
- outcome quality

SIS operates **before**:
- violations can be asserted
- policies apply cleanly
- evidence exists
- attribution is possible

Any logic that depends on post-hoc interpretation violates this boundary.

---

## 3. Human Boundary: What SIS Must Never Do to People

SIS must never:

- name individuals
- identify decision-makers
- profile users
- infer intent
- evaluate behavior
- store decision rationale
- store decision outcomes

SIS does not hold people accountable.
SIS exists precisely because accountability often arrives too late.

Any feature that allows SIS output to be mapped back to a person (outside the sole attribution exception defined below) violates SIS integrity.

---

## 4. Authority Boundary: What SIS Is Forbidden to Enforce

SIS has **no authority**.

SIS must never:

- block actions
- approve actions
- deny actions
- gate access
- escalate automatically
- trigger enforcement
- initiate investigations
- generate tickets
- notify regulators
- notify management by default

SIS introduces **friction**, not force.

If SIS output can compel action without human choice, the system has crossed into enforcement and is no longer SIS.

---

## 5. Data Boundary: What SIS Is Forbidden to Produce or Store

SIS must never produce:

- evidence
- scores
- rankings
- risk ratings
- confidence levels
- probabilities
- compliance signals
- audit artifacts
- forensic artifacts

SIS must never store:

- historical decision chains
- longitudinal user data
- outcome-correlated records
- cross-tenant inferable artifacts
- replayable decision context

SIS output must be **ephemeral, non-aggregating, and non-correlatable**.

Persistence is not a neutral choice.
Persistence is power.

SIS refuses that power.

---

## 6. Logging Boundary (Strict)

SIS logging exists **only** for system integrity, not oversight.

Allowed log events:

1. System enablement
2. System disablement
3. Advisory issuance (anonymous)

### Sole Attribution Exception

A user identifier may be logged **only** when SIS itself is:

- disabled
- degraded
- bypassed

Reason:

Disabling SIS removes pre-harm protection.
Anonymous removal of protection invalidates system integrity.

Required fields on shutdown logging:

- user identifier
- timestamp
- scope (partial / full)
- stated reason
- optional re-enable condition

No other attribution is permitted.

If additional attribution exists, SIS integrity is compromised.

---

## 7. Separation Boundary: Downstream Consumption Prohibition

Anything produced by SIS must **never** be consumed directly by:

- governance systems
- compliance platforms
- HR systems
- IAM systems
- SIEMs
- ticketing systems
- forensic pipelines
- audit tooling
- incident response workflows

This separation is intentional and permanent.

If SIS output becomes admissible evidence, it has failed.

---

## 8. Intelligence Boundary: What SIS Must Not Become

SIS must not contain:

- AI agents
- machine learning models
- adaptive scoring logic
- predictive classifiers
- self-optimizing feedback loops

SIS does not predict outcomes.
SIS surfaces **conditions where outcomes stop being reversible**.

Intelligence that optimizes behavior trends toward control.
SIS must remain a physics system, not a decision system.

---

## 9. Centralization Boundary: Trust Assumptions

SIS assumes:

- partial infrastructure compromise is possible
- cloud isolation may fail
- platform operators are not fully trusted
- centralized authority cannot be relied upon

Therefore:

- advisory meaning remains local
- artifacts are non-inferable cross-tenant
- no global aggregation exists
- ephemerality is a security property

A system designed to surface trust collapse must not rely on unexamined trust.

---

## 10. Drift Detection Clause

If at any point SIS is described as:

- governance
- compliance
- monitoring
- ethics enforcement
- safety enforcement
- oversight tooling
- risk management
- accountability infrastructure

Then SIS has already drifted.

Drift is not a future risk.
Drift is the default failure mode.

Boundaries exist to prevent it.

---

## 11. Amendment Rule

These boundaries may only be amended if:

- the amendment is explicit
- the amendment is documented
- the amendment explains which integrity property is being sacrificed
- the amendment is acknowledged as a departure from original SIS doctrine

Silent boundary erosion is forbidden.

---

## Closing Statement

SIS is valuable precisely because of what it refuses to do.

Any system that does more by violating these boundaries does not strengthen SIS.
It replaces SIS with something easierand far more dangerous.

Integrity is not added.
Integrity is preserved.
