# Core design decisions: research proposal

**Proposed research dispositions; not adopted policy or protocol.** This
document records candidate choices for discussion before any schema or runtime
work.

## Basis and limits

[Decision 0002](../docs/decisions/0002-substrate-independent-reference-design.md)
and [Decision 0003](../docs/decisions/0003-pluggable-assessment-and-revision-research.md)
set research boundaries for source references, assessment, policy revisions,
replay, and failure. [The open research agenda](../OPEN_RESEARCH.md) identifies
remaining temporal, privacy, and dependency questions. [Current status](../STATUS.md)
states that no released protocol, stable schema, conformance suite, or reference
implementation exists.

**Source facts.** Source authority, derived data, evidence, policy-derived
assessment, retrieval rank, and procedural status are distinct. Candidate
policies must declare relevant inputs and fail closed when interpretation is
unsupported. No current source selects the choices below as normative policy.

**Synthesis.** The following dispositions provide a bounded starting point for
review. Each remains falsifiable and can be revised before implementation.

## Candidate dispositions

| Question | Proposed treatment | Counterexample or condition to revise |
| --- | --- | --- |
| Missing required time | Reject a precise temporal request if a required time dimension is absent, malformed, or contradictory. A separately requested weaker view may proceed only under a named policy that exposes the missing dimension and makes no unsupported temporal claim. | If the weaker view still uses missing time to select inputs or assert relevance, reject it too. Another evidenced time dimension may answer a different question; it cannot silently substitute. |
| Conflicting observations | Preserve conflicting in-scope observations where disclosure and retention permit; report unresolved conflict under a named policy. Do not select a winner by retrieval rank, recency, or implicit confidence. | If observations concern different propositions, scopes, or validity periods, treating them as conflict is misleading. A precedence rule requires explicit authority and separate review. |
| Revocation and redaction | Stop derived disclosure that relies on withdrawn access. Suppress even an unavailable marker if it leaks protected membership or a relationship. Treat any retained provenance as a separate, reviewed disclosure and retention choice. | A marker that reveals a sensitive relationship must be suppressed. A retention or erasure duty requires qualified evidence; this proposal does not resolve it. |
| Actor and scope | Declare only context needed to interpret a result and its intended disclosure. Reject a result that depends on missing or mismatched scope. | If identity or scope changes interpretation or access, an allegedly context-free result is not reviewable. A declaration does not authenticate or authorize an actor. |

## Open semantics

Reference identity, event ordering, dependency closure, supersession, policy
compatibility, error visibility, retention, serialization, and recovery remain
open. A later proposal must state alternatives, failure behavior, and a
counterexample for each choice. It must not promote these dispositions into
fields, error codes, a permission system, or an executable rule set by
implication.

Evidence remains distinct from policy-derived assessment. No universal
confidence value, source reliability score, truth determination, legal rule,
or access permission is proposed. This document claims no safety, alignment,
transfer, novelty, performance, or interoperability result.
