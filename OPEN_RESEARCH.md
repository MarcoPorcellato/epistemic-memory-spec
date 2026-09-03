# Open research agenda

This agenda records five initial tracks for a research draft.

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
