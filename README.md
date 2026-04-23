# Autonomous Agent Principles

A theory-level framework for how autonomous AI agents **earn** and **exercise** authority — covering foundational principles, structural problems, and measurable proof of trustworthy behaviour.

---

## Why This Framework Exists

As AI systems move from narrow tools to agents that plan, act, and delegate across open-ended tasks, the question of *authority* becomes critical. Who decides what an agent may do? How does it demonstrate that it deserves wider latitude? What happens when things go wrong?

This framework does not describe how any particular system works today. It describes what a sound theory of autonomous-agent authority *should* look like, so that researchers, engineers, and policy-makers share a common vocabulary when designing, auditing, or constraining such systems.

---

## Document Map

| Document | Purpose |
|---|---|
| [PRINCIPLES.md](PRINCIPLES.md) | The eight foundational principles that govern how authority is earned and exercised |
| [PROBLEMS.md](PROBLEMS.md) | The core structural problems that any authority framework must address |
| [PROOF.md](PROOF.md) | Measurable criteria and evaluation methods that turn principles into verifiable claims |

---

## Core Thesis

An autonomous agent earns authority incrementally through **demonstrated alignment, verifiable transparency, and accountable action** — not by assertion, and not all at once. Authority is a trust relationship maintained continuously, not a capability granted permanently.

Three claims follow from this thesis:

1. **Earning** — Authority must be justified by observable evidence of safe and aligned behaviour.  
2. **Exercising** — The use of authority must be bounded, logged, and proportionate to the task at hand.  
3. **Revocation** — Any authority grant must be reversible; the framework must specify how and when authority is reduced or removed.

---

## Relationship Between Documents

```
PRINCIPLES (normative)
       |
       v
PROBLEMS  ←→  PROOF
(what can go wrong)   (how to know if it went right)
```

Principles state what *should* be true. Problems describe what *can go wrong* when principles are not satisfied. Proof describes how to *measure* whether principles are being upheld in practice.

---

## Intended Audience

- **AI safety researchers** studying alignment and corrigibility  
- **ML engineers** designing agent architectures with access controls  
- **Policy-makers and auditors** setting standards for autonomous systems  
- **Anyone** building a system in which a software agent may take consequential real-world actions  

---

## Scope and Limitations

This framework is *theory-level*. It deliberately omits implementation details so that the principles remain applicable across different agent architectures, modalities, and deployment contexts. It does not address:

- Specific ML training methods  
- Hardware or infrastructure security  
- Legal liability (though it informs that discussion)  

---

## Contributing

Corrections, counter-examples, and proposed extensions are welcome via pull request. Each substantive change should cite a source or provide a worked example that tests the principle in question.
