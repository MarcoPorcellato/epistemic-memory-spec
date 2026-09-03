# Decision 0002: Substrate-independent reference design

## Status

**Proposed research design.**

This decision defines a research direction and an evaluation boundary. It is
not a protocol, a conformance programme, an AAIF submission, or an
implementation commitment.

## Context

The research draft requires portable references, closed schemas, deterministic
replay, and rebuildable derived state. Matryca Plumber is useful evidence that
these ideas can be explored with Logseq-compatible Markdown and rebuildable
local acceleration. It is not sufficient evidence that the concepts are
independent of Logseq, Markdown, SQLite, or one implementation.

An additional reference design should test that independence. Its purpose is
not to replace Plumber, create a competing product, or move Plumber's source
authority. Its purpose is to test whether a small epistemic-memory contract can
survive different source systems, storage engines, and query surfaces.

## Decision

Research will evaluate a minimal, substrate-independent reference design with
these boundaries:

1. **Canonical record:** a versioned JSON event envelope validated by a
   declared JSON Schema revision.
2. **Canonical bytes:** UTF-8 JSON canonicalised under an explicitly pinned
   JCS/I-JSON profile before identifiers, hashes, or signatures are calculated.
3. **Integrity and replay:** immutable, hash-linked records with explicit
   stream identity, sequence, parent digest, schema identifier, policy
   identifier, and payload digest.
4. **Authority:** ordinary immutable record blobs plus an append-only manifest
   are the reference substrate. A source adapter remains responsible for
   identifying its canonical source; the ledger never becomes a hidden write
   authority.
5. **Projections:** Markdown, Logseq, SQLite, PostgreSQL, search indexes,
   JSON-LD/RDF, and token-efficient text renderings are optional, rebuildable
   views or adapters. None is required to read, validate, or replay the
   reference record.
6. **Transport and signatures:** CBOR/COSE may become an optional profile only
   after the canonical JSON profile and test vectors exist. A valid signature
   establishes origin/integrity under a declared key policy, not truth.

## Reference architecture

```text
source adapter
    Markdown | Logseq blocks | database rows | API records
        |
        | opaque, revision-bound source references
        v
canonical epistemic-event ledger
    JSON Schema | canonical bytes | hash chain | append-only manifest
        |
        +-- deterministic replay and validation
        |
        +-- rebuildable projections
              SQLite | PostgreSQL | JSON-LD/RDF | search | Markdown export
```

The ledger contains metadata and references, not an implied copy of a user's
private source corpus. Payload handling, scope binding, and retention must be
defined by a later privacy design before implementation.

## Optional token-efficient human and model projection

TOON (Token-Oriented Object Notation) is the first format worth evaluating as
an **experimental projection** for people and language models. It is a
line-oriented, deterministic encoding of the JSON data model that avoids
repeating field names for uniform records. That can make repeated evidence,
assessment, or event rows cheaper to place in an LLM context and easier to
scan.

It is not a replacement for canonical JSON. The TOON specification is a
Working Draft, token counts vary by corpus and tokenizer, and TOON itself notes
that deeply nested or non-uniform structures may be better represented as JSON.
Its role is therefore deliberately narrow:

- canonical record bytes, event identifiers, hashes, signatures, and replay
  remain JSON/JCS-based;
- a declared TOON encoder creates a projection from validated canonical data;
- any decoded TOON result must validate and normalise back to the same JSON
  data model before it is accepted as an equivalent representation;
- projections carry their format version, encoder version, and canonical-source
  digest; and
- a projection mismatch, malformed strict-mode document, or unsupported TOON
  revision is a validation failure, never a reason to change a canonical event.

No token-saving claim may be published without a versioned corpus, named
tokenizer, encoder configuration, and reproducible measurement procedure. The
first benchmark must compare canonical JSON, TOON, YAML, and JSON5 only as
input/projection formats; it must measure token count, bytes, round-trip
equality, malformed-input rejection, and structured-task accuracy separately.

YAML and JSON5 remain convenience import or authoring formats only. They must
be converted immediately through a restrictive parser into canonical JSON;
their presentation features, aliases, tags, comments, and relaxed syntax never
enter the integrity boundary.

## Minimum event envelope to investigate

The following fields are a research starting point, not a released schema:

