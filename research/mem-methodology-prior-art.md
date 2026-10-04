# `mem` Methodology and Prior-Art Study

**Status:** Prepared for public review; non-normative documentary study with no
original experimental results claimed. All G1–G7 gates remain UNACCEPTED.

**Research cut:** 2026-10-04.

**External source ref:** `sjarmak/mem` commit `66967ea889eefb0d2cb7bf36902533e5655ee0ab`.

This study supplements the [Epistemic Replay Workbench dossier](epistemic-replay-workbench-dossier.md) and its [documentary review record](epistemic-replay-workbench-documentary-review.md). It does not revise either document's gate status, accept a design decision, or establish novelty, scientific effectiveness, implementation behavior, or interoperability.

## Scope and evidence quality

The supplied research note is a lead and interpretation, not primary evidence. Coordinator source inspection covered selected files at `sjarmak/mem` commit `66967ea889eefb0d2cb7bf36902533e5655ee0ab`, including the adoption-results and unscoreable-endpoint reports. Web retrieval returned cache misses for GitHub and raw URLs; the pinned GitHub file connector supplied source text. Reports are cited as documentary evidence of what their authors reported, not as independent verification of runtime behavior, agent correctness, or experimental results. No missing content or result is inferred.

Readable primary-source excerpts establish the following facts and boundaries.

### `mem`: task-trigger information

Decision 23 in [`docs/architecture-decisions.md`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/architecture-decisions.md)
(blob `255d71d303ff33c9504d338d054067d27d9f1ab8`) labels pre-run retrieval
from the held task's own trace errors `ours-oracle-triggered`. It adds a
separable task-text trigger condition.

This corrects the description of the experiment's trigger and separates the
information contribution of the trigger. It does not establish that an agent
autonomously recognizes a new error or decides to retrieve memory.

### `mem`: material admission

Coordinator source inspection covered [`src/distill/verify.ts`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/distill/verify.ts)
(blob `b13ee4fa826eed053072f029b5fe48f3bbf9fc57`) at the pinned ref.
`verifyFixEvidence` rejects missing resolution material and otherwise admits
it; it does not rerun tests.

Source-material admission permits inspection and provenance. It is not an
independent verification that the fix works.

### `mem`: dual-confidence design note

[`docs/memory-prediction-and-dual-confidence.md`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/memory-prediction-and-dual-confidence.md)
(blob `818583c117e11f277fec9b76020eb46aa44e59fc`) is explicitly a proposal.
It proposes separate retrieval and truth confidence, including age decay for
truth confidence, and states that v1 retrieval behavior is unchanged.

The note establishes conceptual overlap and a proposed direction. It does not
establish that either field or age-decay behavior exists in the runtime.

### Beads: operational provenance

Pinned primary files: Beads [`issueops/provenance.go`](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/internal/storage/issueops/provenance.go),
[`dolt/provenance.go`](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/internal/storage/dolt/provenance.go),
and [`cmd/bd/provenance.go`](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/cmd/bd/provenance.go)
at `c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c`.

The pinned code provides opt-in provenance record, log, and by-reference
commands. Event identity derives from source, issue, kind, and either reference
or occurrence time truncated to seconds. It is a deduplication identity, not a
digest of the full payload; insert-ignore leaves the first payload on duplicate
identity.

The pinned code comments that current provenance rows follow issue deletion
through `ON DELETE CASCADE`. This describes current-row lifecycle; Dolt history
was not inspected, so no claim about history erasure follows.

This is useful operational provenance. It does not establish claim truth,
canonical evidence bytes, or a complete integrity commitment.

