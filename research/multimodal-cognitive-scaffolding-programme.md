# Multimodal cognitive scaffolding pre-admission programme

## Status and reading contract

**Proposed pre-admission execution specification, last verified 2026-09-05.**

This document is the canonical execution contract for deciding whether
multimodal cognitive scaffolding warrants a separately governed research
track. Conversation history, issue descriptions, and local notes are supporting
context, not competing plans.

The programme is non-normative. It authorises documentation and review only.
It does not authorise an experiment, benchmark, schema, runtime, model update,
new repository, or change to Matryca Plumber.

## Outcome

Produce an evidence-backed pre-admission packet that lets the maintainer make
one of four explicit decisions:

1. admit a separately numbered research track through a later decision;
2. contain a narrower representation-transformation question within an
   existing track;
3. defer the direction because the evidence or construct boundary is
   insufficient; or
4. reject the direction because it collapses into established terminology or
   makes no separately testable prediction.

Completion of this programme means that the packet, navigation, GitHub
coordination record, and independent review are published and internally
consistent. It does not mean that the proposed research direction is valid,
novel, useful, safe, aligned, performant, or admitted.

## Authoritative anchors

| Item | Verified state | Evidence |
| --- | --- | --- |
| Repository | `MarcoPorcellato/epistemic-memory-spec` | Maintainer repository inspected on 2026-09-05. |
| Base revision | `973f2ada3d4918d2f4ce1e71149972728356c278` | `origin/main` after a fresh fetch on 2026-09-05. |
| Delivery branch | `research/multimodal-scaffolding-pre-admission` | Isolated worktree created from the base revision. |
| Governing maturity | Research Draft — pre-standard | [`STATUS.md`](../STATUS.md) and [`VERSIONING.md`](../VERSIONING.md). |
| Contribution route | Issue before pull request; sources and evidence boundaries required | [`CONTRIBUTING.md`](../CONTRIBUTING.md). |
| Existing strategic-learning boundary | Decision 0004; epistemic core unchanged | [`Decision 0004`](../docs/decisions/0004-incubating-strategic-agent-learning.md). |
| Parallel work | Track 14 Phase 1 remains isolated in PR #16 | [PR #16](https://github.com/MarcoPorcellato/epistemic-memory-spec/pull/16), inspected on 2026-09-05. |
| Current milestone | Pre-admission design approved; canonical programme in delivery | Maintainer approval recorded on 2026-09-05. |

Re-verify drift-prone Git and GitHub anchors before every external mutation.
Do not merge or rebase this work through the Track 14 Phase 1 branch.

## Status vocabulary

- **Source fact:** a bounded statement attributable to a cited source, with
  publication type and scope recorded.
- **Synthesis:** a comparison or boundary proposed from source facts and this
  repository's governance. It is not itself empirical evidence.
- **Hypothesis:** a falsifiable statement reserved for a later preregistered
  test.
- **Unknown:** a material question that the reviewed evidence does not answer.
- **Verified:** terminal authoritative evidence exists for the stated scope.
- **In delivery:** recoverable work exists but its exit gate is incomplete.
- **Blocked:** a named dependency prevents the relevant path.
- **Deferred:** intentionally excluded until a predecessor justifies it.
- **Non-interpretable:** the planned comparison cannot support its target
  conclusion because a declared confound, execution failure, or evidence gap
  remains.

These terms do not replace the repository-wide maturity terms in
[`VERSIONING.md`](../VERSIONING.md).

## Research question

> Can an explicitly specified transformation of the same task information into
> a visual, spatial, auditory, temporal, or affective representation make a
> separately testable contribution to a preregistered task metric under
> semantically audited controls and matched exposure budgets?

This is a candidate question, not a positive claim. The pre-admission packet
must also test whether the question is already covered by prompting, retrieval,
tool use, representation learning, human-computer interaction, or Decision
0004's candidate strategic operator construct.

## Provisional terminology and collapse tests

