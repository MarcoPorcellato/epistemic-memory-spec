# Epistemic Memory Research Draft v0

## Status

Non-normative research draft. This document defines a shared vocabulary and a
testable direction; it does not define a product API, external protocol, or
conformance claim.

## Problem

An agent may retrieve relevant material yet remain unable to explain whether a
statement is source content, a derived claim, a human confirmation, a
challenge, or an assessment under a named policy. Treating these as one kind
of memory risks stale reuse, score inflation, opaque learning, and accidental
promotion of model output into user-owned content.

## Conceptual model

```text
canonical source
    + source-bound observations
    + immutable epistemic events
    = deterministic derived claim projection
    = read-only explanation surface
```

The canonical source remains authoritative. Events and projections are external
derived records. A projection may accelerate retrieval or explanation, but it
cannot be treated as an authority for a source write.

## Vocabulary

| Term | Meaning | Not equivalent to |
| --- | --- | --- |
| Canonical assertion | Content owned by the source system or user. | A derived claim. |
| Observation | A revision-bound source material event. | A verified fact. |
| Claim | A normalized assertion represented by the derived layer. | Source text or a retrieval hit. |
| Evidence | Material supporting, challenging, or contextualising a claim. | A causal guarantee. |
| Assessment | A versioned policy interpretation of current evidence. | Evidence itself. |
| Status | Procedural state, such as proposed or user-confirmed. | Numerical confidence. |
| Provenance | Record of entities, activities, and agents involved. | Truth or quality. |
| Valid time | When a claim is represented as holding. | When the system recorded it. |

## Minimal draft constraints

1. Events are immutable, scope-bound, closed-schema, and canonically encoded.
2. Portable references are opaque and revision-pinned; they do not expose raw
   content, prompts, absolute paths, credentials, or private payloads.
3. Each assessment records policy identity and revision.
4. Replaying identical ordered events under identical policy input produces
   identical projection bytes.
5. Retrieval rank, embedding similarity, and model self-report are not
   epistemic confidence.
6. Early assessments are qualitative and bounded: for example,
   `insufficient_evidence`, `supported`, `challenged`, or `conflicted`.
7. Human feedback creates new immutable evidence or revision events; it does
   not erase history.
8. Missing, malformed, oversized, or unreplayable derived records disable the
   optional epistemic feature without blocking baseline source access.

## Explicit non-goals

- universal truth or authority determination;
- Bayesian or numerical-confidence semantics;
- automatic canonical-source mutation;
- agent permissions or autonomous execution;
- a required database, transport, sync, or event protocol;
- implementation-specific storage formats; and
- standards, compatibility, or certification claims.

## Evidence needed for a future specification

Before this draft can advance, future work must publish closed schemas,
canonical serialization rules, synthetic fixtures, deterministic replay tests,
privacy and retention constraints, a change-control process, and evidence from
at least one implementation. A conformance suite must precede any independent
interoperability claim.
