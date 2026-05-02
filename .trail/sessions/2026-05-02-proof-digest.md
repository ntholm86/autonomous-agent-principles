# 2026-05-02 — proof-digest

fidelity: reconstructed

## Request

"lets go" — underspecified ask with manifesto vision.md open.

## Examination

Bootstrap fired (underspecified ask, v3.7.0 mechanism). Formed three hunches from vision + trail tail:

1. PROOF.md conformance protocol might not yet give an external reader enough to test conformance in their own context (vision's stated gap).
2. The README introduction of the skills/manifesto relationship might be minimal.
3. The "how to conform" section placement was still an open question per vision.

Prioritized question: Does PROOF.md give an external reader enough to test conformance in their own context?

Read PROOF.md in full. The "How conformance is tested" section is correct and domain-agnostic. But: PROBLEM.md and PRINCIPLES.md both have a `## Digest (60 seconds)` section as the first-contact, extractable summary. PROOF.md did not. This breaks the established manifesto pattern and makes the three conformance tests impossible to cite in one breath — directly at odds with the vision destination ("as citable as SOLID").

Three-lens result:
- **Inconsistency**: PROOF.md was the only file in the manifesto without a Digest section. The pattern is defined by PROBLEM.md and PRINCIPLES.md and is the manifesto's established first-contact format.
- Overburden: none.
- Waste: none.

## Decisions and Realizations

[!DECISION] Add `## Digest (60 seconds)` to PROOF.md with three one-line conformance tests, one per principle, immediately after the intro paragraph.
Rationale: matches the established manifesto pattern; makes the conformance protocol extractable without requiring the full test prose; closes the gap between "domain-agnostic protocol" and "citable."
Alternative: add a summary table to the "How conformance is tested" section instead — rejected, pattern break; the Digest is the established first-contact form and it should precede, not be embedded in, the detail.

[!REALIZATION] All four manifesto files now have Digest sections. The reading-order table in README.md already describes PROOF.md as "How to test conformance for each principle" — the Digest makes that claim immediately redeemable rather than requiring the reader to parse the full test prose first.

## Actions

- Added `## Digest (60 seconds)` to PROOF.md: three one-line conformance tests with a closing note "These tests are domain-agnostic. Apply them to your own system."
- Committed 12812ee.

## Reflection

Falsifiable claim: a reader who arrives at PROOF.md and reads only the Digest (60 seconds) can now state all three conformance tests accurately, without reading the full protocol section.

Blind spot: the one-line tests use vocabulary (trail, loop, evaluator family) that is defined in PRINCIPLES.md. A reader who starts at PROOF.md rather than following the reading order may still need the README's reading-order guidance.

Imagined-reader pushback: the occasion-independence bootstrap worked correctly here — underspecified ask, agent formed hunches, identified the highest-confidence structural gap, proceeded to fix it. But this is the same agent/session-family as prior manifesto runs. The reliability test still requires a different arc.
