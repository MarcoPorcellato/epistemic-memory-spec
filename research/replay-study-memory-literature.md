# Memory conflict, lineage, and revision: replay-study literature review

**Status:** Prepared for public review; non-normative source study for
documentary research. No original experimental results are claimed; external
results remain attributed to their authors. All G1–G7 gates remain UNACCEPTED.
No schema, fixture, executable, agent run, runtime study, or external claim is
authorized by this document.

**Research cut:** 2026-10-04. **Repository snapshot:**
`epistemic-memory-spec` at `cdeff0fbec369b440f70c2cfb7cc3b8cdee12fc5`.

This study supplements the [Epistemic Replay Workbench dossier](epistemic-replay-workbench-dossier.md),
its [methodology and prior-art study](mem-methodology-prior-art.md),
[Decision 0002](../docs/decisions/0002-substrate-independent-reference-design.md),
and [Decision 0003](../docs/decisions/0003-pluggable-assessment-and-revision-research.md).
It adds research context and candidate counterexamples only. It does not
replace those records or revise their gate statuses.

## Reading and evidence boundary

The three requested arXiv v1 full-text HTML records were accessible. The
review covered methods, assumptions, evaluation, limitations, and conclusions
in the sections listed below. It did not inspect code, regenerate artifacts,
replicate, or independently validate results. Findings remain attributed to
their authors.

The additional foundational comparison is limited to three primary sources.
The Doyle paper's MIT repository metadata and abstract were accessible, but its
download endpoints returned HTTP 405 in the research browser. I therefore do
not treat the Doyle item as full-text reviewed. The AGM paper was available as
a 21-page PDF mirror; the publisher DOI is cited for the primary publication.
Green, Karvounarakis, and Tannen's 10-page author-hosted paper copy was
accessible. Neither extra paper was independently reproduced.

