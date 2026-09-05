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
- **Projections are designed to be replayable.** A future specification must
  define ordered inputs, policy revisions, fixtures, and tests that reproduce
  a derived result.
- **Human governance is a design requirement.** Derived state cannot become a
  canonical write path without a separate, evidence-backed design.
- **Portable contracts are intended to reduce exposure.** Public records use
  opaque references and digests; they do not require raw source content,
  prompts, paths, or credentials.

## Repository contents

- [Status](STATUS.md) — current maturity and decision boundaries.
- [Charter](CHARTER.md) — scope, governance, and advancement criteria.
- [Research Draft v0](spec/epistemic-memory-research-draft-v0.md) — proposed
  concepts and non-goals.
- [Decision 0002](docs/decisions/0002-substrate-independent-reference-design.md)
  — proposed substrate-independent reference design.
- [Decision 0003](docs/decisions/0003-pluggable-assessment-and-revision-research.md)
  — proposed policy-plug-in boundary for assessment and revision research.
- [Decision 0004](docs/decisions/0004-incubating-strategic-agent-learning.md)
  — incubated boundary for research on explicit strategic learning.
- [Provenance](PROVENANCE.md) — public antecedents and exact source anchors.
- [Citation metadata](CITATION.cff) — how to cite this research record.
- [Governance](GOVERNANCE.md) — maintainer model and decision boundaries.
- [Versioning](VERSIONING.md) — draft and research maturity terms.
- [Open research](OPEN_RESEARCH.md) — agenda and evidence gates.
- [Accelerated Agent Learning](research/accelerated-agent-learning.md) —
  non-normative strategic-learning research track.
- [Multimodal cognitive scaffolding pre-admission programme](research/multimodal-cognitive-scaffolding-programme.md)
  and [evidence review](research/multimodal-cognitive-scaffolding-pre-admission-review.md)
  — non-normative pre-admission research with no decision or track authority.

## Start here

- [Start Here](START_HERE.md) — choose a researcher, implementer, or reviewer path.
- [Research map](docs/research-map.md) — document authority and reading order.
- [Evidence and review](docs/evidence-and-review.md) — evidence ladder and review boundary.
- [Latest research snapshot](https://github.com/MarcoPorcellato/epistemic-memory-spec/releases/latest)
- [Discussion #7](https://github.com/MarcoPorcellato/epistemic-memory-spec/discussions/7)
- [Issue chooser](https://github.com/MarcoPorcellato/epistemic-memory-spec/issues/new/choose)
- [Citation metadata](CITATION.cff) · [License map](LICENSE.md)

## Participate

Read [CONTRIBUTING.md](CONTRIBUTING.md) and [OPEN_RESEARCH.md](OPEN_RESEARCH.md).
Use the [issue chooser](https://github.com/MarcoPorcellato/epistemic-memory-spec/issues/new/choose)
for evidence-backed work. Use [Discussions](https://github.com/MarcoPorcellato/epistemic-memory-spec/discussions)
for exploratory dialogue. Issues are for concrete evidence, counterexamples,
prior art, and implementation feedback; Discussions are for open-ended
exploration.

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

## License

Reuse terms and file allocations are defined in [LICENSE.md](LICENSE.md).
