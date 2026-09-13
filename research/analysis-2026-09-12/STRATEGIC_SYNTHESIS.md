# Strategic synthesis — 2026-09-12

**Bound snapshot:** `3bf173396a2c1ad91d53280c0dd6eac09b3daab7`

**Purpose:** maintainer planning synthesis of repository inventory, governance/discovery review, and scientific review.
**Status:** non-normative assessment. It authorises no edit, protocol, task material, model access, benchmark, implementation, release, or external publication.

## Portfolio vision

This repository is best understood as a disciplined research record for a
future epistemic-memory contract: source authority remains outside the derived
layer; observations and immutable events can support a replayable claim
projection; evidence, policy-derived assessment, procedural status, provenance,
and time stay distinct. The intended value is not a universal truth engine or
a product memory system. It is a testable way to preserve bounded explanations
without silently creating a source write authority
(`spec/epistemic-memory-research-draft-v0.md:9-29,44-69`).

The portfolio has three coupled but non-substitutable layers:

1. **Epistemic core research (Tracks 1–13).** Determine whether a portable,
   privacy-bounded, replayable record and versioned assessment/revision policies
   can be specified and independently checked.
2. **Strategic-learning research (Track 14).** Test whether a separately stated
   problem-representation/process transformation has an incremental effect
   under matched controls. It is not a learning engine or a schema entity
   (`docs/decisions/0004-incubating-strategic-agent-learning.md:66-107`).
3. **Multimodal-scaffolding research (Track 15).** Preserve a candidate question
   about representation treatments only while its distinctness from prompt,
   procedure, tool, retrieval, renderer, capability, and Track 14 is tested
   (`docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md:65-77`).

Any later implementation is downstream of the evidence gates relevant to its
own scope; core work does not require Track 14 or Track 15 to succeed. A
favourable result in one layer does not discharge gates in another.

## Proven strengths

