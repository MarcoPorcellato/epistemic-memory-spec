# Epistemic Replay Research Programme

## Status and decision summary

**Prepared for public review; non-normative documentary programme —
2026-10-04. No original experimental results are claimed.**
Repository snapshot: `cdeff0fbec369b440f70c2cfb7cc3b8cdee12fc5`.
This is a planning and source-synthesis document, not a preregistration,
accepted threat model, closed contract, machine-readable schema, fixture,
implementation, experimental result, or permission to execute or publish.

The maintainer requested deeper primary-source research and a more structured
route to useful results. The recommendation is to narrow the next decision,
not to add a memory stack: first resolve the threat, scope, retention, and
failure questions; then specify a small source-bound, policy-bound contract
that a reader can inspect against a matched manual baseline. Agent trials,
product adapters, persistent orchestration, and storage choices remain later,
separately authorised questions.

All G1–G7 advancement gates in the [workbench dossier](epistemic-replay-workbench-dossier.md)
remain **UNACCEPTED**. The [review record](epistemic-replay-workbench-documentary-review.md)
identifies which exact documentary versions received internal model review.
A documentary PASS is not scientific replication or gate acceptance.

## Evidence-to-design decision ledger

The following are research implications, not selected algorithms or accepted
controls. Source notes record precise locations, assumptions, and reading
limits; author-reported findings are not independent results here.

| Primary-source observation | Programme implication | Candidate check or falsifier |
| --- | --- | --- |
| MemLineage separates custody and lineage enforcement under declared host, key, and attribution assumptions; propagation can fail when required ancestry is missed. | Origin and integrity do not establish truth, complete dependencies, or permission. Do not import its action gate into EMS. | Missing declared ancestry must stay unknown or unsupported, not become independent corroboration or authority. See [literature](replay-study-memory-literature.md). |
| MemConflict distinguishes benchmark-defined temporal, factual, and conditional validity; STALE distinguishes recognition, stale-premise resistance, and downstream application. | Report evidence selection and interpretation separately. Benchmark gold is a constructed reference, not a universal truth policy. | Correct answer with wrong evidence or scope fails the provenance dimension even if the answer dimension passes. See [literature](replay-study-memory-literature.md). |
| Pinned `mem` retrieval uses a strict prior-close cutoff and a target-trace default trigger, while its scripted evaluation uses exact-ID retrieval. | Availability, applicability, and autonomous retrieval capability are separate. | Label held-target hindsight explicitly and do not generalise scripted mechanics to an LLM. See [`mem` audit](replay-study-mem-contracts.md). |
| Pinned operation capture uses first-write-wins ID deduplication and a strict top-level object with open nested payload values. | Operational identity and a structural allow-list do not establish payload integrity or semantic privacy. | Same ID with different content needs the selected profile's explicit comparison/rejection rule; nested material requires a stated boundary, not a comment. See [`mem` audit](replay-study-mem-contracts.md). |
| The `mem` preregistration itself identifies instruction dosage, comparator familiarity, channels, and allow-list limitations. | Arm-to-arm similarity is insufficient when all arms violate the intended information or tool contract. | Audit each condition against the declared protocol as well as against its comparator. See [`mem` audit](replay-study-mem-contracts.md). |
| Official storage/procedure documentation distinguishes recorded workflow state, version history, and external effects. | Neither a versioned database nor replayed orchestration chooses epistemic semantics or proves that an effect occurred. | Current-row deletion must not be called erasure of all copies; ambiguous effects remain unresolved. See [recovery study](replay-study-provenance-recovery.md). |
| Jarmak separates retrieval, verifier execution, artifact validity, acceptance, and engineering outcomes; the pinned CodeScaleBench report uses different denominators and contains an unresolved correlation-table inconsistency. | Keep stage measures and their coverage separate. Do not adopt the disputed correlation or an uncertainty bound criticised for ignoring dependence. | An improvement in retrieval cannot rescue an invalid endpoint, missing coverage, or unsupported task-outcome claim. See [evaluation study](replay-study-agent-evaluation.md). |
| Primary methods distinguish experimental units from repeated measurements, prediction from postdiction, and nonsignificance from practical equivalence. | A fixed-case correctness audit, one-maintainer study, and agent comparison need different inferential claims. Preserve amendments and unresolved outcomes. | Repeated runs do not create independent cases; a null result with inadequate resolution remains inconclusive. See [methods study](replay-study-methodology.md). |

