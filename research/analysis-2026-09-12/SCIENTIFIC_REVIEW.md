# Scientific review — research portfolio and bounded next gates

**Date:** 2026-09-12

**Review surface:** `3bf173396a2c1ad91d53280c0dd6eac09b3daab7` (`research/triz-repository-analysis-20260912`); Track 14 Phase 1 proposal inspected separately at `42d80ebd75320eb89ab618ac86754fb979c302a7`.

**Status:** Evidence-backed research assessment. It proposes no schema, code, task material, model access, benchmark, runtime, repository, or publication action.

## Verdict

The repository has a coherent research-governance programme, not empirical
evidence for its research hypotheses. The strongest near-term portfolio work is
to make Tracks 8 and 12 reviewable as a shared closed vocabulary and synthetic
vector plan, while resolving the still-explicit Phase 1 freeze blockers in
Track 14. Track 15 remains a valid bounded incubation container, but not a
separate empirical construct: its governing decision preserves all six missing
admission predicates.

This is a **NO-GO for empirical or implementation claims**. It is a **GO for
outcome-free protocol, vocabulary, source-to-claim, and vector planning only**,
subject to each decision's separate maintainer authorisation.

The research draft correctly separates canonical source, observation, claim,
evidence, assessment, status, provenance, and time; it also requires identical
ordered events and policy inputs for byte-identical replay
(`spec/epistemic-memory-research-draft-v0.md:27-59`). That boundary is the
portfolio's useful contribution. It is not yet a closed contract, a tested
replay system, or evidence of interoperability.

## Evidence method and limitations

Repository evidence was read from `OPEN_RESEARCH.md`, the research draft, all
seven `research/*.md` files, Decisions 0002–0005, and the two files in the
separate Track 14 Phase 1 proposal. File-and-line citations below refer to the
reviewed source bytes.

A supplementary code-index surface was attempted first. No callable resource,
template, or indexed-repository context was available in this session.
Consequently, this review uses bounded deterministic file/Git inspection and
makes no graph or blast-radius claim.

The external source set is deliberately small and primary/authoritative. It is
not a systematic review and cannot establish novelty, construct validity,
replication, or an effect in this repository. The subsequent
[source audit](SOURCE_VERIFICATION.md) records the level actually accessible:
Doyle was corroborated through the publisher abstract, while direct primary-text
verification of AGM remains inconclusive. Those historical references are
orientation, not the sole basis for any proposed gate.

## What primary sources establish — and do not establish