| Field | Purpose |
| --- | --- |
| `event_id` | Stable identifier for one canonical envelope. |
| `stream_id` | Explicit replay and isolation boundary. |
| `sequence` | Monotonic event order within a stream. |
| `record_type` | Closed event kind. |
| `schema_id` | Exact structural and semantic revision. |
| `created_at` | Normalised record time; never inferred from filesystem metadata. |
| `prev_digest` | Parent binding, or an explicit stream root. |
| `payload_digest` | Integrity binding for declared payload bytes or a declared absent/redacted state. |
| `source_refs` | Opaque, revision-bound references to canonical-source material. |
| `policy_ref` | Named assessment policy and revision where applicable. |
| `status` | Declared lifecycle state, including redaction or tombstone state. |

Deterministic replay must reject duplicate or missing sequence numbers, broken
parent links, unknown schema revisions, malformed canonical bytes, and scope
or policy mismatches. It must never infer event order from modification time.

## Alternatives considered

### Logseq Markdown plus SQLite only

Keeps implementation close to Plumber, but does not demonstrate portability or
separate source authority from a specific local graph and database lifecycle.

### JSON-LD/RDF as canonical substrate

Strong graph interoperability option, but needs vocabulary, context, dataset
canonicalisation, and query-operational decisions before it can provide a
small replayable record. Keep it as a later projection/interchange profile.

### PostgreSQL as canonical substrate

Provides transactions and rich querying, but creates server, credential,
backup, migration, and operational dependencies. Keep it as a service
projection, not a portable reference substrate.

### CBOR/COSE as sole representation

Supports compact authenticated transport, but weakens direct inspection and
increases key-management requirements. Keep it optional and losslessly
projectable to the canonical JSON form.

## Privacy, deletion, and failure boundaries

Content addressing is not a deletion mechanism. Any future implementation must
separate and document:

- payload deletion;
- cryptographic erasure and key retention;
- retained hashes and metadata linkability;
- derived-index deletion and rebuild policy;
- backup and replication retention; and
- audit or legal-retention requirements.

Until these rules are designed and tested, the reference design must use
synthetic fixtures only. A malformed, unreplayable, or privacy-unsafe derived
record disables the optional feature; it must not block baseline source access
or create a canonical-source write path.

## AAIF posture

AAIF alignment is a research and governance posture, not a compliance claim.
This work can map future evidence to relevant themes such as interoperability,
observability, traceability, security, privacy, and governance. It must not
claim AAIF endorsement, hosting, certification, membership, regulatory
compliance, or standard status without separate public evidence and an
applicable AAIF decision.

If this research matures, credible external conformance should mean only that
an implementation passes a public, versioned suite for declared profiles. It
would not imply production safety, truth of content, or approval by any
foundation.

## Research anchors

This proposed design is informed by, but does not adopt, the following public
specifications and governance material:

- [RFC 8785: JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785.html)
  for repeatable JSON hashing and signing inputs;
- [JSON Schema Draft 2020-12](https://json-schema.org/draft/2020-12) for
  structural validation vocabulary;
- [JSON-LD 1.1](https://www.w3.org/TR/json-ld/) as a possible graph
  interchange projection;
- [RFC 8949: CBOR](https://www.rfc-editor.org/rfc/rfc8949.html) and
  [RFC 9052: COSE](https://www.rfc-editor.org/rfc/rfc9052.html) for optional
  compact and authenticated transport profiles; and
- [TOON Specification v4.1](https://github.com/toon-format/spec/blob/main/SPEC.md)
  for an experimental, token-efficient JSON projection; and
- [AAIF Project Lifecycle Policy](https://github.com/aaif/project-proposals/blob/main/governance/project-lifecycle-policy.md)
  for the distinction between transparent project governance and standards or
  conformance claims.

These sources do not define this event model, privacy policy, or conformance
programme. Those remain open research work.

## Advancement gates

Before creating code, a repository, or an implementation claim for this design,
the following must be reviewed and accepted in sequence:

1. threat model and privacy/retention decision;
2. closed v0 envelope schema and canonicalisation profile;
3. synthetic positive and negative conformance vectors;
4. deterministic replay and failure-semantics specification;
5. minimal independent reference implementation using only synthetic data;
6. a separate Plumber adapter or projection, without changing Plumber source
   authority; and
7. independent implementation or consumer evidence before any interoperability
   claim.

An optional TOON profile additionally requires a pinned specification revision,
strict-mode round-trip and negative vectors, canonical-digest equivalence
tests, and tokenizer-specific benchmark results. It remains experimental until
those results and an independent implementation review are public.

## Consequences

This direction increases credibility of an eventual agentic-memory standard by
testing its concepts outside one product and storage stack. It also deliberately
slows implementation: durability, concurrency, privacy, and recovery cannot be
assumed from a JSON file format or hash chain.

The next approved work, if any, should be a specification and vector plan for
items 1--4. It should not yet create a production service, declare an AAIF
submission, or change Matryca Plumber.
