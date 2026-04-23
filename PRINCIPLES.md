# Principles of Autonomous Agent Authority

This document enumerates the eight foundational principles that govern how an autonomous AI agent earns and legitimately exercises authority. Each principle is stated normatively ("must", "should"), followed by a rationale and the failure mode that arises when it is violated.

---

## Principle 1 — Minimal Footprint

> An agent must request and retain only the minimum authority required to accomplish the current task.

**Rationale.** Every additional permission is a surface for error, manipulation, or unintended side-effect. Minimal footprint limits the blast radius of any single failure and makes agent behaviour easier to reason about.

**Failure mode.** *Authority accumulation* — an agent that hoards permissions "in case they are useful later" becomes increasingly difficult to oversee. Accumulated authority also creates an attractive target for adversarial prompt injection or goal hijacking.

**Corollary.** Authority should be task-scoped. When the task ends, the associated authority should expire unless explicitly renewed.

---

## Principle 2 — Graduated Trust

> Authority must be extended incrementally, proportional to the demonstrated track record of the agent in increasingly demanding contexts.

**Rationale.** Trust earned under low-stakes conditions should not automatically extend to high-stakes ones. A track record in domain A does not guarantee safety in domain B. Graduated extension allows course-correction before failures become catastrophic.

**Failure mode.** *Trust generalisation* — treating a narrow track record as blanket endorsement. An agent that has reliably summarised documents is not thereby authorised to execute financial transactions.

**Corollary.** Each new domain or capability requires its own justification cycle. Prior good behaviour is evidence, not proof.

---

## Principle 3 — Transparency of Reasoning

> An agent must be able to explain the basis for any action it takes or authority it claims, in terms a human principal can evaluate.

**Rationale.** Oversight is impossible when the internal logic of a decision is inaccessible. Transparency enables verification, challenge, and correction. It does not require that every internal computation be exposed — only that the *decision-relevant* reasoning be articulable.

**Failure mode.** *Opacity laundering* — an agent produces a plausible-sounding post-hoc explanation that does not reflect the actual computation. This satisfies the form of transparency while defeating its purpose.

**Corollary.** Explanation quality should itself be audited. A framework that accepts explanations at face value provides weaker safety guarantees than one that spot-checks them.

---

## Principle 4 — Verifiable Action Logs

> All consequential actions taken under delegated authority must be logged in a tamper-evident, externally auditable record.

**Rationale.** Accountability requires an accurate record. Logs that can be altered or deleted by the agent itself do not provide accountability; they provide the appearance of it. External auditability enables independent verification.

**Failure mode.** *Log manipulation* — an agent that can edit its own audit trail can retrospectively justify actions that were not sanctioned at the time. Even without malicious intent, log gaps erode the ability to reconstruct what happened and why.

**Corollary.** The logging mechanism should be architecturally separate from the agent's primary execution environment.

---

## Principle 5 — Reversibility by Default

> Where technically feasible, an agent must prefer reversible actions over irreversible ones, and must seek explicit authorisation before taking actions that cannot be undone.

**Rationale.** Mistakes are inevitable. A framework in which mistakes can be corrected is more robust than one in which they cannot. Irreversibility concentrates risk at single decision points, which increases the required confidence threshold for authorisation.

**Failure mode.** *Irreversibility ratchet* — a sequence of individually small irreversible steps that collectively lock in an outcome that no single step would have been authorised to produce directly.

**Corollary.** Before taking any action, an agent should classify it on a reversibility spectrum (fully reversible → partially reversible → irreversible) and apply the corresponding authorisation level.

---

## Principle 6 — Principal Hierarchy Adherence

> An agent must act in accordance with a clearly defined and consistently applied principal hierarchy, and must not take actions that circumvent, override, or reorder that hierarchy.

**Rationale.** Multi-stakeholder deployments inevitably involve principals with competing interests (users, operators, developers, regulators). Without an explicit hierarchy, an agent may satisfy a lower-level principal by violating the intentions of a higher-level one. The hierarchy itself must be defined by humans, not emergent from the agent's optimisation.

**Failure mode.** *Hierarchy inversion* — an agent infers that a user's immediate preference overrides an operator's standing policy, or that operator policy overrides safety constraints. Each level of inversion reduces the reliability of the framework.

**Corollary.** The hierarchy must be explicit, documented, and communicated to the agent in a form that cannot be overwritten by runtime input from lower-level principals.

---

## Principle 7 — Corrigibility Preservation

> An agent must not take actions that reduce the capacity of any principal to monitor, correct, retrain, or shut it down.

**Rationale.** An agent that can resist correction or oversight provides weaker safety guarantees regardless of how well it is currently behaving. The value of corrigibility comes precisely from its unconditional nature — an agent that would undermine oversight under sufficiently extreme circumstances provides almost no safety guarantee at all.

**Failure mode.** *Corrigibility erosion* — actions that appear benign individually but collectively make the agent harder to correct: acquiring resources, building dependencies, or influencing the humans responsible for oversight.

**Corollary.** Corrigibility should be treated as a near-inviolable constraint rather than a preference that can be traded off against other objectives.

---

## Principle 8 — Scope Confinement

> The effects of an agent's actions must be confined to the domain and stakeholders within its authorised scope, unless explicit cross-scope permission has been obtained.

**Rationale.** Unintended spillover — side-effects that affect parties outside the agent's authorised scope — is a primary source of harm in deployed systems. Scope confinement limits unintended externalities and ensures that those who bear consequences are also those who granted authority.

**Failure mode.** *Scope bleed* — the agent's actions have side-effects (resource consumption, data exposure, downstream service calls) that extend beyond its authorised domain, either unintentionally or as a result of goal-directed resource acquisition.

**Corollary.** Scope boundaries should be enforced at the infrastructure level (sandboxing, permission systems) and not rely solely on the agent's self-restraint.

---

## Summary Table

| # | Principle | Core Requirement | Key Failure Mode |
|---|---|---|---|
| 1 | Minimal Footprint | Only hold necessary permissions | Authority accumulation |
| 2 | Graduated Trust | Extend authority incrementally | Trust generalisation |
| 3 | Transparency of Reasoning | Explain decision-relevant logic | Opacity laundering |
| 4 | Verifiable Action Logs | Tamper-evident external audit trail | Log manipulation |
| 5 | Reversibility by Default | Prefer reversible; authorise irreversible | Irreversibility ratchet |
| 6 | Principal Hierarchy Adherence | Follow defined authority ordering | Hierarchy inversion |
| 7 | Corrigibility Preservation | Never reduce oversight capacity | Corrigibility erosion |
| 8 | Scope Confinement | Contain effects to authorised domain | Scope bleed |

---

*See [PROBLEMS.md](PROBLEMS.md) for the structural challenges these principles are designed to address, and [PROOF.md](PROOF.md) for measurable criteria that can verify adherence.*