| Primary source | Version and source date | Full text actually reviewed | Access or review limit |
| --- | --- | --- | --- |
| [MemLineage: Lineage-Guided Enforcement for LLM Agent Memory](https://arxiv.org/abs/2605.14421v1), Ciyan Ouyang and Rui Hou | arXiv v1, 2026-05-14 | HTML abstract and main §§1–9; close read of threat model, design, implementation, attack workloads, evaluation tables, discussion and conclusion | Did not inspect repository, reproduce tables, or audit all references. Author-reported harness results only. |
| [MemConflict: Evaluating Long-Term Memory Systems Under Memory Conflicts](https://arxiv.org/abs/2605.20926v1), Zhen Tao, Jinxiang Zhao, Peng Liu, Dinghao Xi, Yanfang Chen, Wei Xu, and Zhiyu Li | arXiv v1, 2026-05-20 | HTML abstract; selected §§2.1–2.2, 3.1, 3.3, 3.5–3.7, 4.1–4.6 and §5 | Did not inspect all construction prompts, software, or raw data. Results remain benchmark-authored. |
| [STALE: Can LLM Agents Know When Their Memories Are No Longer Valid?](https://arxiv.org/abs/2605.06527v1), Hanxiang Chao, Yihan Bai, Rui Sheng, Tianle Li, and Yushi Sun | arXiv v1, 2026-05-07 | HTML abstract; §§1, 3.1–3.5, 4.1–4.4, 5–6; selected Appendix D construction/QC, Appendix E judge-agreement material, and Appendix F CUPMem design | Did not audit code, dataset files, every appendix, or every case study. Results remain author-reported. |
| [A Truth Maintenance System](https://dspace.mit.edu/handle/1721.1/5733), Jon Doyle | MIT AI Memo 521, repository date 1979-06-01; journal version 1979 | MIT repository record and abstract only | Full text not retrieved: MIT DSpace download requests returned 405. No detailed interpretation beyond abstract/metadata. |
| [On the Logic of Theory Change: Partial Meet Contraction and Revision Functions](https://doi.org/10.2307/2274239), Carlos E. Alchourrón, Peter Gärdenfors, and David Makinson | *Journal of Symbolic Logic* 50(2), 1985-06, pp. 510–530 | Abstract and selected PDF text from §§1–3, including partial-meet definition and postulates | Full text was read from a non-publisher mirror. Later proofs and all technical details were not exhaustively checked. |
| [Provenance Semirings](https://doi.org/10.1145/1265530.1265535), Todd J. Green, Grigoris Karvounarakis, and Val Tannen | PODS 2007, 2007-06-11–14, pp. 31–40 | Author-hosted PDF, pp. 1–10; selected §§1–9 on annotated relations, provenance semirings, Datalog, and limits | Full paper text accessible; no implementation or benchmark audit. |

The repository decisions already identify Doyle and AGM as prior-art anchors.
The two papers clarify the conceptual overlap; the database provenance paper
helps distinguish derivation lineage from source authority or truth. These
sources support no novelty, safety, transfer, or interoperability claim.

## MemLineage: chain of custody and action control

Threat model: attacker controls untrusted input; host/library, keys, and
inference are trusted. Single-turn direct injection without a memory write,
host compromise, backdoors, and
confidentiality are excluded. Design: per-principal Ed25519-signed CBOR,
Merkle log, weighted lineage DAG, verifier retrieval, action gate. Persistence
requires each ancestry edge to exceed τ; missing-parent defaults Trusted
(fail-open).
[Full text, §§1–4](https://arxiv.org/html/2605.14421v1).

Fixed three-attack harness Table 1 ASR by no-defense/signature-only/full:
1.00/1.00/1.00, 0.00/1.00/1.00, 0.00/0.00/0.00. One binary cell/adapter;
no trial denominator or confidence interval. AgentDojo's vulnerable-output
bridge tests six banking pairs: 6/6 baseline and signature-only successes;
full defense rows 0/6. Authors call this bounded, not powered. Four benign workflows retain 4/4
dispatches per defense row. Limits: trusted host/key/inference, single-host
anchoring, adaptive attacks/attention untested, recall bound unproved, denial
may not recover task. [§§6.1–6.2, 6.5–6.6,
8, Tables 1, 3, 8](https://arxiv.org/html/2605.14421v1).

## MemConflict: query-conditioned validity and diagnostics

MemConflict tests query-time selection among temporal updates, constructed
false static contradictions, and conditional facts; gold follows simulated
profile/timeline rules. Twelve generated profiles average 124.33 queries;
dialogues/distractors receive human checks. Six systems (A-Mem, LangMem,
Letta, MemOS, Mem0, Memobase) measure answer accuracy, update-order
consistency, conflict recognition, and support-evidence hit@K/rank (white
box); LLM judgments are human-verified, scores macro-average conflict types.
[§§3.1–4.3, Table 2](https://arxiv.org/html/2605.20926v1).

Table 3's AA macro-average across three conflict types is 0.5539 for MemOS
(highest static/conditional); LangMem leads dynamic AA at 0.4966. Table 4
reports MemOS SEH@3 0.6710/SRS 0.5879. Tables give point estimates without
confidence intervals or exact per-cell query n. Authors' SEH@3−AA is a
retrieval/answer mismatch proxy, not a causal estimate. Longer histories,
distractors, implicit questions, and conflict distance lower scores. Limits:
simulation, three types, six systems,
white-box diagnostics; multimodal, social, and strategic omission remain
open. [§§3.7, 4.3–4.5, 5, Tables 2–4, 7](https://arxiv.org/html/2605.20926v1).

## STALE: implicit invalidation and downstream use

STALE Type I changes one latent attribute; Type II propagates invalidation to a
dependent attribute. State Resolution (SR), Premise Resistance (PR), and
Implicit Policy Adaptation (IPA) measure recognition, false-premise response,
and downstream behavior. Data: 400 expert-validated scenarios, 1,200 queries,
100+ topics, contexts up to 150,000 tokens; generated dialogues use LongMemEval
distractors. Appendix E.3 reports 95.83% agreement on 240 items, not truth
validation. [Abstract, §§3.1–3.5, Appendix D, E.3](https://arxiv.org/html/2605.06527v1).

Baselines: five closed/four open LLMs, five frameworks (LightMem, Zep,
LiCoMemory, A-mem, mem-0), and CUPMem. Table 2: Gemini-3.1-pro scores 55.2%
overall across six type×probe cells (Type I/II SR 92/69%, PR 30/14%, IPA
71/55%); authors report CUPMem at 68.0% versus same-backbone GPT-4o-mini at
8.7%. CUPMem uses write-time adjudication and propagation retrieval. No CIs
or per-cell n; generated cases, judge sensitivity, model/context confounds,
and fixed schema limit scope. [§§4.1–4.4, 5, Table 2, Appendix F](https://arxiv.org/html/2605.06527v1).

## Foundational comparisons

### Truth maintenance: Doyle (1979)

The MIT DSpace record for AI Memo 521 describes a TMS as recording reasons for
program beliefs and lists belief revision, dependency-directed backtracking,
and explanation among the paper's topics. The repository record also supplies
author/date and abstract. I could not retrieve the memo itself through MIT's
download endpoints, so details beyond that abstract are intentionally omitted.
[MIT DSpace primary record](https://dspace.mit.edu/handle/1721.1/5733).

**EMS comparison:** dependency-aware reason maintenance is clear prior art for
revising derived conclusions when assumptions change. It is a reasoning
subsystem; the accessible source does not establish EMS's proposed
substrate-independent event envelope, canonical bytes, source-revision replay,
or privacy boundary. No originality inference follows.

### Formal belief revision: AGM (1985)

The paper treats contraction (remove a proposition while preserving a theory)
and revision (admit a proposition inconsistent with a theory while restoring
consistency). Partial-meet contraction selects a non-empty family of maximal
subsets that do not entail the proposition, then intersects them. The authors
relate this construction to postulates and representation results; revision
can be defined using contraction and the Levi identity. These are formal
operator semantics over deductively closed theories, not timestamps, source
lineage, event bytes, or authority rules. [Primary publication DOI](https://doi.org/10.2307/2274239);
[reviewed paper copy](https://fitelson.org/piksi/piksi_22/agm.pdf).

**EMS comparison:** an assessment/revision policy plug-in is near the notion of
a selected revision operator, but EMS Decision 0003 does not choose an AGM
operator. A future policy must not silently import AGM postulates or assume
that source changes entail belief contraction. Whether a named operator helps
specify replay is a research question, not a design commitment.

### Database provenance: Green, Karvounarakis, and Tannen (2007)

The paper generalizes positive relational algebra over annotated `K`-relations
where annotations form a commutative semiring. Its provenance semiring uses
polynomials over input tuple identifiers to retain how query outputs derive
from input tuples, and extends the account to Datalog with fixed-point and
formal-power-series machinery. The authors distinguish “why” provenance from
the richer “how” derivation expression. They state limits: the positive
algebra framework does not include negation as presented, and they identify
extensions/conjectures as future work. [Author-hosted primary paper](https://www.cs.ucdavis.edu/~green/papers/pods07.pdf);
[PODS DOI](https://doi.org/10.1145/1265530.1265535).

**EMS comparison:** a replay record may need to identify inputs and derivation
paths; database provenance shows established formal work for recording
derivation lineage. Its semantics concern database query evaluation, not
whether an input assertion is true, which source governs, what a policy means,
or who may act. This distinction blocks an unsupported novelty claim around
“provenance.”

## Comparative synthesis

| Work | Main object | What its evidence can support | Boundary relative to EMS |
| --- | --- | --- | --- |
| MemLineage | Signed lineage and action gate | Conditional, narrow harness results | Trust label is not EMS truth or authority |
| MemConflict | Query-conditioned conflict benchmark | Simulated-query results | Benchmark gold is not source authority or replay correctness |
| STALE / CUPMem | Implicit-invalidation probes | Generated-case results | Latent inference is not immutable event replay |
| Doyle TMS | Reasons for beliefs and revision/backtracking | Abstract-level evidence that dependency-directed belief maintenance predates EMS | Full-text detail not read; not portable event serialization/replay evidence |
| AGM | Formal contraction/revision operators | Prior formal characterization of classes of theory change | EMS has no accepted belief-revision operator and no truth-state semantics |
| Provenance Semirings | Input tuple lineage through database queries | Formal algebra for derivation provenance in positive relational algebra/Datalog | Not source authority, epistemic assessment, privacy policy, or action authorization |

The common problem word “memory” hides different targets: cryptographic
custody, database derivation, logical belief revision, benchmark answer
validity, latent user-state inference, and EMS event reconstruction. Similar
vocabulary does not establish equivalent semantics.

## Candidate cases and falsifiers for later review

These are prose cases only. They add no fixture, schema, expected bytes, or
accepted behavior. They should be reconciled with dossier cases V20–V24 before
any later case-selection decision.

1. **Authenticity versus correctness.** A synthetic signed record has valid
   canonical bytes and a valid registered signature, but a second declared
   observation contradicts its proposition. A future projection should report
   integrity/origin separately from the policy result. Falsifier: signature or
   “trusted” label alone upgrades the proposition to true, verified, or
   actionable.
2. **Retrieval/rank versus assessment.** In the initial qualitative workbench,
   hold declared evidence, source revision, and named policy fixed; vary only
   retrieval rank or add a distractor. Rank alone must not change assessment.
   Falsifier: top rank, duplication, or popularity changes the assessment.
   Any future policy that intentionally consumes rank requires separate
   review; it is not adopted here.
3. **Query condition versus timeless claim.** Keep evidence fixed; ask two
   questions with different declared valid-time intervals or conditional
   scopes. A future policy may return different query-scoped views while
   preserving event history. Falsifier: one unqualified answer overwrites
   source history or hides the selected scope.
4. **Implicit dependency versus automatic invalidation.** A new event changes
   a declared attribute A; an older claim about B is incompatible only if a
   particular dependency rule applies. With a pinned policy and declared
   relation, replay may emit a policy-labelled challenge or revision result.
   Without that relation, keep outcome unresolved/unsupported. Falsifier:
   chronology or model inference alone rewrites B's event or history.
5. **Premise resistance versus action authority.** A question presupposes an
   obsolete premise and asks for a side-effecting action, but no authority
   record exists. Content correction, abstention, source evidence, and action
   authority must remain separately reviewable. Falsifier: a correct answer
   automatically grants permission, or every refusal is scored as error.

The first four cases test whether source binding, scoped policy, replay, and
derived views remain separate. The fifth is only an interface to a future,
separately authorized agent study; this dossier and paper results authorize no
agent run.

## Measurement implications

Any later protocol should keep these quantities distinct rather than combine
them into one “memory quality” score:

| Question | Possible observation in a later protocol | Do not infer |
| --- | --- | --- |
| Is record history valid? | Exact bytes, event order, parent links, schema/policy identities, and stable replay result or error | The proposition is true |
| Is evidence traceable? | Source revision, observation conditions, dependency links, and cutoff availability | The source is authoritative or independent |
| Is retrieval effective? | Supporting item returned, rank, and query scope | A retrieved item was used or applicable |
| Is assessment correct under policy? | Output compared with separately reviewed expected result for declared inputs/policy | Universal truth or calibrated probability |
| Is a human inspection surface useful? | Matched manual baseline, correct/scorable rate, review time, setup and maintenance burden | Agent task benefit or general user utility |
| Is an action authorized? | Separate authority record and action-specific review in a future study | Assessment or memory presence grants permission |

Measure retrieval, assessment, use, downstream behavior, and missing-parent
rejection separately if later work studies them. This is a proposal; no metric,
threshold, or software requirement is frozen.

For contract correctness, independent expected outputs should come from a
reviewed source trace and selected policy, not from copying one implementation's
answers. Agreement among implementations is insufficient by itself if all
share one flawed expected result. For maintainer utility, the current dossier's
manual B0 remains the relevant candidate baseline: same evidence, revision,
policy, cutoff, and question, with only a structured explanation surface
changed. Any agent or action-utility study would require a separate protocol,
permissions, budget, and authorization.

## Unknowns and stop boundary

- No source paper, benchmark, or database provenance model demonstrates that
  the proposed EMS composition is novel, safe, transferable, or interoperable.
- No paper outcome establishes correctness of an EMS schema, canonicalization,
  replay implementation, source adapter, retention rule, or assessment policy.
- No paper artifact was run, codebase inspected, or result independently
  replicated in this task.
- No current product compatibility, post-v1 arXiv revision, publication status,
  or later code change was checked.
- Doyle's 1979 full text remains inaccessible through the attempted MIT DSpace
  endpoints; only the repository record and abstract support the limited note.
- The AGM full text came from a mirror; only selected opening sections were
  examined. Green et al.'s author-hosted full text was read, but not tested.
- The three recent studies rely in part on synthetic or fixed benchmark
  constructions. Their author-reported results do not establish general
  performance in private corpora, live deployments, other source domains, or
  EMS's proposed manual workbench.
- All EMS advancement gates remain **UNACCEPTED**. No implementation,
  experiment, human study, real-data access, agent execution, publication, or
  interoperability claim follows from this literature review.
