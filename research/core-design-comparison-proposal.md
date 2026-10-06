# Core design comparison proposal

**Proposed comparison; no profile or standard adopted.** This document turns
the candidate boundaries in [the core design decisions proposal](core-design-decisions-proposal.md)
into reviewable design questions. It does not select a schema, serialization
profile, canonical bytes, hash, signature, runtime, or interoperability claim.

## Primary source comparisons

- [RFC 8785, JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785.html)
  specifies deterministic JSON representation for cryptographic operations.
  Its input must conform to I-JSON, it preserves array order, sorts object
  property names, emits UTF-8 without whitespace, and constrains number
  serialization (§§3.1–3.2). It does not establish application adoption or
  event identity.
- [RFC 7493, I-JSON](https://www.rfc-editor.org/rfc/rfc7493.html) describes a
  constrained JSON message format, including UTF-8, no duplicate member names,
  and numeric portability guidance (§2). It does not define canonical bytes,
  provenance, event order, or schema evolution.
- [W3C PROV-DM](https://www.w3.org/TR/prov-dm/) defines a domain-agnostic
  provenance model. [W3C PROV-O](https://www.w3.org/TR/prov-o/) maps provenance
  concepts to an ontology; `prov:wasRevisionOf` describes revision as a kind
  of derivation. These are provenance models, not repository/version-control
  implementations.
- [W3C PROV-CONSTRAINTS](https://www.w3.org/TR/prov-constraints/) §6.2 defines
  event-ordering constraints as a relative preorder, without requiring a
  physical clock. Its ordering graph is one validation step, not a total order
  or a complete validation algorithm for this research proposal.

## Candidate concepts and failure cases

| Concept | Candidate use | Rejection condition | Counterexample |
| --- | --- | --- | --- |
| Event identity | Distinguish declared observations and assessments during review. | Reject complete replay when identity is missing, duplicate, ambiguous, or mismatched. | Two streams may reuse local identifiers without denoting the same event. |
| Source revision | Bind a derived statement to the observed source state. | Do not replace unavailable observed material with a current version. | Same revision label can map to changed content if the source adapter is faulty. |
| Policy revision | Name interpretation applied to declared inputs. | Unsupported revision yields no derived result; no automatic fallback. | Changed semantics under one unchanged label make the label insufficient. |
| Time and order | Distinguish observation, recording, assessment, and validity from declared event order. | Reject precise temporal or complete-order claims when required inputs conflict or are absent. | Later recording time alone does not prove causality or event order. |
| Dependency and supersession | Describe declared support, challenge, revision, and supersession relationships. | Keep impact unresolved when required relation is unavailable, cyclic, or out of scope. | A newer source revision need not refute every historical observation. |
| Replay | Re-evaluate a bounded interpretation using declared inputs, order, and policy revision. | Do not report replay success when required inputs are unavailable or disclosure is withheld. | Determinism cannot resurrect revoked material. |
| Error and unavailable result | Distinguish malformed input, unsupported interpretation, unavailable evidence, and withheld disclosure. | Do not report any failed or withheld interpretation as successful reconstruction. | An unavailable marker can itself reveal sensitive membership. |

## Serialization questions, not decisions

Any later profile comparison should address duplicate member names, number
precision and range, Unicode constraints, object-property ordering, array
ordering, and unsupported revisions. RFC 8785 imposes input and number
requirements for JCS; RFC 7493 gives I-JSON portability guidance. A candidate
implementation must not silently choose duplicate-name winners, round values,
or equate visually similar strings. These are comparison questions only; no
canonical-byte or conformance claim follows.

## Falsification

If a design requirement cannot be expressed without choosing event identity,
total order, relation closure, policy fallback, or canonical-byte behavior, the
claim that this work remains pre-schema is false. Narrow the requirement or
record a separately reviewed decision before proceeding.