Contrary or internally inconsistent source evidence is retained, not silently
repaired. The programme uses a source finding only at the level actually
established: document content, selected code, author-reported experiment, or
formal result under its assumptions. Public artifact availability is not
independent reproduction.

## Reading route and research ownership

Start with this programme for decisions, then consult the evidence notes rather
than treating a short synthesis as a complete reading of every source:

| Evidence note | Bounded research responsibility | Use in the next decision |
| --- | --- | --- |
| [Memory literature](replay-study-memory-literature.md) | Full-text access and methods of nearby memory papers; selected foundational work. | Identify overlap, assumptions, and candidate counterexamples; do not infer novelty. |
| [Agent evaluation](replay-study-agent-evaluation.md) | Relevant official book, evaluation publications, and their evidence boundaries. | Separate search quality, task outcomes, artifact verification, acceptance, and cost. |
| [`mem` contracts](replay-study-mem-contracts.md) | Static audit at the declared `mem` revision. | Separate temporal eligibility, trigger information, material admission, and scripted mechanics. |
| [Provenance and recovery](replay-study-provenance-recovery.md) | Official provenance, storage, and durable-execution material. | Distinguish identity, integrity, retention, retries, and authority without selecting a backend. |
| [Research methodology](replay-study-methodology.md) | Primary and official guidance on precommitment, precision, units, and reporting. | Make null, inconclusive, amended, and non-interpretable outcomes usable rather than relabelled as success. |

Each note has a single Luna Max writer. The coordinator owns integration and
scope reconciliation. Model-assisted reading is not an independent human
review. Sources unavailable in full remain explicit access gaps. The earlier
[methodology study](mem-methodology-prior-art.md) retains its historical reading
depth; these follow-up notes may close some gaps without rewriting that record.

## Governing repository evidence

The [charter](../CHARTER.md), [status](../STATUS.md),
[governance](../GOVERNANCE.md), [contribution rules](../CONTRIBUTING.md),
[versioning](../VERSIONING.md), and [evidence ladder](../docs/evidence-and-review.md)
control interpretation. This repository is pre-standard, with no released
protocol, stable schema, conformance suite, or reference implementation.
Maintainer acceptance records a bounded research decision, not truth,
certification, interoperability, or authority over a source.

The programme advances documentary questions relevant to Tracks 1, 4, 6, 8,
9, and 12. It does not merge these into Tracks 14 or 15. Under
[Decision 0004](../docs/decisions/0004-incubating-strategic-agent-learning.md),
`candidate strategic operator` remains a provisional research construct, not
a schema or runtime entity. Track 15 remains incubated under
[Decision 0005](../docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md).
Neither track is validated by a memory paper or this programme.

The historical [September analysis](analysis-2026-09-12/SCIENTIFIC_REVIEW.md)
and [action plan](analysis-2026-09-12/ACTION_PLAN.md) are useful antecedents,
not fresh remote-state evidence. This selected snapshot still contains
`type: "research"` in `CITATION.cff` and a latest-release README link. No
metadata correction is made here; the prior R1 decision is not proof that its
corrections are present in this worktree. Any maintenance follow-up must bind
the chosen source state rather than reuse a historical completion claim.

## Questions in dependency order

