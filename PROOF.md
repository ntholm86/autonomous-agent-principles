# Empirical Evidence

*The framework's load-bearing claims are not asserted. They were tested. This file documents what was tested, what survived, and what failed.*

This manifesto is implementation-agnostic. The empirical record below comes from one specific implementation (the kata skills suite, a separate repository) running against this manifesto repository. The implementation is one possible conformance; the evidence is real but bounded.

## Provenance

These principles were not designed in one sitting. They were derived through approximately one hundred self-targeting improvement runs and two full structural rebuilds of the implementing skill suite, during which the measurement framework itself was retired and replaced twice. The full development trail — every run, every retired rubric, every reversal — is preserved in the kata repository and is itself a record of the framework operating on itself.

That trail is **genealogical evidence**: it shows where the principles came from and that the framework can survive its own destructive scrutiny (Kaikaku in action). It is not **independent validation**, because the loop validating the principles was the same loop the principles describe. The clean-room test below was the first attempt to evaluate the principles against evidence that did not come from inside that loop.

## What was tested

In April 2026, three independent evaluator families (Grok, Gemini, GPT) were each given a fresh conversation, the locked manifesto repository (`PROBLEM.md`, `PRINCIPLES.md`, `README.md`), and a single instruction: derive an evaluation scheme cold from the principles, then evaluate the manifesto against it. No prior scores, rubrics, or framings were provided. Each ran in isolation; none consulted the others.

This was a test of three claims simultaneously:

1. **Commander's Intent (Principle 1).** Could a fresh model family, given only the philosophy and a mission, derive a coherent evaluation approach — or would it stall without a checklist?
2. **Convergence Is Silence (Principle 3).** Would three diverse independent evaluators converge on the same outcome?
3. **Cross-family portability.** Would the principles transmit across distinct model lineages, or were they overfit to the family that authored them?

## What survived

**Commander's Intent held.** Each evaluator, given only the philosophy and a mission, produced a coherent evaluation approach without an external checklist. None reported the philosophy as underspecified for the task. The principles transmitted enough to direct action.

**Three-peg silence convergence held.** All three evaluator families, evaluating the same locked manifesto, independently recorded zero changes. This satisfied the minimum bar defined in `PRINCIPLES.md` Principle 3 (3 consecutive runs, 3 distinct evaluator families, zero artifact changes, with at least one re-derivation of the measurement scheme converging with the inherited scheme).

**Cross-family portability held within the tested set.** Three model families from different lineages produced compatible outcomes, supporting the claim that the principles are not narrowly overfit to a single family's habits. The test does not extend beyond the three families actually evaluated.

## What failed

After the convergence chain closed, a human review of the same manifesto found a cross-file contradiction that all three convergence runs had missed: a file in scope for the chain referred to one of the principles by a name that did not match the name in `PRINCIPLES.md`. Three independent evaluator families, looking at the same files, all stepped past the same defect.

This is not a refutation of Convergence Is Silence. It is a falsification of an unstated stronger claim — that family-diverse session-independent convergence implies artifact correctness. The principle as written in `PRINCIPLES.md` does not make that claim; it says convergence is the **strongest external signal the framework can produce**, not a guarantee. The empirical evidence is consistent with the principle as written and inconsistent with any stronger reading of it.

The unsolved limit this exposes is the one `PROBLEM.md` already names: *evaluator independence and diversity reduce shared blind spots but do not eliminate them.* Today's event is concrete evidence that this open problem is real, not theoretical.

A second instance of the same class was subsequently found in the implementing skill suite (kata repo, v3 convergence chain, April 2026): the chain's three independent evaluators each read `trail/README.md` during their runs and stepped past a documentation drift in which the file described a retired three-file trail structure and a Glossary listing skill names that no longer exist in v3. The defect was found by human review during publication preparation, after the chain had closed. Two instances in two repositories within the first month of operation indicate this is a recurring failure mode of the convergence chain, with a specific shape: cross-file claims-vs-reality drift in surrounding documentation, where the chain reads files for their first-order content and does not test second-order claims those files make about the rest of the repository. This is a property of the chain as currently operated, not a defect in any single principle.

## What this evidence does and does not establish

| Claim | Status |
|---|---|
| Philosophy alone (without a checklist) can direct a fresh evaluator's reasoning | Supported |
| Diverse independent evaluators can independently converge on the same outcome | Supported |
| The principles transmit across at least three distinct model families | Supported |
| Convergence Is Silence implies the artifact is correct | **Not supported. Falsified by this test.** |
| Convergence Is Silence is the strongest external correctness signal the framework can produce | Consistent with this test |
| Independent evaluators are immune to shared blind spots | **Not supported. The open problem `PROBLEM.md` names is real.** |

## Why this matters

The framework's value is not that it guarantees correctness — it does not, and the evidence shows it does not. Its value is that it produces an evidence substrate where the limits of what is known are themselves visible. The convergence chain produced real evidence. The human review revealed a defect that survived the chain. Both are now part of the record, and both are accessible to any future observer at the resolution they need.

A framework that hid the second event to protect the claims of the first would be exactly the kind of self-validating loop the principles were written to prevent.