| Strength | Evidence | Bounded meaning |
| --- | --- | --- |
| Clear authority boundary | Canonical source remains authoritative; derived records cannot write source content (`spec/epistemic-memory-research-draft-v0.md:27-29,46-59`). | Strong conceptual safety boundary; not an implemented access-control proof. |
| Evidence discipline | Source fact, synthesis, hypothesis, and unknown are separated in the Track 14 and Track 15 reviews (`research/explicit-strategic-learning-phase-0-review.md:23-31`; `research/multimodal-cognitive-scaffolding-pre-admission-review.md:25-34`). | Claims can be audited by type; source coverage is not scientific validation. |
| Explicit non-goals | Research draft excludes universal truth, automatic source mutation, agents, and protocol/certification claims (`spec/epistemic-memory-research-draft-v0.md:61-69`). | Reduces accidental scope expansion; does not prove future work will observe boundaries. |
| Dependency-aware agenda | Decision 0003 orders policy/uncertainty and time before revision, question selection, meta-claims, and multi-agent work (`docs/decisions/0003-pluggable-assessment-and-revision-research.md:143-166`). | A credible research order; no closed policy or vector set exists yet. |
| Falsification posture | Track 14 names adjacent explanations and collapse conditions; Track 15 retains collapse, containment, deferral, and retirement outcomes (`research/explicit-strategic-learning-phase-0-review.md:32-96`; `docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md:100-120`). | Makes negative evidence first-class; no construct has yet passed controls. |
| Governance/navigation boundaries | Authority, status, contribution, privacy, and reader routes are already explicit (see the governance review's status section). | Maintainer process is inspectable; the dated remote review covers selected GitHub settings, not enforcement effectiveness. |

## Proven weaknesses and unresolved questions

| Matter | Evidence | Consequence |
| --- | --- | --- |
| No closed schema, canonicalisation profile, vectors, replay result, or independent implementation | Future-specification gates list all of these as outstanding (`spec/epistemic-memory-research-draft-v0.md:90-96`). | Core claims remain design hypotheses. |
| Privacy/retention/deletion semantics unclosed | Decision 0002 requires a separate decision and synthetic-only work until those limits are designed and tested (`docs/decisions/0002-substrate-independent-reference-design.md:151-166,205-223`). | No source/payload treatment or implementation should be inferred. |
| Assessment/revision semantics underdetermined | Future policies must specify identity, inputs, conflicts, supersession, scope, privacy, replay, and vectors (`docs/decisions/0003-pluggable-assessment-and-revision-research.md:76-110`). | No score, confidence, reliability, or revision rule can be treated as ambient truth. |
| Track 14 registration remains unfrozen | Model/environment, task grammar, prompts, budgets, practical threshold, precision, sample plan, and provenance ownership are all explicit blockers (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:247-269`). | No adequate sample, cost, transfer, causal, or efficacy claim is available. |
| Track 15 is portfolio-incubated, not scientifically admitted | Decision 0005 retains six unproved predicates, including separability, frozen controls, fidelity audits, regime/budget freeze, governance need, and independent review (`docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md:43-63`). | It must not be described as an established distinct construct or an authorized experiment. |
| Documentation integrity has a concrete metadata defect | `CITATION.cff` uses CFF 1.2.0 with unsupported `type: research`; the governance review's “Citation and licensing boundaries” section records the valid controlled values and validation proposal. | Citation rendering/archival metadata may fail or degrade; scientific content remains unaffected. |
| Remote release navigation is wrong for current release state | Live read-back on 2026-09-12 found prerelease `v0.0.0-research`, while `/releases/latest` returned 404; README's “Latest research snapshot” uses that failing endpoint (`README.md:97-101`). | Discovery link does not identify current prerelease. A later edit must select an explicit tag route or different promised meaning. |
| Remote governance evidence remains partial | Live read-back found PR #16 open at `42d80eb`, API base `973f2ada`, and zero checks, which is not PASS; classic main protection returned 404 and only a tag ruleset was observed. Zenodo/DOI and hosted issue-form/workflow behaviour remain unverified. | Do not claim protected-main enforcement, CI success, archival DOI, or hosted-form behaviour from the local tree. |

## Reconciled report findings

The initial governance report incorrectly stated that no local tag existed;
the source audit identified the contradiction and the report was corrected.
After reconciliation, the following apparent tensions are status distinctions
that must remain visible:

| Apparent conflict | Reconciliation | Maintainer rule |
| --- | --- | --- |
| Track 15 historical **DEFER** versus current bounded incubation | The admission memorandum records that six scientific predicates were not met; Decision 0005 changes only portfolio disposition and preserves those facts (`research/multimodal-cognitive-scaffolding-admission-review.md:27-57`; `docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md:43-63`). | Say “accepted for bounded incubation”; never say “scientifically accepted,” “validated,” or “Phase 0 authorised.” |
| Documentation-only repository versus proposed event ledger / Phase 1 draft | Decisions and drafts are research designs. The inventory's “Scope and result” and “Research-track coverage” sections found no schema, executable workflow, fixtures, runtime, package, or tests. | Terms such as “ledger,” “policy,” and “protocol” need “proposed,” “future,” or exact decision qualification. |
| Passing local hygiene checks versus quality claim | Local link/fence/diff checks support narrow document integrity only; the inventory's “Scope and result” and evidence record say zero executable checks are absence, not pass evidence. | Never convert document checks into runtime, scientific, legal, or remote-state validation. |
| Navigation currently coherent versus drift risk | Governance review's “Status and governance” section found no material contradiction at this snapshot, while identifying duplicated status summaries as a predictable future hazard. | Add one short linked status summary only if decision records remain explicitly authoritative. |
| Citation version/tag match versus invalid CFF type | Version/tag agreement is a local consistency fact; schema validity is a separate metadata correctness property (see the inventory's CFF entry and governance review's “Citation and licensing boundaries” section). | Retain version consistency, but repair/validate CFF before relying on hosted citation output. |

The absence of supplementary code-index coverage is consistently reported, not
conflicting: no usable index or callable surface was available. Deterministic
source inspection is adequate for this documentation snapshot, but does not
supply graph-based impact evidence.

## Core and track boundaries

| Area | Permitted current interpretation | Not established |
| --- | --- | --- |
| Core vocabulary | A design boundary for source-bound observation, immutable event, derived claim, evidence, assessment, status, provenance, and time. | A released protocol, API, conformance target, or source-write mechanism. |
| Tracks 1–5 | Foundational prior-art, schema/vector, privacy, and independent-review questions. | Completion, fixture coverage, implementation, interoperability, or certification. |
| Tracks 6–7 | Possible substrate-independent record and optional projection research. | Portability, token saving, adapter correctness, or a preferred format. |
| Tracks 8–13 | Candidate policy/revision/time/dependency/question-selection/meta-claim/coordination research. | Universal assessment, confidence, reliability, multi-agent governance, or authority. |
| Track 14 | Incubated candidate-operator construct and outcome-free Phase 1 proposal. | Operator existence, causal use, benefit, transfer, retention, safety, alignment, or execution authority. |
| Track 15 | Incubated candidate representation-treatment question. | Separability, efficacy, learning, retention, workspace participation, safety, alignment, or a separate implementation need. |

## What verifiable quality means

“Stellar” is not a testable repository state. For this portfolio, quality is
the conjunction of narrow, inspectable evidence:

1. **Claim traceability:** every material assertion is labelled source fact,
   synthesis, hypothesis, or unknown, with source type and scope.
2. **Boundary integrity:** source authority, evidence, assessment, status,
   policy, and time remain distinguishable; a rejected or malformed derived
   record cannot change canonical source access.
3. **Reproducibility readiness:** exact schema/policy/profile/version,
   deterministic inputs, expected output or error, synthetic vectors, and
   failure semantics can be independently replayed.
4. **Construct validity discipline:** a proposed operator/scaffold predicts
   something beyond prompt, procedure, tool, retrieval, renderer, or capability;
   matched controls can falsify it.
5. **Measurement integrity:** estimand, practical threshold, uncertainty method,
   stopping rule, budgets, provenance, regressions, and null/failed/
   non-interpretable labels are frozen before outcomes.
6. **Governance integrity:** a decision identifies current portfolio status and
   next explicit authorization; navigation links rather than silently overrides
   decisions.
7. **Metadata integrity:** citation and links parse/resolve under declared
   bounds; remote/archival state is claimed only after live read-back.

This is evidence quality, not a maturity score. Each item must be attached to
its exact version and its limits. A clean report, a documentation merge, or one
positive metric cannot satisfy the set.

## Strategic conclusion

The highest-leverage move is to convert the existing conceptual discipline into
small falsifiable planning objects before expanding scope: a privacy boundary,
a closed vocabulary/time/vector plan, and an independently reviewed Track 14
freeze record. This sequence directly attacks the portfolio's central risk:
that attractive language about provenance, strategic learning, or multimodal
scaffolds gets ahead of inspectable semantics and controls.

Track 15 remains accepted for bounded incubation. Its next phase remains a
separate maintainer decision, not a consequence of Track 14 or core work. A
dedicated review may later support containment, renaming, or retirement of a
specific construct, but none changes current portfolio status without a later
decision. Track 13 should remain blocked until a dedicated
identity/authority/consent/privacy decision exists.

The portfolio should use two parallel, bounded planning lanes: foundation work
for Tracks 4, 8, and 12; and protocol/construct work for Tracks 14 and 15.
Neither lane is scientific evidence for the other. Metadata/navigation repairs
are valuable parallel hygiene but cannot substitute for research gates.