| Question | Candidate comparison or inspection | Useful bounded result | Falsifier or stopping condition |
| --- | --- | --- | --- |
| Q0 — overlap | Compare the proposed composition with pinned prior-art contracts, not project labels. | A precise difference hypothesis and named existing alternatives. | Existing contracts already supply the proposed distinction; narrow or abandon that difference claim. Limited inspection cannot establish absence. |
| Q1 — semantic specification | Independently inspect declared source revisions, relations, time scope, policy, and failure cases. | Each eligible case has an unambiguous specified result, explicit unsupported state, or rejection. | Reviewers cannot determine an outcome without hidden defaults or invented authority; keep the profile unfrozen. |
| Q2 — deterministic reconstruction | Later compare exact declared inputs and outputs against independently reviewed expectations. | A reproducible result or declared rejection under the frozen profile. | Replay differs, missing material is silently substituted, or two implementations merely share the same mistake. No execution is authorised now. |
| Q3 — manual inspection utility | Later compare manual baseline B0 with an explanation surface using identical underlying evidence and policy information. | Better bounded inspection at a declared acceptable burden, without an undeclared correctness loss. | B0 meets the need at lower burden, or explanation induces unsupported promotion. Stop or simplify that workbench, not all provenance research. |
| Q4 — agent uptake and utility | Later compare task conditions with matched information, model, budgets, tools, and permissions. | Distinct evidence for capture, exposure, interpretation, use, and task outcome. | Usage rises without useful outcomes, memory is unnecessary, hindsight leaks, or changed access explains the difference. Requires a separate protocol and authorisation. |
| Q5 — adapter or orchestration value | Later evaluate a named integration against its lightest alternative and exact consumer contract. | A measured requirement that justifies operational complexity. | The integration duplicates authority or cannot preserve the consumer boundary. G6/G7 and separate repository authorisations remain required. |

These are different questions. Success at Q1 does not establish Q3 or Q4;
success at Q4 does not establish replay integrity or authority. A correct answer
with the wrong source revision must not be counted as a successful provenance
explanation. A refused action is not automatically correct or incorrect.

## Baseline discipline

For Q3, B0 gives the reader the same source excerpts or synthetic source
representations, revision references, declared relations, policy text, scope,
cutoff, valid intervals, and update history. The proposed surface adds only
organisation and an inspectable derivation, not new evidence or privileged
answers. Any extra interpretation supplied by the surface is the treatment
and must be identified, not concealed as matched input.

A later agent comparison is not B0 with a different name. It would need its
own conditions and estimand. Candidate conditions include no additional
memory, source evidence, and source evidence plus an epistemic explanation;
their information, budgets, and permissions must be audited before a causal
comparison. Include cases where the necessary information is already present
to detect unnecessary retrieval. Neither these conditions nor a statistical
method, sample size, model, threshold, or execution count is selected here.

## Proposed case-family coverage