[Beads PR #4461](https://github.com/gastownhall/beads/pull/4461) establishes
that the contribution merged on 2026-08-07 and is opt-in, without default
automatic capture. It provides a provenance surface, not an epistemic
assessment contract. No installed CLI version or compatibility claim is made.

### Adjacent papers: abstract-level reading only

[MemLineage](https://arxiv.org/abs/2605.14421v1), [MemConflict](https://arxiv.org/abs/2605.20926v1),
and [STALE](https://arxiv.org/abs/2605.06527v1) identify adjacent problem
families: lineage and sensitive-action gating; temporal, factual, and
contextual conflicts; and implicit conflict or stale-premise handling.

Authors are Ciyan Ouyang and Rui Hou; Zhen Tao and coauthors; and Hanxiang
Chao and coauthors, respectively. Only abstracts were inspected. Methods,
results, review status, and comparative performance are not assessed. The
supplied note attributes their inclusion in Jarmak's reading list; that
curation attribution was not independently verified.

Other exact-ref sources fetched but not sufficiently inspected for detailed claims include [`src/retrieve/exclusions.ts`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/retrieve/exclusions.ts), [`synthetic_arms.py`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/memory-bench/membench/report/synthetic_arms.py), and [`docs/prereg-beads-three-arm.md`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/prereg-beads-three-arm.md). Amendment specifics remain unverified. The supplied note's counts and scores are omitted as empirical findings.

This is a narrow source audit, not a corpus review. It does not inspect the complete `mem` repository, its website, paper library, book, Beads integration, adjacent projects, or all experiment artifacts. It makes no claims about those materials.

### Supplied-note coverage register

The supplied note also discusses other sources and wider claims. The following were not independently verified for this study and are retained only as possible future research leads:

| Lead in supplied note | Treatment here |
| --- | --- |
| Website-wide writing census, book catalog, and book-research limitations | No coverage, count, catalog, or quality claim adopted. |
| CodeScaleBench results and historical model/repository comparisons | No scores, task counts, or causal conclusions adopted. |
| Temporal workflow/runtime deployments and recovery claims | No deployment, canary, or production-readiness claim adopted. |
| Scheduling replay and its threshold | No experiment, dataset, or decision claim adopted. |
| Livedocs, ToM-SWE, CodeProbe, and AOA | Future comparison candidates only; no capability, performance, or safety endorsement. |
| Unresolved `:chatgpt-content-reference` markers | Not citations and not evidence. |

Other unverified claims in the supplied note remain outside this study. Exact source names and links are retained only where needed to identify a possible follow-up question; they do not imply that the source was read or that the description is accurate.

## Relevance to EMS

The verified overlap is meaningful but bounded. `mem` explicitly separates a memory's retrieval value from a proposed truth-related value, and its decision log demonstrates why experimental labels must describe the information actually used to trigger retrieval. These are relevant to EMS's assessment and replay research. Neither fact establishes that `mem` and EMS have the same contract.

EMS Decision 0002 remains a proposed substrate-independent, source-bound event and deterministic replay design. EMS Decision 0003 remains a proposed policy boundary: status, evidence, assessment, source revision, observation time, recorded time, assessment time, valid time, and authority must not collapse into one implicit score or operation. The research draft and decisions disclaim novelty. This comparison narrows the question; it does not support an originality claim.

The distinction to investigate is not simply “retrieval confidence versus truth confidence.” A retrieval score describes selection or surfacing. An epistemic assessment is an output under identified evidence, scope, time, and policy. A proposed numeric field cannot substitute for that contract, and no value alone authorizes a write, action, or promotion.

## Evidence and interpretation

### Hindsight in retrieval trigger

**Evidence:** Decision 23 reclassifies held-task trace-error-triggered
pre-run retrieval as oracle-triggered and adds a task-text control.

**Synthesis:** “Available before task start” does not prove “retrievable from
information the agent could observe at that point.” Trigger provenance belongs
in the experiment record.

**Case and falsifier:** Hold task and memory fixed; vary only trigger
information. If the task-text arm reads held-task errors, trigger labels and
leakage controls fail.

### Material availability and fix verification

**Evidence:** `verifyFixEvidence` checks for resolution material, not a fresh
test result.

**Synthesis:** A diff or readable transcript can support provenance and
inspection without proving correctness. Keep evidence presence, verification
method, verifier result, and artifact revision distinct.

**Case and falsifier:** Provide resolution diff with a failing test at the
bound revision. If a projection calls the fix verified solely because the diff
exists, this distinction fails.

### Temporal availability and valid time

**Evidence:** EMS distinguishes source observation, record time, and valid
time. The supplied note describes a retrieval cutoff relative to task start;
that external implementation detail remains unverified here.

**Synthesis:** Eligibility as of a task cutoff answers an information
availability question. It does not say when a claim held in the represented
world. Availability time and claim valid time need separate rules.

**Case and falsifier:** A record is eligible at task start but concerns a
different commit interval. If eligibility alone makes it current, the temporal
contract is underspecified.

### Retrieval confidence and assessment

**Evidence:** The dual-confidence note proposes ranking and correctness fields
and explicitly says v1 retrieval behavior is unchanged.

**Synthesis:** EMS can recognize this overlap without adopting two numeric
fields. Any future score must be policy-bound, interpretable, and separate from
procedural status and action authority.

**Case and falsifier:** Frequently retrieved claim is contradicted by
revision-bound evidence. If popularity increases its assessment or permission,
the boundary fails.

**Synthesis:** Inactivity is not itself evidence of falsity. Decay may suit a
separately justified retrieval heuristic, but must not silently expire
constraints, permissions, or intent.

**Case and falsifier:** Leave a still-valid safety constraint unused. If time
alone weakens or removes it, the rule violates the authority boundary.

### Closure, adoption, and task benefit

**Source-reported document findings:** [`docs/adoption-harness/RESULTS.md`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/adoption-harness/RESULTS.md)
(blob `ae9e339010eaa3c3f5534406e567c8963286df9d`) reports that explicit
instructions and redirection increased observed Beads adoption, without
showing improved overall task completion. It describes synthetic design and
native-memory confounds. These are findings reported in the document, not
independently rerun or runtime-verified here.

**Synthesis:** Lifecycle closure, landed artifact, review, explicit acceptance,
and task benefit differ. Recall calls, citations, storage volume, and capture
are process measures; benefit needs a comparable outcome and burden measure
against a defined baseline.

**Case and falsifier:** If task closure implies acceptance, or tool use alone
counts as task benefit, the endpoint conflates distinct outcomes.

### Scripted synthetic agent

**Evidence:** Attachment-reported only; source content not sufficiently
reviewed here. The supplied note describes exact-ID scripted retrieval.

**Synthesis:** A deterministic harness can validate persistence, isolation,
stale-data, and distractor mechanics without demonstrating language-model
capability or real-task utility.

**Case and falsifier:** Replace exact-ID retrieval with blinded task-text
query and a separately specified agent. If the claimed capability disappears,
the scripted result did not establish it.

### Abstention and unscoreable endpoint

**Source-reported document findings:** [`docs/finding-goal-endpoint-unscoreable.md`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/finding-goal-endpoint-unscoreable.md)
(blob `d6d4fc76f2b897b94dbbe8f1707bbe09afb2dc7a`) reports that the goal
endpoint could not discriminate memory arms when the target configuration was
viewed as implausible; it treats capture as a separate outcome. This does not
independently establish that any particular refusal was objectively correct.
Amendment details and any fresh-pilot outcome remain unverified here.

**Synthesis:** Correctness, abstention, capture, and action authorization need
separate outcomes. Agent retrieval, abstention, authority, and task-benefit
evaluation are future questions, not findings of this study. No action is not
automatically success or failure; define scoreability before interpretation.

**Case and falsifier:** A task supplies a questionable value. If the endpoint
cannot distinguish retrieval, capture, abstention, and authorized action, it
cannot support an arm-level task-benefit conclusion.

## Difference hypothesis and limits

**Candidate difference hypothesis:** EMS investigates a portable, human-governed record that binds source authority, revision-bound evidence, assessment policy, temporal scope, replay, and explicit authority boundaries. `mem` is relevant prior art for work-linked memory, retrieval evaluation, trigger controls, and a proposed utility/correctness distinction. The materials inspected here do not show that `mem` implements EMS's full proposed contract; this limited inspection also cannot establish that it does not.

The hypothesis would be weakened or falsified if a pinned primary-source audit found an existing `mem` contract and executable consumer that already preserve these distinctions with equivalent failure semantics and replay behavior. It would also fail to establish practical value if EMS's distinctions did not change outcomes on preregistered counterexamples, or imposed cost without reducing errors, unsafe actions, or ambiguity against a matched baseline.

## Candidate evaluation boundary

A staged future evaluation agenda could distinguish four outcomes:

1. **Evidence integrity:** source reference, revision, observation conditions, and derivation remain inspectable.
2. **Assessment integrity:** assessment identifies policy and inputs; missing or conflicting inputs remain explicit.
3. **Manual review burden:** human effort required to inspect source references, revisions, evidence, and policy scope in the synthetic workbench.
4. **Later agent task utility:** task outcome, errors, latency, context cost, retrieval, abstention, and authority behavior under a separately authorized agent study.

These are candidate measurement dimensions, not frozen metrics or acceptance thresholds. This is a staged future agenda, not an executed evaluation. The immediate workbench is a manual synthetic design with no agents; it does not evaluate agent retrieval, abstention, authority, or task benefit. Any such evaluation would require separate authorization, fixed scopes, task information, policies, agent budget, permissions, denominators, unscorable cases, controls, and falsifiers before a run. This document authorizes neither.

## Conclusion

The strongest verified contribution for EMS is methodological: label retrieval triggers according to their actual information source, and do not equate resolution material with verified correctness. The dual-confidence note is a clearly marked design proposal, not a runtime result. Adoption and unscoreable-endpoint reports support narrower statements about what those documents report; they do not independently establish runtime behavior, objective refusal correctness, or task benefit. Synthetic-arm details, temporal exclusion behavior, and amendment specifics remain unverified.

Beads adds a practical provenance primitive, while its deterministic identity is a deduplication key rather than a whole-payload integrity digest. The three cited papers identify nearby research families, but abstract-only inspection cannot support methods or performance comparisons. These additions sharpen the prior-art map without implying that EMS invented provenance, confidence separation, temporal conflict handling, or stale-memory reasoning.

No numeric experiment result, implementation claim, novelty claim, runtime recommendation, source admission, or authorization follows from this study. The companion documentary review record identifies the disposition and exact digest of any reviewed version; a verdict does not transfer automatically to later edits.
