# Decision 0003: Pluggable assessment and revision research

## Status

**Proposed research design.**

This decision records a boundary for future research. It does not add a
released schema, protocol, implementation, conformance programme, or claim of
novelty, compatibility, certification, or external endorsement.

## Context

The Research Draft v0 deliberately separates source material, evidence,
procedural status, and an assessment produced under a named policy. Its first
qualitative assessment states are intentionally narrow. They do not model
numerical confidence, source-reliability learning, Bayesian updating, or a
universal theory of truth.

That restraint remains necessary. Yet a useful research record must make room
to study harder cases: conflicting evidence, revisions, time, actor-scoped
views, dependence between claims, and the cost of obtaining better evidence.
Adding one hidden confidence score or one mandatory reasoning engine would
collapse those distinctions and create an untestable authority boundary.

Relevant components have extensive prior art. Truth-maintenance systems,
belief revision, evidence combination, provenance, information-value research,
temporal epistemic logic, and multi-agent agreement each address parts of the
problem. This repository therefore makes no claim to have invented claim
revision, evidence weighting, uncertainty, provenance, or active inquiry.

The research question is narrower: can a portable, human-governed record bind
source authority, evidence, policy revision, dependency-aware review,
replayable reconstruction, privacy-safe provenance, and future question
selection without silently turning a derived projection into a write authority?

## Decision

Future work will treat assessment and revision semantics as **versioned policy
plug-ins** over an immutable, source-bound event record. The core contract must
preserve provenance and replay boundaries without selecting a universal truth,
probability, reliability, or multi-agent model.

The initial qualitative policy remains the only proposed v0 assessment boundary.
Future policies may be researched only as separately identified revisions with
their own inputs, outputs, fixtures, failure semantics, privacy review, and
replay evidence.

## Core contract boundary

Any future core contract must keep these concerns explicit and separate:

| Concern | Meaning | Must not imply |
| --- | --- | --- |
| `status` | Procedural lifecycle state, such as proposed or user-confirmed. | Truth, probability, or automatic authority. |
| `assessment` | Output of one named policy revision over declared inputs. | Evidence itself or a universal conclusion. |
| `uncertainty` | Policy-scoped representation of what remains unresolved. | A universal scalar or calibrated probability. |
| `source_reliability` | Explicit, scoped policy input or assessment about a source. | Intrinsic source worth, truth, or passive learning. |
| `actor` | Declared human, service, or other holder context for an event or view. | Permission, identity assurance, or consent. |
| `source revision` | Pinned identity of source material observed by an event. | Current source state or write authority. |
| `observation time` | Time source material was observed under declared conditions. | When it was valid or recorded. |
| `recorded time` | Time a derived event was recorded. | Observation or valid time. |
| `assessment time` | Time a policy produced a declared result. | Event creation time or a causal guarantee. |
| `valid time` | Time interval the policy represents a claim as holding. | Filesystem modification time or permanence. |

`source_reliability`, if studied, must be scoped to an identified policy,
source reference, evidence class, and evaluation time. It must be explainable,
reviewable, and revisionable. No policy may infer it from unrecorded behaviour,
silently change canonical records, or convert it into a fact claim.

The core must preserve immutable events, opaque revision-bound source
references, policy identity and revision, deterministic ordering, and a
replayable result or explicit error. A policy can propose a derived projection;
it cannot silently create a canonical-source write, rewrite history, or make a
permission decision.

## Policy plug-in requirements

Each candidate policy must declare:

1. a stable identifier and semantic revision;
2. accepted event kinds, schema revisions, and ordered inputs;
3. its representation of assessment and uncertainty;
4. treatment of missing, conflicting, malformed, redacted, or out-of-scope
   evidence;
5. dependency and supersession behaviour;
6. actor, scope, privacy, and retention assumptions;
7. deterministic replay and failure semantics; and
8. synthetic positive, negative, and counterexample vectors.

No score, probability, reliability value, policy upgrade, or policy fallback
may be interpreted without its policy identity and revision. An unsupported
policy, unknown input revision, or unverifiable replay must fail closed for the
optional derived feature while leaving baseline source access available.

## Candidate families, not selected algorithms

The following are research families, not requirements or endorsements:

- truth-maintenance and dependency-directed review;
- AGM-style belief revision and its alternatives;
- Dempster--Shafer or transferable-belief representations;
- provenance semirings and other provenance query models;
- information-value or cost-aware question selection;
- temporal and dynamic epistemic reasoning; and
- multi-agent belief, disclosure, and reconciliation models.

