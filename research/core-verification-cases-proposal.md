# Core verification cases proposal

**Proposed reasoning cases; not fixtures, tests, or conformance criteria.**
This document makes the proposed boundaries in [core design decisions](core-design-decisions-proposal.md)
and [core design comparison](core-design-comparison-proposal.md) falsifiable
in prose.

## Result categories

Keep four non-success outcomes distinct:

| Category | Bounded meaning | Required response |
| --- | --- | --- |
| Structural rejection | Declared input is missing, malformed, duplicate, ambiguous, contradictory, or incompatible with the requested interpretation. | Do not coerce, repair, rank, or silently weaken the request. |
| Unsupported interpretation | Named policy or revision cannot answer the request. | Produce no derived result and do not fall back to other semantics. |
| Unavailable evidence | Required source, revision, or dependency cannot be obtained or verified. | Do not substitute current content or claim successful replay. |
| Withheld disclosure | A result or even an availability marker could disclose protected information. | Suppress the affected output under the declared boundary. |

These categories do not specify error codes, priority, externally visible
messages, recovery behavior, or runtime handling.

## Traceability cases

| Case | Minimum declared inputs | Bounded expected conclusion | Rejection condition / falsifier |
| --- | --- | --- | --- |
| Positive bounded interpretation | Source revision, scope, named policy revision, and requested claim. | Inputs may support only the stated claim within declared scope. | If any required source or policy is implicit, conclusion is unsupported. |
| Malformed or duplicate input | Declared envelope and attempted interpretation. | Structural rejection. | Any silent coercion or duplicate-name winner violates the proposal. |
| Conflict | Two in-scope observations and their declared propositions/times. | Preserve conflict; no default winner. | Different propositions or validity intervals may not be a conflict at all. |
| Cross-scope request | Input scope and requested output scope. | Reject interpretation or disclosure requiring undeclared transfer. | A context label alone cannot grant permission. |
| Unavailable source | Opaque reference and expected revision. | Unavailable evidence; no current-source substitution. | Current content differs from the observed revision. |
| Missing temporal dimension | Requested temporal claim and required time dimensions. | Reject precise request; separate weaker view may be explicitly qualified. | If weaker view depends on missing time, reject it too. |
| Redaction or revocation | Declared source/disclosure change and affected derived view. | Stop dependent disclosure; suppress leaking markers. | Marker reveals protected membership or relation. |
| Unsupported policy revision | Requested revision and available named revisions. | Unsupported interpretation, no fallback. | Different semantics are applied under an undeclared revision. |
| Dependency failure | Declared dependency graph and available revisions. | Keep dependent conclusion unavailable or rejected. | Cycles, missing dependency, or scope mismatch invalidate claimed closure. |
| Challenge | Original observation and a declared challenge. | Preserve both and mark review as unresolved. | Challenge target differs from proposition or scope. |
| Supersession | Two source revisions and explicitly declared relation. | Treat supersession as a declared relation only. | Newer revision without that relation cannot erase historical observation. |
| Combined failures | One request with structural, unsupported, unavailable, or disclosure failure. | Preserve category distinctions and fail the affected optional result closed. | If safe output requires a priority rule, leave priority open; do not invent one. |

## Adequacy test

Coverage is inadequate if a materially distinct failure mode cannot map to an
input, bounded conclusion, and rejection condition above. A future review must
identify such counterexamples and add prose cases before any separately
authorized fixture design. These examples contain no real or private data and
do not execute a protocol.

## Boundary

The cases establish no legal, access-control, safety, alignment, learning,
transfer, performance, interoperability, or conformance result. They do not
authorize generated fixtures, executable tests, a schema, an implementation,
source ingestion, model access, or evaluation.
