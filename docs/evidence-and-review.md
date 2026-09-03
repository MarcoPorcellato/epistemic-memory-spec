# Evidence and Review

## Evidence ladder

1. A clearly bounded claim or research question.
2. A primary source, synthetic fixture, or reproducible counterexample.
3. A documented interpretation that separates evidence, inference, and limits.
4. Maintainer review against the applicable maturity gate.
5. A published versioned draft only when its stated evidence exists.

Progress up this ladder is conditional: a later step does not repair missing
evidence at an earlier step.

## Evidence classes

- **Hypothesis:** a proposed explanation, constraint, or research direction;
  it is explicitly provisional and requires testing.
- **Cited prior art:** a traceable external source, with enough context to
  distinguish the source's claim from the repository's interpretation.
- **Synthetic replay:** a public, non-sensitive fixture and reproducible
  procedure whose expected result can be checked independently.
- **Implementation evidence:** observations from a named implementation,
  including version, inputs, outputs, and known limitations; it does not by
  itself establish general behaviour.
- **Independent interoperability evidence:** separately produced evidence
  that two implementations or reviews agree on an explicitly bounded fixture;
  it does not imply compatibility beyond that fixture and version.

## Review boundaries

Review records the evidence considered, the interpretation, unresolved limits,
and the maturity gate applied. Review may reject, narrow, or request more
evidence; acceptance records a research decision, not a universal conclusion.
Claims about schemas, replay, privacy, provenance, or implementations remain
bounded by their fixtures, versions, and stated assumptions.

## Privacy and public-record boundary

Use public sources and synthetic data in published evidence. Do not publish
private prompts, credentials, vault content, customer data, personal data, or
local paths. A source-of-record owner retains authority over that source;
derived research material must not expose, overwrite, or overrule it. Redact or
replace sensitive material with a synthetic fixture before requesting review.

## What acceptance does not mean

Acceptance of evidence does not establish truth, endorsement, standard status,
certification, conformance, compatibility, or authority to alter a canonical
source. It only records that the bounded evidence was reviewed against the
stated maturity gate and limits at that time.