| Term | Provisional operational boundary | Collapse or falsification condition |
| --- | --- | --- |
| **canonical task information** | Frozen task content from which every experimental presentation would be derived. | The label is misleading if an arm silently adds, removes, reorders, resolves, or hints at task information without recording that difference. |
| **scaffold-generation procedure** | The versioned method that produces an asset or presentation from canonical task information. | Collapse it into a prompt, renderer, retrieval operation, or tool invocation when that existing term fully describes the intervention and no additional prediction follows. |
| **candidate multimodal scaffold** | A research treatment consisting of an explicitly specified modality-specific representation derived from the same task information. It is not evidence, a source, an assessment, or an entity type. | Remove the term if it predicts nothing beyond “a different input format” or cannot be varied independently of its generation procedure and exposure budget. |
| **scaffold asset** | One concrete visual, spatial, auditory, temporal, or affective artefact presented in a treatment arm. | Do not distinguish it from ordinary task input if no derivation, modality, or exposure boundary is relevant to the comparison. |
| **representation treatment** | The complete material presented to a model in one experimental arm, including ordering and budgets. | Collapse it into a prompt or tool treatment when modality is never independently varied. |
| **candidate strategic operator** | Decision 0004's provisional reusable transformation of a problem representation or problem-solving process whose incremental contribution is testable. | Classify a proposed item as scaffold-only, prompt, procedure, policy, or tool access if no independently specified reusable transformation remains. Autonomous selection is not required. |
| **selection policy** | A separate rule deciding whether, when, and which scaffold or operator to use. | Omit it when treatment allocation is fixed. Never make selection a defining property of a scaffold or operator. |
| **mnemonic recoding** | A declared mapping from task items or sequences to other representational cues. | Reclassify it as retrieval or example exposure when the mapping introduces answer-relevant external knowledge. |
| **affective salience** | A declared valence-, arousal-, dominance-, novelty-, or goal-relevance-related treatment property. | Reject affective terminology when only formatting intensity changes. Never equate salience with confidence, truth, source authority, importance, or safety. |
| **audio-temporal cue** | An audio presentation whose transcript, duration, order, prosody, rhythm, and other declared properties can be controlled separately. | Collapse it into a text treatment if transcript alone reproduces the effect, or into an exposure-duration effect when time is unmatched. |
| **cross-modal alignment** | Measured correspondence between representations in different modalities. | Do not infer reasoning, retention, workspace entry, or causal use from alignment alone. |
| **workspace claim** | A model-specific claim that a representation is reportable, controllable, flexibly reusable, and causally involved under declared tests. | Stop at decodability, correlation, or sensitivity if intervention, necessity, or flexible-reuse evidence is absent. Never generalise a model-specific result to other architectures. |
| **learning regime** | A declared distinction among same-turn conditioning, within-context retention, external-memory support, non-parametric persistent state, and parametric update. | Do not use “learning” when the benefit requires the current scaffold or retrieval, or when the starting and ending model states are not bound. |

The terminology survives pre-admission only if at least one distinction makes a
separately testable prediction and improves experimental diagnosis. Otherwise
the packet must recommend collapse into existing terms.

## Epistemic envelope

| Evidence class | What it may support | What it cannot support |
| --- | --- | --- |
| Source inspection | A bounded account of what a cited source reports. | Reproduction, causality beyond the source, transfer, safety, novelty, or performance in a new setting. |
| Instrumentation evidence | That provenance, budgets, transformations, and outputs can be recorded as planned. | Scaffold efficacy or learning. |
| Exploratory evidence | Hypothesis generation and detection of confounds in declared pilot conditions. | Confirmatory claims or gate promotion. |
| Confirmatory evidence | Only the frozen estimand and comparisons in a preregistered bounded protocol. | General capability, universal modality advantage, safety, alignment, or unregistered transfer. |
| Independent review or replication | Robustness within the reviewed protocol and tested models. | Generalisation outside that scope or admission by itself. |

Negative, null, failed, and non-interpretable outcomes remain part of the
record. A later policy-derived assessment must remain separate from source
facts and experimental outcomes. A memorable or salient representation does
not become epistemic evidence and does not inherit the authority of its source.

## Initial primary-source map

This map records bounded starting anchors, not a completed systematic review.
Every source retained in the pre-admission review must state publication type,
tested setting, limitations, and forbidden inference.

