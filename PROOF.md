# Empirical Evidence

*The framework's load-bearing claims are not asserted. They were tested. This file documents the experiment, one clear example per principle, and what was falsified.*

---

## The experiment

Build a **skill suite** that an AI agent runs on itself to improve itself, governed entirely by the three principles. The principles define the rules of the loop; convergence defines the exit. The experiment tests whether a self-improving skill suite — operating under nothing but these principles — can actually reach silence rather than churn forever.

The artifact under proof is the **skill suite**, not this manifesto. The manifesto is the rulebook; the skill suite is what was built under the rulebook and what survived running under it. Where this manifesto is used as an evaluation target below, it is a *test fixture* for the skill suite, not the artifact being proven.

This manifesto is implementation-agnostic. The evidence below comes from one specific implementation (the kata skills suite, a separate repository). One conformance, real but bounded.

---

## One clear example per principle

### Principle 1 — Commander's Intent

**The test.** The skill suite is written as missions, not procedures. The litmus test in [PRINCIPLES.md](./PRINCIPLES.md): *if you removed all specific examples and thresholds from a skill, would an intelligent agent still know what to do?* Three fresh model families (Anthropic, xAI/Grok, Google/Gemini) — none involved in authoring the suite — were each asked to apply it cold to a real target.

**What happened.** Each evaluator, given only the skills' missions, produced a coherent evaluation approach without external scaffolding. None reported the skills as underspecified. The suite directed independent reasoning across distinct model lineages without a checklist.

**What this shows.** A skill suite written as *what + why* (rather than as steps) is sufficient to direct fresh agents that did not participate in its design. That is the operational claim of Principle 1.

### Principle 2 — Observable Autonomy

**The test.** Every run of the skill suite produces a continuous, multi-resolution trail (full reasoning, indexed decisions, digested summary). The standing test: *can a human who was not present reconstruct what the agent did, why, and whether to trust the results, from the trail alone?*

**What happened.** After a closed convergence chain, a human review opened the trail cold and was able to reconstruct each evaluator's reasoning, locate decisions, and — critically — find a defect the chain had missed (see *What was falsified*). The defect was findable *because* the trail made the chain's reasoning inspectable after the fact.

**What this shows.** The trail did its job: it made invisible reasoning visible enough that an outside observer could audit it and surface a finding the loop had produced. Observability is what allowed falsification to occur at all.

### Principle 3 — Convergence Is Silence

**The test.** Run the skill suite to silence on a frozen artifact: three diverse evaluator families, fresh sessions, each independently finding nothing material to change. The skill suite either reaches silence or it doesn't — and "doesn't" is the failure mode the principle was written to expose.

**What happened.** Three evaluator families, evaluating a locked artifact in isolation, each independently recorded zero changes. The chain closed on silence rather than on a stabilizing score. The skill suite reached its own defined exit condition.

**What this shows.** A self-improving skill suite governed by these principles can actually stop. Silence convergence across diverse independent evaluators is achievable in practice — not proof of correctness, but evidence that the loop has an honest exit and reaches it.

---

## What was falsified

After the chain closed, human review of the same target found a cross-file contradiction all three evaluators had stepped past: a file in scope referred to one of the principles by a name that did not match [PRINCIPLES.md](./PRINCIPLES.md). A second instance of the same class — documentation drift surviving a closed convergence chain — was then found inside the skill suite itself.

This falsifies one specific (unstated) reading: *that family-diverse silence convergence implies the artifact is correct.* It does not falsify Principle 3 as written, which claims convergence is the **strongest external signal**, not a guarantee.

The recurring shape of the failure is now part of the record: the chain reads files for their first-order content and does not reliably test the second-order claims those files make about the rest of the repository. This is a property of the chain as currently operated, and it is exactly the kind of limit [PROBLEM.md](./PROBLEM.md) already names — independent evaluators reduce shared blind spots but do not eliminate them.

---

## What this evidence does and does not establish

| Claim | Status |
|---|---|
| A skill suite written as missions (not steps) can direct fresh evaluators' reasoning | Supported |
| A self-improving skill suite governed by these principles can reach silence | Supported |
| The trail makes after-the-fact reasoning inspectable by an absent observer | Supported (the falsification itself is the evidence) |
| The principles transmit across at least three distinct model families | Supported within the tested set |
| Silence convergence implies the artifact is correct | **Not supported. Falsified.** |
| Independent evaluators are immune to shared blind spots | **Not supported.** |

---

## A note on the development trail

The skill suite was not built in one sitting. It was derived through roughly one hundred self-targeting improvement runs and two structural rebuilds, during which the measurement framework was retired and replaced more than once. That history is genealogical evidence — it shows where the suite came from and that it can survive its own destructive scrutiny — but it is not what this document is proving. The proof above is against the **frozen** skill suite, exercised by parties that did not participate in its development.

A document that hid the falsification to protect the convergence claim would be the self-validating loop these principles were written to prevent. Both results are recorded here for the same reason.