| Source | Bounded source claim | Limit for this portfolio |
| --- | --- | --- |
| [RFC 8785, JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785.html) | Defines deterministic JSON canonicalisation for hashable representations; it constrains input to I-JSON and deterministic property sorting. | Informational RFC, not a source-authority, event, privacy, replay-policy, or truth model. |
| [Doyle 1979, A Truth Maintenance System](https://doi.org/10.1016/0004-3702(79)90008-0) | Describes recording reasons for beliefs, revision after contradictory discoveries, and dependency-directed backtracking. | A prior architecture, not proof that this ledger's assessment, retention, or human-governed policy is correct. |
| [Alchourrón, Gärdenfors and Makinson 1985](https://doi.org/10.2307/2274239) | Establishes a major formal family for contraction and revision of belief sets. | AGM assumptions do not choose a policy for source-bound event records or solve provenance, privacy, or temporal semantics. |
| Green, Karvounarakis and Tannen 2007, Provenance Semirings ([DOI](https://doi.org/10.1145/1265530.1265535); [author PDF](https://www.cs.ucdavis.edu/~green/papers/pods07.pdf)) | Proposes commutative-semiring annotations to document and track positive relational-algebra query provenance from inputs to outputs. | Query provenance is not source authority, belief revision, redaction, or a universal dependency/replay representation. |
| [Geiger et al. 2021, Causal Abstractions](https://proceedings.neurips.cc/paper/2021/hash/4f5c422f4d49a5a807eda27434231040-Abstract.html) | Uses aligned causal variables and interchange interventions to test a proposed causal role in a bounded neural-model case study. | Supports a control standard for mechanism claims, not a generic certificate for an external representation or a black-box model. |
| [Hsu et al. 2023, Visual-Scratchpad](https://proceedings.mlr.press/v239/hsu23a.html) | Reports a bundled diagram-execution/readout method that beat an inference-only comparator but lost to a fine-tuned model in its experiments. | Workshop result; generation, readout, visual model, and optional expert iteration are bundled, so it cannot isolate a scaffold effect. |
| [Hou et al. 2025, visual-language evaluation](https://proceedings.mlr.press/v267/hou25c.html) | In its six-model suite, relational diagram understanding was limited and background knowledge produced shortcuts. | It motivates relation and leakage controls; it does not prove that diagrams never help or that every visual result leaks. |
| [Turpin et al. 2023, unfaithful chain-of-thought](https://proceedings.neurips.cc/paper_files/paper/2023/hash/ed3fea9033a80fea1376299fa7863f4a-Abstract.html) | Shows in tested settings that plausible chain-of-thought can fail to report biasing factors that influenced a model answer. | Does not show every trace is unfaithful; it blocks treating a trace as causal evidence without an intervention. |

### Synthesis, not source fact

These sources support three design disciplines: canonical bytes are necessary
for reproducible byte-level replay; dependency/revision and provenance have
substantial prior art; and representation or trace performance alone does not
identify a causal mechanism. They do **not** establish novelty of the proposed
composition, benefit of a candidate operator, a multimodal scaffold, learning,
transfer, retention, safety, alignment, or workspace participation.

## Portfolio map: priority, gate, and failure state

Priority means value of next **documentation/review** work, not permission to
build or evaluate.

| Track | Priority | Strongest bounded next action | Acceptance gate | Failure / stop gate |
| --- | --- | --- | --- | --- |
| 1. Prior art and terminology | P0 | Maintain a source-type-labelled overlap matrix for every new construct. | Each term has closest prior art, exact difference hypothesis, and collapse example. | Any claimed distinction is fully described by prior terminology. |
| 2. Closed schema and canonical serialization | P1, after privacy boundary | Specify envelope/profile decisions and rejection cases only. | Versioned closed proposal, canonical rules, fixtures, independent replay plan. | Undefined canonical bytes, silently accepted unknowns, or write-authority leakage. |
| 3. Synthetic replay and malformed vectors | P1, with 2 | Plan positive, negative, ordering, parent-link, and malformed vectors. | Public synthetic fixtures, expected result/error, independent-review route. | Missing expected failure semantics or one implementation only. |
| 4. Privacy, retention, scope | P0 foundation | Produce threat/misuse and deletion-boundary decision material. | Explicit payload, metadata, linkability, index, backup, and legal-retention handling. | Privacy-unsafe or unreplayable record blocks optional feature; baseline source access remains available. |
| 5. Independent implementation/review | P3 | Draft review protocol against exact future vectors. | Reproducible notes, independent findings, limitations, version gate. | Review cannot reproduce materials or implies certification/adoption. |
| 6. Substrate-independent design | P2 after 2–4 | Convert Decision 0002 gates 1–4 into a dependency-ordered specification/vector plan. | Threat model, closed envelope, vectors, deterministic replay/failure semantics precede implementation. | Any projection becomes hidden source authority or privacy boundary remains unreviewed. |
| 7. Token-efficient projections | P3 after 2–3 | Define an evaluation card for JSON/TOON/YAML/JSON5 projection comparison. | Pinned format/encoder/tokenizer, digest equivalence, round-trip and negative vectors. | Token result lacks named corpus/tokenizer or changes canonical semantics. |
| 8. Assessment and uncertainty | P0 | Close vocabulary and candidate policy-input/output/rejection plan with Track 12. | Policy identity/revision, ordered inputs, conflicts/redactions/malformed handling, vectors. | Ambient score, undeclared fallback, or policy turns into truth/write authority. |
| 9. Revision and dependency closure | P1 after 8/12 | Plan supersession/challenge/dependency/redaction vectors against a declared policy. | Deterministic review output/error and independent review of exact vectors. | Automatic downstream refutation or history rewrite. |
| 10. Cost/provenance-aware questions | P2 after 8–9/12 | Specify objective, costs, refusal and fixed/random baselines synthetically. | Candidate-question provenance, comparison corpus, human review/refusal paths. | Retrieval/model preference is represented as truth or cost is undeclared. |
| 11. Higher-order provenance | P2 after 8–9/12 | Draft typed object/meta-claim examples and counterexamples. | Scope/privacy rules, replay tests, rejection cases, prior-art comparison. | Meta-claim conflated with source content or ordinary claim. |
| 12. Temporal reconstruction | P0 | Close time vocabulary and out-of-order/missing-time vector plan with Track 8. | Source, observation, recorded, assessment, valid time definitions; replayed results/errors. | Filesystem time substitutes for a declared time or causal/real-world time is inferred. |
| 13. Multi-agent coordination | HOLD | Write no protocol until a separate governance/threat-model decision exists. | Identity, authority, consent, disclosure, minimisation, conflict, abuse, and independent evaluation. | Single-user ledger is offered as coordination evidence. |
| 14. Explicit Strategic Learning | P0 protocol-only | Resolve Phase 1 freeze blockers through independent review; do not generate tasks or access outcomes. | Frozen candidate, task/split, controls, budgets, estimand, labels, provenance and authorisation. | Prompt/procedure/tool/retrieval/trace/model-update explanation remains; null, failed, or non-interpretable primary outcome stops promotion. |
| 15. Multimodal Cognitive Scaffolding | Incubated; dedicated Phase 0 separately authorised | Conduct construct-separability review only if separately authorised. | One term makes a prediction not captured by prompt/retrieval/tool/procedure/operator terminology, plus fidelity and budget controls. | Failure to specify a required predicate blocks experiment promotion. Any later containment, renaming, retirement or deferral requires a new decision; current portfolio incubation remains unchanged. |

The ordering is source-bound: Track 6 requires threat model, closed envelope,
vectors, and replay semantics before implementation
(`docs/decisions/0002-substrate-independent-reference-design.md:205-223`);
Decision 0003 makes Tracks 8 and 12 the first dependent work, then 9, 10, 11,
and only later 13 (`docs/decisions/0003-pluggable-assessment-and-revision-research.md:143-166`).
The agenda independently requires concrete evidence for each track
(`OPEN_RESEARCH.md:9-132`).

## Cross-track scientific blockers

1. **No closed experimental or replay object yet.** The draft has constraints,
   not a public closed schema, canonicalisation profile, vectors, or independent
   replay (`spec/epistemic-memory-research-draft-v0.md:44-59,90-96`). A hash
   chain alone cannot establish semantics, source authority, privacy, or
   deletion.
2. **Revision semantics are underdetermined by provenance.** TMS, AGM, and
   provenance semirings overlap with Tracks 8–11 but answer different questions.
   A future policy must name its input domain, failure behaviour, supersession,
   redaction, time, actor scope, and revision; no universal confidence or truth
   policy follows (`docs/decisions/0003-pluggable-assessment-and-revision-research.md:36-93`).
3. **Temporal and dependency claims need falsifiable replay vectors.** The
   repository correctly distinguishes time concepts, but has no executed
   reconstruction proof. Ordering from filesystem metadata is explicitly
   forbidden (`OPEN_RESEARCH.md:80-86`; `docs/decisions/0002-substrate-independent-reference-design.md:120-125`).
4. **Track 14 construct validity remains open.** Existing literature gives
   direct adjacent explanations: prompt, procedure, retrieval, tools, trace,
   latent proxy, policy, and parametric update. The Phase 0 review labels this
   exact distinction provisional and names collapse conditions
   (`research/explicit-strategic-learning-phase-0-review.md:32-96`).
5. **Track 15 separability is unproved.** Decision 0005 admits a research
   container, not a construct or result, and retains missing treatment,
   comparator, fidelity, regime, governance, and independent-review predicates
   (`docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md:43-77`).
6. **Modality claims need content and exposure parity before performance.** The
   required audits include semantic, relational, source, numerical,
   contradiction, and temporal fidelity, then token, time, compute, renderer,
   capability, retrieval, tool, feedback, and human-effort parity
   (`OPEN_RESEARCH.md:113-132`; `research/multimodal-cognitive-scaffolding-programme.md:232-250`).

## Track 14 Phase 1 proposal: quantitative review

**Status:** Proposal only; no task instances or outcomes accessed
(`research/explicit-strategic-learning-phase-1-preregistration-draft.md:1-25`).
It has a credible *shape* for a falsifiable study: source-blind cactus-graph
evaluation, direct/process/ablation arms, parity requirements, deterministic
final-answer verification, and `T-C` as the only primary contrast
(`research/explicit-strategic-learning-phase-1-preregistration-draft.md:116-214`).
That is not an executable registration.

| Quantitative blocker | Evidence | Required bounded resolution before freeze | What cannot be claimed meanwhile |
| --- | --- | --- | --- |
| No concrete model, environment, decoder, seed, time, context, grammar, parser, verifier, prompt, or budget values. | Explicit freeze-blocker list (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:247-269`). | Complete exact values, hashes, owners, ceilings, and parity rule in a new reviewed version. | Reproducibility, comparable arms, cost, or a possible run count. |
| No practical effect threshold `delta`, interval half-width `h`, coverage, interval method, multiplicity rule, or finite-sample confirmation. | These are named but unfilled (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:314-334,356-365`). | Choose values before outcomes; demonstrate finite-sample precision for declared paired/block analysis. | Adequate sample size, power, precision, or positive decision rule. |
| `n_total` is symbolic. | The `4 × ceil(ceil((z_coverage / h)^2) / 4)` expression is explicitly a conservative planning upper-bound target, not evidence of an effect (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:316-331`). | Freeze `n_total`, allocation, missing/invalid handling, reserve policy, and max attempts after the precision check. | Statistical sufficiency or affordability. |
| Call volume and cost are indeterminate. | Minimum envelope is `n_total × 5`, or `× 6` if conditional arm `P` is required; cost cannot be estimated until blocked values are fixed (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:336-342`). | Produce a reviewed cost envelope only after all ceilings/model fields and `P` gate are fixed. | Economy, feasibility, or authorised model evaluation. |
| Separability gate unresolved. | Independent reviewer must state transformation without ordered prompt steps; reviewer-specified procedure-equivalent `P` arm becomes mandatory if found (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:72-83,193-214,264-266`). | Obtain independent pre-freeze review; freeze `P` or classify as procedure-level. | An operator-level or causal claim. |
| Exposure and split integrity are not yet evidenced. | Manifests, leakage audit, fresh contexts, and no retrieval/tool/example/feedback/update are prerequisites; breach is `non_interpretable` (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:147-179,367-389`). | Freeze/access-control evidence before outcomes; predefine terminal handling. | Held-out transfer, source blindness, or valid attribution. |

The proposed positive rule is appropriately narrow: lower bound of the frozen
two-sided interval for `T-C` must exceed `delta`, with all regressions reported.
The proposal itself says a pass remains only an evidence-bound comparison, not
assessment, truth, deployment, general transfer, safety, or alignment
(`research/explicit-strategic-learning-phase-1-preregistration-draft.md:356-409`).

### Competing explanations and falsifiers

For a future result, higher `T` score remains compatible with: extra effective
prompting; a fixed procedure; extra token/time/attention; output-format or
ordering cues; training contamination; retrieval/tool/feedback exposure;
easier generated instances; verifier/scorer artefacts; a single favourable
paraphrase; or model/environment drift. The proposed `C`, `N`, `I`, conditional
`P`, parity logging, split rules, and outcome labels are sensible controls, but
they are only planned controls.

Falsification is decisive, not cosmetic: if `T-C` misses the frozen rule, a
matched process/prompt control explains the effect, components explain it,
surface/source leakage appears, the transformation cannot be stated apart from
the procedure, or a mandatory regression/non-interpretable condition occurs,
the candidate must not be promoted (`research/explicit-strategic-learning-phase-1-preregistration-draft.md:391-409`).

## Strongest bounded next actions

1. **Tracks 8 + 12 planning packet.** Draft a single reviewable vocabulary and
   vector-plan artefact: each time and policy field, valid/invalid input,
   replay output/error, privacy condition, and closest prior-art difference.
   Acceptance: all terms closed enough for rejection cases; no policy selection
   or implementation. Failure: any fallback or score lacks an identity/revision.
2. **Track 14 independent pre-freeze audit.** Ask one independent reviewer to
   test only construct separability, comparator parity, and whether `P` is
   required. Acceptance: written reviewer conclusion can state an independent
   transformation and each confound/control mapping. Failure: classify as a
   procedure/prompt bundle; do not freeze or evaluate.
3. **Track 14 freeze-completion checklist.** Turn lines 222–269 and 314–389 of
   the proposal into a maintainer-owned field-by-field completion record,
   including `delta`, `h`, interval method, finite-sample confirmation,
   `n_total`, upper cost, call cap, ITT rule, and terminal conditions. Acceptance:
   no placeholder remains before outcomes. Failure: stay proposal-only.
4. **Track 15 Phase 0 decision packet, only with separate authorisation.** Use
   one named representation treatment and test whether its proposed prediction
   survives collapse into prompt/procedure/operator terminology before selecting
   models or creating materials. Acceptance: all Decision 0005 predicates can
   be specified outcome-free. Failure: contain, rename, defer, or retire.
5. **Tracks 2–6 dependency ledger.** Publish no code; map each exact source and
   decision field to privacy, canonicalisation, vector, replay, independent
   implementation, and adapter gates. Acceptance: no implementation or
   interoperability assertion precedes its evidence. Failure: retain as research
   design.

## Non-claims and final gate

No source or repository evidence reviewed here shows a working epistemic-memory
implementation, deterministic replay result, scientific effect, distinct
operator, distinct multimodal scaffold, transfer, retention, model learning,
causal internal use, workspace participation, safety, alignment, or
interoperability. Completion of a track adds research evidence only and creates
neither standard nor authority (`OPEN_RESEARCH.md:3-7`).

Before any later empirical step, the controlling sequence remains: frozen
outcome-free protocol, separately authorised synthetic material, bounded
evaluation, independent review/replication, then a continuation/containment/
retirement decision. Neither Decision 0004 nor 0005 authorises an automatic
phase transition (`docs/decisions/0004-incubating-strategic-agent-learning.md:179-212`; `docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md:140-165`).