| Area | Primary source | Bounded relevance |
| --- | --- | --- |
| Diagrammatic scratchpads | [Hsu et al., 2023](https://proceedings.mlr.press/v239/hsu23a.html), NeurIPS workshop proceedings | Visual-Scratchpad combined diagram execution and readout; the reported method outperformed an inference-only model but underperformed one fine-tuned model. This exposes tool, model, and training confounds. |
| Diagram comprehension | [Hou et al., 2025](https://proceedings.mlr.press/v267/hou25c.html), ICML proceedings | Six evaluated vision-language models showed limited relational diagram understanding and evidence of background-knowledge shortcuts. This motivates relation-fidelity and leakage controls. |
| Knowledge-graph prompting | [Wen et al., 2024](https://aclanthology.org/2024.acl-long.558/), ACL proceedings | The reported pipeline bundles graph retrieval, external knowledge, prompting, and question answering; it is not direct evidence for a visual scaffold or internal mechanism. |
| Visual graph guidance | [Lei, Xiao, and Wei, 2026](https://arxiv.org/abs/2606.02673), arXiv preprint | The authors report benefits for visual graph guidance in a teacher-student multi-hop-QA pipeline under their controls. The preprint does not establish a general visual advantage or durable learning. |
| Multimodal alignment | [Girdhar et al., 2023](https://openaccess.thecvf.com/content/CVPR2023/html/Girdhar_ImageBind_One_Embedding_Space_To_Bind_Them_All_CVPR_2023_paper.html), CVPR proceedings | A joint embedding was trained across six modalities. Alignment does not establish scaffold efficacy, reasoning, retention, or workspace use. |
| Audio-visual latent reasoning | [Dai et al., 2026](https://arxiv.org/abs/2605.22012), arXiv preprint | The proposed trained system interleaves text and audio-visual latent states. It is not evidence for external audio scaffolds or a general workspace claim. |
| Affective representation | [Maheswaran and Desarkar, 2026](https://aclanthology.org/2026.eacl-long.165/), EACL proceedings | The authors report dataset-transferable emotion-direction results in tested models while also reporting limits in complex emotion reasoning. This does not establish felt emotion or desirable decision control. |
| Concept directions | [Kim et al., 2018](https://proceedings.mlr.press/v80/kim18d.html), ICML proceedings | TCAV tests model sensitivity to user-defined concept directions. Sensitivity is not causal use, an operator, or a workspace. |
| Causal representation testing | [Geiger et al., 2021](https://proceedings.neurips.cc/paper/2021/hash/4f5c422f4d49a5a807eda27434231040-Abstract.html), NeurIPS proceedings | Interchange interventions test proposed causal roles in a bounded case. They are not a generic interpretability certificate. |
| Verbalizable workspace representations | [Gurnee et al., 2026](https://transformer-circuits.pub/2026/workspace/index.html), research article and preprint | The authors report functional workspace properties for verbalizable representations in studied language models. The result does not show image or audio workspace entry, consciousness, or use of an external mind map. |

Human-learning evidence may supply hypotheses only. It must be placed in a
separate table, labelled as human evidence, and paired with a statement that no
effect transfers to artificial agents without direct controlled evidence.
Trivium, Quadrivium, Suggestopedia, TRIZ, OTSM, mind-map traditions, and human
mnemonic systems are comparison lenses or hypothesis sources only, never
architecture or proof.

## Scope

- Preserve the direction as a reviewable, versioned research programme.
- Produce a terminology matrix with a collapse or falsification condition for
  every proposed distinction.
- Produce a primary-source prior-art map covering visual and diagrammatic
  reasoning, graph prompting, mnemonic recoding, audio-temporal treatments,
  affective representations, cross-modal alignment, latent reasoning, and
  causal interpretability.
- Separate source facts, synthesis, hypotheses, and unknowns.
- Define matched-control requirements for semantic, relational, source,
  numerical, temporal, exposure, and modality fidelity.
- Define future gates for preregistration, synthetic materials, bounded
  evaluation, independent review, and eventual admission or extraction.
- Publish a GitHub issue and a narrow documentation pull request after review.
- Keep navigation current without creating a second status authority.

## Non-goals

- No Track 15 or Decision 0005 in this delivery.
- No schema, manifest schema, runtime entity, API, implementation, task
  generator, benchmark, model execution, training, model update, or dataset.
- No Matryca Plumber, Logseq, database, Shadow, source-authority, or
  compatibility change.
- No claim of safety, alignment, novelty, transfer, retention, acceleration,
  learning, workspace use, or performance without direct evidence matching the
  claim.
- No assertion that models experience emotions.
- No equation of visual, auditory, mnemonic, or affective salience with truth,
  reliability, authority, importance, or evidence.
- No treatment of a reasoning trace, probe, concept direction, or decodable
  representation as a causal explanation without intervention evidence.
- No new repository until later extraction criteria are independently met and
  separately authorised.

## Invariants and approval boundaries

1. The epistemic core remains unchanged.
2. Evidence remains distinct from policy-derived assessment; assessment remains
   distinct from truth.
3. A source remains authoritative over a derived scaffold. The scaffold is a
   versioned treatment artefact, not evidence.
4. “Accelerated” requires a declared metric, unit, matched baseline, budget,
   uncertainty treatment, and reported regressions.
5. Same-turn conditioning, context retention, external-memory support,
   non-parametric persistent state, and parametric learning are separate claims.
6. Cross-modal alignment, decodability, causal use, workspace participation,
   retention, and learning are separate claims.
7. Every future phase requires its own entry evidence and explicit maintainer
   authorisation. A completed document never authorises the next phase.
8. Public prose remains maintainer-owned, vendor-neutral, and bounded to cited
   evidence.
9. Track 14 Phase 1 and PR #16 remain isolated from this programme.
10. Commit, push, issue publication, pull-request creation, merge, experiment,
    and extraction are distinct gates even when several documentation gates
    have been authorised together.

## Future experimental-control requirements

These are requirements for later protocol design, not authorisation to create
tasks or run models:

- freeze canonical task information before generating any representation;
- audit semantic, relational, numerical, source, contradiction, and temporal
  fidelity separately;
- disclose additions, omissions, ordering changes, answer hints, and generation
  failures;
- match or explicitly model token, pixel, frame, sample, duration, context
  position, latency, compute, tool, retrieval, feedback, and human-effort
  budgets;
- separate content, topology, layout, colour, imagery, prosody, rhythm,
  melody, timbre, valence, arousal, novelty, and duration when relevant;
- bind model, revision, runtime, preprocessing, renderer, generator, prompt,
  seed, and asset digest;
- preregister one primary estimand, practical threshold, uncertainty method,
  multiplicity treatment, failure states, and stopping rules;
- use source-blind and structurally held-out evaluation when transfer is a
  registered target;
- retain invalid, failed, null, negative, and non-interpretable outcomes;
- require open-weight activation access and intervention evidence before any
  mechanistic workspace claim.

## Evolution ledger

| Milestone | Delivered result | Evidence | Residual boundary |
| --- | --- | --- | --- |
| Track 14 Phase 0 | Terminology and prior-art review for Explicit Strategic Learning | Main commit `973f2ada3d4918d2f4ce1e71149972728356c278`, issue #13, and PR #14 | Does not admit multimodal scaffolding or authorise experiments. |
| Track 14 Phase 1 proposal | Bounded CSP preregistration draft | PR #16 head `14473bdae9f1766d549b66c8ecee7010c8bac4ed`, inspected open on 2026-09-05 | Separate workstream; no task generation or evaluation authority. |
| Multimodal pre-admission design | Maintainer approved the pre-admission architecture | Approval recorded on 2026-09-05 | Written programme still requires review and publication. |

## Ordered delivery milestones

### M1 — Canonical programme

**Outcome**

- This file records the research question, terminology, boundaries, evidence
  envelope, milestones, publication gates, and completion checklist.

**Dependencies**

- Maintainer approval of the pre-admission architecture.

**Exit evidence**

- Self-review finds no placeholders, internal contradictions, ambiguous scope,
  unsupported positive claim, or unauthorised downstream work.
- Maintainer reviews the committed programme before execution planning.

**Impact**

- The direction gains a durable source of truth without being admitted as a
  research track.

**Residual risk**

- Source coverage and the distinctness of the construct remain unproven.

### M2 — Evidence-backed pre-admission review

**Outcome**

- A separate review document contains the complete terminology matrix,
  primary-source map, human-evidence quarantine, confound register,
  falsification conditions, unknowns, and disposition of the original
  integration proposal.

**Dependencies**

- M1 maintainer review.

**Exit evidence**

- Every retained factual statement has a direct citation.
- Publication type and source limitations are explicit.
- Every proposed distinction has a collapse or falsification condition.
- An independent reviewer checks source-to-claim correspondence.

**Impact**

- The maintainer can decide whether a distinct research object exists.

**Residual risk**

- Literature coverage cannot prove novelty or empirical utility.

### M3 — Inspectable execution plan and GitHub scoping issue

**Outcome**

- A dependency-ordered Markdown execution plan maps every programme requirement
  to a file, action, validation, and publication gate.
- A public issue records the bounded research question, evidence requested,
  non-goals, failure states, and admission choices.

**Dependencies**

- M1 maintainer review; issue-before-PR rule in `CONTRIBUTING.md`.

**Exit evidence**

- The plan contains no placeholder or implicit phase transition.
- GitHub read-back confirms exact issue title, body, labels, and URL.

**Impact**

- Work can resume after interruption without relying on chat history.

**Residual risk**

- An issue records coordination, not acceptance or evidence.

### M4 — Navigation and historical-state repair

**Outcome**

- Stable navigation points to the pre-admission packet without declaring a new
  track.
- The Phase 0 issue-draft header accurately records that issue #13 was
  published and closed, rather than calling it unpublished.

**Dependencies**

- M2 review document and M3 issue URL.

**Exit evidence**

- All repository-relative links resolve.
- Search finds no false “unpublished” statement for issue #13.
- No change touches Track 14 Phase 1 files or Matryca Plumber.

**Impact**

- Readers can find current evidence without creating a second status authority.

**Residual risk**

- Future GitHub state remains drift-prone and must be dated.

### M5 — Independent review and pull request

**Outcome**

- Independent scientific and governance reviews are reconciled.
- A narrow pull request contains only approved documentation changes.

**Dependencies**

- M2–M4 complete.

**Exit evidence**

- `git diff --check` passes.
- Markdown headings, direct links, absolute-path leakage, unsupported claim
  language, and forbidden-scope terms are checked explicitly.
- Exact base/head, file list, diff statistics, issue link, review findings, and
  GitHub PR state are read back.

**Impact**

- The programme becomes inspectable in the public repository.

**Residual risk**

- A documentation merge does not admit the research track or validate a
  scientific hypothesis.

### M6 — Documentation merge and checkpoint

**Outcome**

- The reviewed documentation pull request is merged if every publication gate
  is terminal and clean.
- The programme ledger records the merged commit, issue, PR, validation, and
  remaining future gates.

**Dependencies**

- M5 complete; no unresolved review finding; exact-head revalidation.

**Exit evidence**

- GitHub reports the pull request merged.
- `origin/main` contains the expected files at the reported merge commit.
- The completion checklist is audited requirement by requirement.

**Impact**

- The direction is durably preserved and ready for a later admission decision.

**Residual risk**

- No Phase 0 experiment, track admission, or later research phase is thereby
  authorised.

## Later research gates — planned, not authorised

1. **Admission review:** determine whether the construct survives terminology
   collapse and whether a separate track is architecturally justified.
2. **Dedicated Phase 0:** extend the systematic prior-art review and freeze the
   research vocabulary only after a later decision admits the question.
3. **Preregistration:** freeze one bounded question, task family, primary
   estimand, controls, budgets, failure states, analysis, and cost ceiling.
4. **Synthetic materials:** create only the preregistered, reviewable task
   materials under separate authorisation; do not create a general benchmark.
5. **Bounded evaluation:** run only the authorised model/task envelope; retain
   null, negative, failed, and non-interpretable outcomes.
6. **Independent review or replication:** test shortcuts, leakage, modality
   confounds, and claim scope before promotion.
7. **Extraction decision:** consider a new repository only if terminology,
   protocols, controls, reproducibility, and an architectural separation reason
   all survive independent review.

Each gate may end in admission, revision, deferral, collapse, or rejection. No
gate begins because a predecessor document exists.

## Delegation and cost policy

1. Use deterministic inspection and validation before model-assisted work.
2. Give independent read-heavy research, chronology, link checking, and
   mechanical documentation checks to the least costly suitable worker.
3. Give every worker explicit scope, exclusions, expected evidence, and stop
   conditions.
4. Do not permit overlapping writes. One integration owner reconciles all
   source, terminology, and governance conclusions against live repository
   bytes.
5. Retain scientific, statistical, architectural, publication, and merge
   judgment with the integration owner.
6. Allow one focused correction after a bounded worker failure; escalate only
   with an exact evidence packet.
7. Treat delegated conclusions as orientation until directly verified.

## Validation and publication gates

Before commit:

- inspect complete changed files, not truncated excerpts;
- check every factual claim against its cited source;
- classify sources as proceedings, peer-reviewed article, preprint, technical
  report, official research article, maintained archive, or human-evidence
  hypothesis source;
- scan for placeholders, private paths, credentials, prompts, vendor advocacy,
  unsupported superlatives, and forbidden scope;
- run Markdown whitespace and relative-link checks.

Before push:

- re-fetch and verify the complete `origin/main` commit;
- verify branch, HEAD, dirty state, diff scope, and issue-before-PR evidence;
- stop on unexpected divergence or unrelated user work.

Before pull request:

- read back the public issue;
- bind the PR body to the exact base/head and list claims that the diff does not
  establish;
- confirm that no Phase 1, schema, runtime, benchmark, model, or Plumber file is
  changed.

Before merge:

- require terminal independent scientific and governance reviews;
- re-run deterministic checks on the exact remote head;
- verify review threads, diff, mergeability, checks, and base drift;
- stop on any unresolved or non-interpretable result.

## Interruption and recovery

At each interruption record:

- repository, worktree, branch, exact HEAD, exact base, and dirty state;
- issue and pull-request URLs and live state;
- completed source checks and explicitly unverified sources;
- completed milestones and unmet exit evidence;
- active workers or processes, if any; and
- the next safe action and its authorisation boundary.

Save in-scope work in a recoverable commit when authorised. A temporary
worktree path alone is not a durable checkpoint.

## Milestone report format

- Result obtained
- Terminal validation evidence
- Claims or behaviour changed
- Residual risks
- Next dependency and authority gate

## Completion checklist

- [ ] The canonical programme is committed and maintainer-reviewed.
- [ ] The pre-admission review distinguishes source facts, synthesis,
      hypotheses, and unknowns.
- [ ] Every proposed term has a collapse or falsification condition.
- [ ] Primary-source coverage spans every declared research family.
- [ ] Human-learning evidence is quarantined as hypothesis material.
- [ ] Scaffold, generation procedure, treatment, selection policy, strategic
      operator, learning regime, alignment, and workspace claims remain
      distinct.
- [ ] Semantic, relational, source, numerical, temporal, exposure, and modality
      confounds are explicit.
- [ ] Future phases have entry, exit, failure, and separate-authorisation gates.
- [ ] Track 14 Phase 1 and PR #16 remain untouched.
- [ ] No Track 15, Decision 0005, schema, runtime, benchmark, model execution,
      training, or Plumber change is introduced.
- [ ] The GitHub scoping issue is published and read back.
- [ ] Stable repository navigation points to the packet without creating a new
      status authority.
- [ ] The stale Phase 0 issue-draft status is corrected against issue #13.
- [ ] Independent scientific and governance reviews are terminal.
- [ ] Deterministic Markdown, link, scope, privacy, and diff checks pass on the
      exact pull-request head.
- [ ] The documentation pull request is merged and verified on `origin/main`.
- [ ] The evolution ledger records exact final GitHub and Git anchors.

Completion remains unproven until every item has authoritative current
evidence. The result may still be deferral, collapse, or rejection of the
research direction.
