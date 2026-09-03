# Epistemic Memory Spec

## Research draft, not a standard

This repository records a public research direction for provenance-bound,
human-governed epistemic memory in human-and-agent systems.

It is **not** a standards body, a conformance programme, a production API, or
an interoperability promise. No implementation may claim compatibility with
this work unless a future, explicitly versioned specification defines the
claim and its tests.

## Why this exists

Retrieval can find relevant material. It does not, by itself, say whether a
statement is an observation, a claim, a human confirmation, a stale assertion,
or an assessment derived under a named policy. This research explores a small,
inspectable layer that preserves those distinctions without replacing a
user-owned source of record.

The working hypothesis is:

> A useful agent memory records what it currently assesses as a claim, the
> evidence that supports or challenges it, the policy and revision that
> produced the assessment, and the uncertainty that remains.

## Core commitments

- **Canonical sources remain authoritative.** A derived memory projection must
  not silently replace a user's graph, documents, or host-defined database.
- **Evidence is not belief.** A retrieval hit, model output, or event is not a
  verified fact merely because it exists.
- **Policy is explicit.** Assessment semantics, revisions, and limits must be
  named and testable.
- **Projections are replayable.** The same ordered inputs and policy revision
  must reproduce the same derived result.
- **Human governance is preserved.** Derived state cannot become a canonical
  write path without a separate, evidence-backed design.
- **Portable contracts protect privacy.** Public records use opaque references
  and digests; they do not require raw source content, prompts, paths, or
  credentials.

## Repository contents

- [Status](STATUS.md) — current maturity and decision boundaries.
- [Charter](CHARTER.md) — scope, governance, and advancement criteria.
- [Research Draft v0](spec/epistemic-memory-research-draft-v0.md) — proposed
  concepts and non-goals.
- [Provenance](PROVENANCE.md) — public antecedents and exact source anchors.
- [Citation metadata](CITATION.cff) — how to cite this research record.

## Relationship to Matryca projects

This research was seeded by design work in
[Matryca Plumber](https://github.com/MarcoPorcellato/matryca-plumber), where
Markdown remains a semantic source of record and Shadow DB state is
rebuildable acceleration. This repository extracts portable research concepts;
it does not transfer Plumber runtime evidence, endorse an implementation, or
make a standards claim. Exact anchors are recorded in [PROVENANCE.md](PROVENANCE.md).

## How to read and discuss it

Read [STATUS.md](STATUS.md) before treating any term as a requirement. Raise a
GitHub issue for a concrete concern, counterexample, or prior-art reference.
Discussion is welcome; acceptance of a suggestion does not by itself create a
normative specification or a conformance obligation.

## License status

No license grant has been selected for this early research record. Public
visibility does not grant permission to reuse the material beyond rights that
applicable law or the GitHub Terms of Service provide. A future licensing
decision will be explicit and versioned.