Initial comparisons must use synthetic fixtures. A later public corpus or
external benchmark requires a separate review of source authority, privacy,
retention, and comparability. No result may be generalised from one policy,
corpus, tokenizer, implementation, or source domain into a universal
assessment claim.

## Prior-art and falsification posture

This repository must actively try to falsify any claim that its building blocks
are new. The following anchors identify established families that future work
must distinguish from this research direction:

- [Doyle, *A Truth Maintenance System*](https://doi.org/10.1016/0004-3702(79)90008-0)
  for truth maintenance;
- [Alchourrón, Gärdenfors, and Makinson, *On the Logic of Theory Change*](https://doi.org/10.2307/2274239)
  for belief revision;
- [Smets and Kennes, *The Transferable Belief Model*](https://doi.org/10.1016/0004-3702(94)90026-4)
  for evidence combination;
- [Green, Karvounarakis, and Tannen, *Provenance Semirings*](https://doi.org/10.1145/1265530.1265535)
  for provenance representation;
- [Lindley, *On a Measure of the Information Provided by an Experiment*](https://doi.org/10.1214/aoms/1177728069)
  for information-value research; and
- [Pacuit, *Dynamic Epistemic Logic I: Modeling Knowledge and Belief*](https://doi.org/10.1111/phc3.12059)
  for temporal and dynamic epistemic reasoning;
- [Bucheli, Kuznets, and Studer, *Realizing Public Announcements by Justifications*](https://doi.org/10.1016/j.jcss.2014.04.001)
  for justification and higher-order reasoning; and
- [Aumann, *Agreeing to Disagree*](https://doi.org/10.1214/aos/1176343654)
  for multi-agent belief analysis.

The only hypothesis worth testing is an **evidence-bounded composition**:
source authority plus explicit policy/revision binding, dependency-aware
review, replayable reconstruction, privacy-safe provenance, and
human-governed question selection. That hypothesis remains unproven until
published baselines, synthetic vectors, and independent review show what this
composition does that existing approaches do not already provide.

## Research sequence

The agenda adds six dependent tracks. Each track brief must name its closest
prior-art baseline and the exact difference hypothesis under test. Completing a
track creates research evidence only; it does not create an implementation,
standard, or external compatibility claim.

1. **Track 8: assessment policies and uncertainty boundaries.** Define a
   closed vocabulary and candidate policy contract before comparing semantics.
2. **Track 12: reproducible temporal reconstruction.** Define source,
   observation, recorded, assessment, and valid-time vectors before making
   revision claims.
3. **Track 9: provenance-preserving revision and dependency closure.** Test
   supersession, challenge, dependency review, and safe failure without
   automatic refutation.
4. **Track 10: cost- and provenance-aware question selection.** Evaluate
   whether a system can request better evidence without treating retrieval or
   model preference as truth.
5. **Track 11: higher-order provenance and meta-claims.** Study claims about
   sources, assessments, and policies without confusing them with object-level
   claims.
6. **Track 13: provenance-aware multi-agent coordination.** Consider only
   after explicit identity, disclosure, authority, consent, privacy, conflict,
   and security boundaries have their own reviewed decision.

## Advancement gates

No candidate policy may advance beyond documentation until all applicable gates
are met:

1. prior-art comparison identifies overlap, difference, and non-novelty;
2. vocabulary and policy boundary are closed enough for rejection cases;
3. synthetic fixtures cover support, challenge, conflict, supersession,
   dependency, temporal, redaction, and malformed-input cases;
4. replay and failure results are reproducible from declared inputs;
5. privacy, retention, deletion, and actor-scope limits are reviewed;
6. at least one independent implementation or review evaluates the exact
   fixtures; and
7. any public claim is narrowed to the exact policy, version, corpus, and
   evidence available.

Multi-agent work adds separate gates for identity, authentication, authority,
consent, disclosure, conflict resolution, data minimisation, and abuse cases.
It must not reuse a single-user provenance record as evidence that those
requirements are solved.

## Consequences

This decision keeps v0 small and deterministic while making future research
more honest. It prevents confidence labels, reliability scores, or agent
coordination from entering the core as unexplained ambient state. It also makes
an eventual comparison with established work possible: each policy can be
tested against its declared assumptions rather than defended as a universal
model of knowledge.

The next approved work should be a closed vocabulary and synthetic-vector plan
for Tracks 8 and 12. It must not implement an assessment engine, modify a
canonical source, claim external compatibility, or propose an external standard.