The [V01–V24 coverage backlog](epistemic-replay-workbench-dossier.md#proposed-vector-plan)
remains prose, not a frozen corpus or executable fixtures. The following
grouping helps choose a small initial profile; it does not require every
feature to be implemented:

| Family | Existing cases | Distinction to preserve | Scope limit |
| --- | --- | --- | --- |
| Declared relation and conflict | V01–V03 | Relation presence is a policy-scoped output, not truth. | Scope selection precedes assessment. |
| Temporal and contextual applicability | V04–V05, V20–V21 | Validity, source revision, and information availability differ. | Missing time remains unknown; newer is not automatically correct. |
| Duplicate and identity boundaries | V06–V08, V22 | Transport redelivery, canonical sequence, shared evidence, and payload integrity differ. | Unknown dependence is not independent corroboration. |
| Reconstruction and safe unavailability | V09–V10, V15–V17 | Ledger validation is not source reconstruction. | Preserve otherwise available baseline access; do not promise restoration of an unavailable source. |
| Policy and unsupported semantics | V11–V14, V19 | Historical assessment is not silent reassessment or automatic dependency propagation. | Withdrawal, reassessment, and cycles remain unsupported until their rules are reviewed. |
| Retention and authority | V18, V23–V24 | A tombstone is not erasure; readable material is not tested success; assessment is not permission. | No permission engine, automatic source write, or deletion guarantee is introduced. |

Select initial cases only after the G1 boundary and proposed policy scope can
be stated. Hold additional cases for later review. Excluding a case because a
profile explicitly does not support its semantics is different from hiding an
unfavourable result after execution. Record both coverage and exclusions.

For that later selection, a deliberately small candidate slice would ask:
does declared support remain distinct from truth; does declared challenge
produce the specified conflict only within compatible scope; do disjoint
validity intervals avoid an invented conflict; is the policy revision bound
to the result; does missing required source material stay unavailable; and
is a duplicate identity with changed content handled explicitly? These are
priority questions, not selected vectors or permission to generate them.
Dependency propagation, agent learning, effect recovery, and backend selection
need not enter the first profile merely because the prior art discusses them.

## Prospective measures, not reported results

| Dimension | Candidate observation | Denominator or unit to declare later | What it cannot establish |
| --- | --- | --- | --- |
| Specification completeness | Can an independent reader identify required inputs and one bounded result/rejection? | Eligible cases and assigned cases; unsupported cases separately. | Runtime correctness or usefulness. |
| Binding and interpretation | Correct source revision, relation, scope, cutoff, valid interval, policy, and failure explanation. | Per-dimension correct/scorable plus scorable/assigned; preserve errors and omissions. | Truth or source reliability. |
| Replay agreement | Canonical output or rejection compared with reviewed expectations. | Frozen vectors and named implementations; exact versions and bytes. | General correctness, independence, or compatibility outside that profile. |
| Manual burden | Setup, task inspection, correction, maintenance, and explanation review. | Reader, matched case, and session; order and familiarity recorded. | Population benefit from a single maintainer. |
| Later agent process | Capture, eligible exposure, interpretation, and actual use. | Assigned tasks, eligible opportunities, and actual experimental unit. | Causal utility from calls, citations, or stored-record counts. |
| Later agent outcome | Task correctness, justified uncertainty or abstention, authority boundary, latency, context and total cost. | Task families or clusters rather than assumed independent sessions. | Safety, alignment, transfer, or learning without direct evidence. |

Do not create a weighted score that lets faster inspection conceal source
substitution or an authority violation. Declare any permitted accuracy/burden
tradeoff before outcomes. Costs are distinct components; token counts, elapsed
time, operator effort, and billed spend are not interchangeable.

Before any later study, define scoreability, missing-input handling, exclusions,
timeouts, invalid endpoints, practical decision thresholds, and uncertainty
analysis. Failure to reject a null is not proof of equivalence or of no useful
effect. A small study may be inconclusive; do not recover a positive claim by
switching endpoints, selecting tasks, or reclassifying abstentions afterwards.

## Outcome-free protocol preparation

A later preregistration proposal should identify the research question and
primary comparison, experimental unit, task families, eligibility, information
cutoffs, policies, model state where applicable, exposure budgets, allocation
and order, measurement rules, precision rationale, ceilings, stop conditions,
and handling of every non-interpretable outcome. Exploration and confirmation
must be labelled separately.

Review a proposed scorer against counterexamples before exposing evaluation
outcomes. If an endpoint cannot distinguish relevant conditions, preserve that
diagnosis. An amendment creates a new protocol version and, where required, a
new pilot; it must not rewrite an earlier outcome into confirmatory success.
No protocol is frozen, publicly registered, or executed by this document.

## Dependency-ordered work packages

| Package | Proposed deliverable | Completion evidence | Authority and stop boundary |
| --- | --- | --- | --- |
| D0 — documentary source review | Source notes, overlap/falsifier map, and this programme. | Traceable primary sources, honest reading depth, reconciled limits, and documentary QA. | Current documentary work only; no gate acceptance. |
| D1 — G1 proposal | Threat, scope, retention, and failure memorandum. | Explicit owner questions, synthetic-only boundary, reviewed alternatives, and a recorded maintainer decision. | Separate authorisation to prepare it; acceptance is another decision. This programme is not that memorandum. |
| D2 — G2 proposal | Closed vocabulary/envelope and canonicalisation specification proposal. | All identity, sequence, policy, scope, error, and resource-limit choices justified. | G1 prerequisite and separate authorisation; no machine schema is created here. |
| D3 — G3 proposal | Versioned synthetic vectors and independent expected-outcome review. | Scope and expected results/rejections are reproducible and independently inspectable. | Separate material-generation authorisation; current tables are not fixtures. |
| D4 — G4 proposal | Deterministic replay and failure-semantics specification. | Canonical output requirements, validation precedence, and reconstruction limits are specified. | Specification, not executed replay evidence. |
| D5 — G5 proposal | Bounded independent synthetic implementation/evaluation. | Exact inputs, outputs, versions, deviations, and independent expectation comparisons. | Separate execution authorisation; no current runtime exists. |
| D6 — optional utility study | Manual Q3 study, or separately framed agent Q4 study. | Reviewed rubric, matched baseline, declared uncertainty and burden decision. | Separate study authorisation; does not replace G5 or accept G6/G7. |
| D7 — optional integration | Named adapter/consumer and, if justified, independent interoperability evidence. | Consumer boundaries and exact-profile evidence reviewed separately. | G6/G7 and each affected repository's authorisation; no automatic multirepo action. |

Research work can proceed in parallel only where dependencies and source
exposure remain independent. No model may accept an owner decision on the
maintainer's behalf. `PASS`, `PASS_WITH_NOTES`, and `BLOCKED` describe internal
documentary QA only. A failed, null, invalid, or non-interpretable outcome is
retained evidence, not an invitation to retry without authorisation.

## Product and registry boundary

The read-only Matryca Knowledge service was queried for orientation on
2026-10-04. It reported degraded operations at `[runtime:matryca_status]`.
Its source snapshot is not proof of current remote source heads; no refresh
or managed-source change was performed.

Two retrieved sections of
`matryca-plumber@05f9581c602adb1bfb1be25cedf4dd712aee35db:docs/superpowers/specs/2026-09-02-epistemic-claim-layer-v0-design.md`
state that the document is design-only and preserves existing Markdown,
Parser, P0 evidence, recall, and Shadow responsibilities. This is a pinned
document claim, not fresh implementation evidence. Synthesis: do not turn a
design, recall envelope, sparse archive, or operational tracker into an
accepted epistemic ledger. This programme makes no Plumber change.

Dolt, Beads, Temporal, and Gas City remain adjacent or optional tools. They
do not supply the proposed semantics merely by retaining records or completing
work. A multirepository study is not authorisation to link trackers, import
backlogs, configure remotes, or run cross-repository workflows.

Recovery vocabulary and effect-reconciliation cases in the source notes are
optional downstream-consumer concerns. They are not additions to the initial
reference-core profile, which has no agents, effects, or source writes.

## Recommended next decision and unresolved choices

### Evidence gaps to retain

The notes are bounded readings, not a systematic corpus census. The Jarmak
companion protocol is a mutable `main` read without a resolved commit; the
book itself is bound to arXiv v1. CodeScaleBench's named correlation input
was unavailable, so its inconsistent table is not a substantive finding.
Doyle was accessible at abstract/record level only; AGM was inspected in
selected sections of an explicitly identified mirror. The pinned Beads audit
did not inspect transaction helper bodies or reproduce inter-phase failure.
No author-reported experiment, implementation, deployment, or cost result
was independently replicated here. These gaps limit claims; they are not
automatic blockers for preparing a narrower documentary proposal.

### Owner choices before empirical work

The narrowest substantive next authorisation remains **preparation and review
of a G1 documentary memorandum only**, with no implementation or publication.
The maintainer would still decide its acceptance separately. Before any later
empirical step, decide the initial semantic scope, retained material and
reconstruction limits, reviewer independence, admissible burden/accuracy
tradeoff, and exact protocol and resource envelope.

This programme aims to make a useful negative result possible: an existing
contract may already cover the distinction; the proposed profile may remain
ambiguous; the manual baseline may be enough; or the operational burden may
outweigh any bounded gain. Any of those is a reason to narrow, simplify, or
stop the specific proposal. None establishes that all agent memory is useless.
