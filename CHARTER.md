# Charter

## Purpose

Develop a careful public research record for epistemic memory: an optional,
derived layer that can explain how a system represents claims, evidence,
assessments, revisions, and uncertainty while preserving the authority of the
underlying human or host-owned source.

## Scope

In scope:

- terminology and non-goals;
- privacy-safe, opaque-reference data concepts;
- deterministic replay requirements;
- provenance and revision semantics;
- synthetic fixtures, test vectors, and future conformance criteria; and
- evidence required for responsibly evolving a research draft into a technical
  specification.

Out of scope:

- selecting a universal truth-maintenance algorithm;
- defining a model-training or reinforcement-learning system;
- writing into user-owned knowledge sources;
- host-specific database, transport, sync, event, or locking contracts;
- certification, trademark programmes, or compatibility badges; and
- claims of legal priority, ownership, or exclusivity.

## Design discipline

1. Preserve source authority. Derived records cannot silently overwrite a
   canonical source.
2. Keep evidence, assessments, and retrieval rank distinct.
3. Make policy identity and revision inspectable.
4. Prefer qualitative, bounded semantics before numerical confidence claims.
5. Require reproducible evidence before expanding scope.
6. Fail closed for the optional epistemic feature; baseline source reads remain
   independently available.

## Change process

Changes begin as issues containing a problem statement, a proposed change,
counterexamples or prior art where relevant, and test implications. A change is
not normative until a versioned draft, fixtures, and review criteria have been
published. Major scope changes require an explicit status update.

## External engagement

This repository welcomes critique, prior art, implementation feedback, and
counterexamples. It does not speak for any external project or organisation.
Any future collaboration, governance group, or standards process requires a
separate public decision.

Licensing grants reuse rights, not standards authority. This repository has no
consensus process, certification programme, or compatibility badge.
