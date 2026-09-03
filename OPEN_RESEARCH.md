# Open research agenda

This agenda records thirteen research tracks for a research draft.

Completion of any track adds research evidence only. It does not create a
standard, protocol, compatibility obligation, certification, or authority over
an underlying source of record.

## 1. Prior-art and terminology review
**Question:** Which existing work covers provenance-bound epistemic memory, source-of-record boundaries, and human governance, and where do terms differ?
**Required evidence:** Citable primary sources, stable links or identifiers, quoted definitions with context, and a comparison that distinguishes analogy from technical overlap.

## 2. Closed schema and canonical serialization
**Question:** What minimum closed schema and deterministic serialization could represent claims, evidence, policy revisions, uncertainty, and opaque source references without silently becoming a write authority?
**Required evidence:** A versioned schema proposal, canonical serialization rules, fixtures, rejection cases, and independent replay results.

## 3. Synthetic replay and malformed-input vectors
**Question:** Which synthetic inputs and malformed or adversarial vectors best test replayability, ordering, provenance binding, and fail-closed behaviour?
**Required evidence:** Public synthetic fixtures, expected outputs or errors, execution instructions, coverage rationale, and results from more than one independent implementation or review.

## 4. Privacy, retention, and scope-binding boundaries
**Question:** What privacy, retention, deletion, and scope-binding rules keep derived memory from exposing or overruling user-owned source records?
**Required evidence:** Threat and misuse cases, data-flow boundaries, retention and deletion scenarios, synthetic examples, and documented human review criteria.

## 5. Independent implementation and external review criteria
**Question:** What evidence would make an implementation or external review meaningful without implying compatibility, certification, or adoption?
**Required evidence:** Reproducible implementation notes, review protocol, independent findings, known limitations, and explicit versioning gates.

## 6. Substrate-independent reference design
**Question:** Can a small canonical event ledger preserve epistemic-memory
boundaries independently of Logseq, Markdown, SQLite, and a single product?
**Required evidence:** A reviewed threat model; closed schema and
canonicalisation profile; synthetic positive and negative vectors; deterministic
replay rules; a minimal independent implementation; and separate adapter or
projection evidence without changing source authority.

## 7. Token-efficient human and model projections
**Question:** Can an optional text projection reduce model-context tokens while
preserving exact canonical-record semantics and safe failure behaviour?
**Required evidence:** A pinned format profile; synthetic corpus; named
tokenizers and encoder settings; JSON/TOON round-trip and negative vectors;
canonical-digest equivalence checks; measured token and byte counts; and an
independent implementation review. No universal saving or compatibility claim
follows from a format conversion alone.

## 8. Assessment policies and uncertainty boundaries
**Question:** What closed, versioned policy contract can represent qualitative
or other declared assessment semantics without turning a derived projection
into a universal truth or confidence system?
**Required evidence:** A precise vocabulary for status, assessment,
uncertainty, source reliability, actor, and time; declared policy inputs and
outputs; rejection cases; synthetic vectors; reproducible replay; and a
prior-art comparison that names overlap and non-novelty.

## 9. Provenance-preserving revision and dependency closure
**Question:** How can a revision, challenge, or supersession identify affected
claims and dependencies without silently rewriting history or automatically
refuting downstream claims?
**Required evidence:** Closed event and dependency semantics; synthetic
supersession, challenge, conflict, redaction, and malformed-input vectors;
deterministic review outputs or errors; privacy limits; and independent review
of the exact vectors.

## 10. Cost- and provenance-aware question selection
**Question:** Can a system identify the next useful evidence request while
keeping information value, retrieval preference, model output, and truth
distinct?
**Required evidence:** A declared objective and cost model; synthetic decision
corpora; comparisons with fixed or random baselines; provenance for every
candidate question; human-review and refusal paths; and version-bounded results.

## 11. Higher-order provenance and meta-claims
**Question:** How should the record represent claims about sources, evidence,
assessments, and policies without confusing those meta-claims with the
underlying source content?
**Required evidence:** Typed examples and counterexamples; scope and privacy
rules; provenance queries; rejection cases; deterministic replay tests; and a
prior-art comparison with provenance and argumentation models.

## 12. Reproducible temporal reconstruction
**Question:** What minimum representation distinguishes source revision,
observation time, recorded time, assessment time, and valid time so a past
derived view can be reconstructed or rejected honestly?
**Required evidence:** A time vocabulary; clock, ordering, and missing-time
policy; synthetic temporal and out-of-order vectors; replay outputs or errors;
and documented limits on causal and real-world-time interpretation.

## 13. Provenance-aware multi-agent coordination
**Question:** Under what explicit identity, authority, disclosure, consent,
privacy, and conflict conditions could separate actors exchange bounded
epistemic records?
**Required evidence:** A separate reviewed threat model and governance
decision; identity and authority assumptions; disclosure and data-minimisation
rules; synthetic conflict and abuse cases; versioned interoperability vectors;
and independent evaluation. A single-user ledger is not evidence for this
track.
