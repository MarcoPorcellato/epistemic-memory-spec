# Methods for a Later Epistemic Replay Study

**Status:** Prepared for public review; non-normative documentary synthesis,
2026-10-04. No original experimental results are claimed; external findings
remain attributed to their authors. All G1–G7 gates remain UNACCEPTED.
**Snapshot reviewed:** `cdeff0fbec369b440f70c2cfb7cc3b8cdee12fc5`.
**Scope:** Study-design guidance for [the programme](replay-study-programme.md) and [the workbench
dossier](epistemic-replay-workbench-dossier.md). Not a preregistration, frozen protocol, analysis
plan, accepted gate, experiment, result, or authorization to execute or publish.

## Decision boundary

The workbench dossier separates three questions that need different evidence:

1. **Contract and replay correctness (Q1–Q2, later G1–G5):** can a reviewed profile specify bounded
   outputs or rejections that a later independent implementation reproduces from declared material?
2. **Maintainer inspection utility (Q3):** for one maintainer and bounded synthetic cases, does an
   inspectable explanation justify its setup, correction, review, and maintenance burden over B0?
3. **Agent task utility (Q4):** in a separate study, does a named information condition improve
   outcomes under matched models, tools, permissions, budgets, and information cutoffs?

Agreement on fixed replay vectors cannot establish user utility; a maintainer pilot cannot establish
agent benefit. More tool calls, stored records, or citations do not establish better decisions. Do
not pool these questions into one score or claim.

## Evidence registry

Access depth records what was inspected on 2026-10-04. Live documentation can change; entries bind
sources by title, DOI or official location, and inspected sections, not an immutable snapshot.

| Source and identity | Version / access depth | Relevance and limit |
| --- | --- | --- |
| [OSF, “Welcome to Registrations & Preregistrations”](https://help.osf.io/article/330-welcome-to-registrations) | Live OSF Support page, last updated 2026-08-11; accessed 2026-10-04. Targeted read of “Overview,” “Effective Practices,” “Preparing your Registration,” “Update a registration,” and selected registration FAQs; page reports 999 lines. | Official registry guidance on timestamped read-only plans, plans before data collection or analysis, outcomes, exclusions, planned and unplanned work, contingencies, and updates. Platform process guidance, not a statistical standard for this study. |
| [Nosek et al., “The preregistration revolution,” PNAS 115(11), 2600–2606 (2018)](https://doi.org/10.1073/pnas.1708274114) | Published article; full publisher HTML available and targeted sections read: “Preregistration Distinguishes Prediction and Postdiction,” exploratory research discussion, and conclusion. | Primary methodological argument for distinguishing prediction from postdiction, preserving all planned outcomes, and using exploration to generate future predictions. The authors state preregistration’s benefits are not established as universally superior by experimental evidence. |
| [Lakens, “Sample Size Justification,” Collabra: Psychology 8(1), 33267 (2022)](https://doi.org/10.1525/collabra.33267) | Published article; full publisher HTML available and targeted sections read: inferential goals, resource constraints, smallest effect size of interest, precision, and sensitivity analysis. | Primary methods overview. It treats resource constraints, power, precision, heuristic choice, and an explicit lack of justification as distinct sample-size rationales. It does not supply an EMS sample size. |
| [Lakens, “Equivalence Tests: A Practical Primer for t Tests, Correlations, and Meta-Analyses,” SPPS 8(4), 355–362 (2017)](https://doi.org/10.1177/1948550617697177) | Published open-access article; full publisher HTML available and targeted sections read: TOST, outcome combinations, and dependent means. | Primary methods tutorial. A nonsignificant result alone does not support absence; practical equivalence needs prespecified bounds tied to a smallest effect of interest. The article also explains paired/dependent-mean calculations. No bound or test is selected here. |
| [Hurlbert, “Pseudoreplication and the Design of Ecological Field Experiments,” Ecological Monographs 54(2), 187–211 (1984)](https://doi.org/10.2307/1942661) | Publisher metadata and abstract read; full article PDF inspected from this [university-hosted copy](https://faculty.fiu.edu/~stoddard/courses/IBR/readings/Hurlbert_1984.pdf), especially “Multiple samples per experimental unit” and “Temporal pseudoreplication.” | Primary design paper warns that repeated samples from one experimental unit do not create independent treatment replicates. Ecological field examples; transfer here is the unit/dependence principle, not ecological design prescriptions. |
| [NeurIPS, Paper Checklist](https://neurips.cc/public/guides/PaperChecklist) | Official live guide, no revision date shown; accessed 2026-10-04. Targeted read of items 5–8: reproducibility, data/code, experimental setting, statistical significance, compute resources. | Field-specific reporting example: give a reproducibility path, exact commands/environment, setting details, sources and method for variability summaries, and compute per run and overall, including unreported preliminary or failed work. It is not a universal benchmark standard or an EMS requirement. |

## Compact source facts

- OSF defines preregistration as a time-stamped, read-only submitted snapshot made before data
  collection or analysis. Its update workflow creates a later draft update and requires a reason.
  Immutability applies to each submitted snapshot; it coexists with separately traceable, justified
  amendments. For EMS, retain the original plan and date/reason each amendment without treating
  change as misconduct.
- Nosek et al. distinguish prediction from postdiction. Exploration remains valuable for discovery
  and can motivate later confirmation. Full outcome reporting and accessible plans help reveal
  selective reporting; preregistration alone does not remove multiple-comparison or cross-study
  selection problems.
- Lakens (2022) says sample-size rationale should match the inferential goal: finite-population
  coverage, resource constraints, a priori power, desired precision, a heuristic, or explicit lack of
  justification. Consider what effects matter and what the design can estimate or exclude. Describe
  a resource-limited pilot as such, not as adequately powered evidence.
- Lakens (2017) shows why nonsignificance alone is not evidence of no meaningful effect. Equivalence
  requires prespecified bounds and enough precision to exclude effects outside them. For paired
  outcomes, dependence between observations enters the analysis; paired scores are not independent
  samples.
- Hurlbert distinguishes measurements within one experimental unit from independent replication.
  Repeated measurements may improve unit-level precision but do not multiply independent units;
  analysis must respect the unit and dependence structure.
- The current NeurIPS checklist asks for a reproducibility path, experimental details, defined error
  bars and calculation method, and per-run and total compute, including preliminary and failed work.
  These reporting prompts do not validate results or make a study generalizable.

## Proposed synthesis for EMS

### Manual maintainer study

Treat Q3 as a bounded, within-maintainer feasibility and utility study over
synthetic cases. The maintainer is one reader, not a sample of users. Repeated
cases can reveal where this reader spends time or corrects an explanation;
they do not establish population-level usability, inter-reader agreement, or
agent benefit.

B0 and the explanation condition should expose the same underlying synthetic
source representations, revision references, relations, policy text, scope,
cutoff, valid intervals, and update history. The treatment is the organization
and inspectable derivation. Any extra interpretation, hint, or evidence is a
condition difference and must be disclosed. Pair conditions on the same case
where feasible. Record presentation order and prior exposure, since seeing a
case once can teach its answer. A single-maintainer comparison remains
descriptive even if case order is counterbalanced.

Keep practical observations separate: resolution and source/policy binding;
unsupported promotions or missed conflicts; setup, inspection, correction,
maintenance, and explanation-review effort; and the maintainer’s reported
uncertainty. Do not let shorter time offset source substitution, an incorrect
derivation, or an authority-boundary violation. Do not use one maintainer’s
ratings as independent participants.

If B0 already resolves the bounded cases with acceptable effort, or the
explanation condition adds burden without a decision-relevant improvement,
that is a direct falsifier for building this workbench for the stated Q3 need.
It does not falsify source-bound replay as a separate Q1–Q2 research question.

### Later agent studies

Q4 needs its own protocol and authorization. It is not an extension of the
maintainer pilot. State the target task population, condition contrast,
information available at each cutoff, model and tool state, permissions,
exposure and cost ceilings, and primary outcome before outcomes are visible.
Audit that conditions differ only in the declared treatment; keep no-memory,
source-evidence, and explanation conditions conceptually distinct if later
selected. Include cases where the answer is already present to test unnecessary
retrieval, as the programme proposes.

Name the experimental unit before counting observations. A task, case, prompt,
run, session, model instance, and case family are not interchangeable units.
If each condition sees the same cases, the case-level contrast is paired or
matched. Repeated runs on the same case, model, or session may be dependent;
cluster or otherwise model that dependence, or report descriptive case-level
results without pretending each score is an independent replicate. Case-family
coverage and independent task/model replication answer different questions.
No model, allocation, number of runs, test, or analysis method is chosen here.

Report capture, eligible exposure, interpretation, actual use, and task
outcome separately. Uptake can rise without utility. A task answer can be
correct for the wrong source revision; a refusal can be justified or
unjustified. Include justified uncertainty, abstention, source/policy binding,
and authority violations in the endpoint rubric rather than scoring activity
counts as success.

### Precision and practical equivalence

Before any inferential Q3 or Q4 claim, an owner-reviewed protocol must state
the estimand and what difference would matter for the decision. A practical
margin, if one is used, needs a defensible rationale independent of observed
results. Do not borrow conventional “small/medium/large” values or invent a
margin because available resources make it convenient.

Then justify available cases or runs against that goal: define whether the
study covers a fixed finite synthetic set or samples a broader task universe;
state the feasible N and why; show expected precision or sensitivity over
plausible effects, including what the design cannot distinguish. If only
resource constraints determine N, report the study as exploratory/descriptive
and bound conclusions to observed cases. If the required precision is not
feasible, keep the outcome inconclusive rather than weakening the practical
margin after results are seen.

For a fixed, exhaustively enumerated replay vector set, report exact coverage,
agreement, mismatches, and rejected or unsupported cases against independent
expectations. That is a profile-specific census, not a random sample of all
possible histories. For human utility or future agent effects, task cases may
be correlated or unrepresentative; report uncertainty at the defensible unit
and avoid generalization beyond the sampled population. This note chooses no
sample size, power target, margin, budget, or hypothesis test.

### Artifact and benchmark record

Any later authorized study report should make the exact evaluated artifact
auditable. Preserve a manifest for protocol version and dated amendments;
synthetic case-set identity and version; expected-outcome review; implementation
or model and version; relevant environment and configuration; exact invocation
or interaction procedure; assigned and completed units; exclusions and
missingness; outcome/scoring rules; per-case results; deviations; and a clear
record of successful, failed, timed-out, and preliminary work. Report time,
operator effort, compute, and other costs as separate measures. Give the
variability or uncertainty method and its unit, not just an unlabeled average
or error bar. Retain enough synthetic material and instructions for another
reviewer to reconstruct the bounded claim. Do not include genuine source
content, identities, credentials, personal data, or absolute local paths.

## Proposed pre-freeze checklist

Before a later study protocol can be reviewed for freeze, resolve and record:

- Which one question is primary: semantic specification, replay agreement,
  maintainer inspection utility, or agent task utility? Which claims are
  expressly outside scope?
- What is the estimand, target case/task population, and experimental unit?
  Which task families are included, excluded, unsupported, or reserved for
  later work, and why?
- What information, source revisions, policy, cutoff, tools, model state, and
  permissions are available in each condition? Are treatment and baseline
  otherwise matched? What counts as an information leak?
- Which cases are paired across conditions? What is randomized or
  counterbalanced? Which observations share reader, case, session, model, or
  family, and how will dependence affect reporting or analysis?
- What is the primary endpoint and scoring rubric? Can it distinguish useful
  inspection from source substitution, lucky correctness, hindsight, or
  activity? Are outcome expectations reviewed without access to condition
  results?
- What are the scoreability, missing-input, exclusion, timeout, invalid-endpoint,
  protocol-deviation, and execution-failure rules? Are valid null and
  inconclusive outcomes retained without endpoint switching?
- Which work is confirmatory and which exploratory? What primary/secondary
  outcomes and multiplicity or sensitivity issues will be reported? How will
  amendments be timestamped and compared with the original plan?
- What precision can the feasible sample provide for the stated inferential
  goal? Is N a census of a finite synthetic set, a resource-limited pilot, or
  a sample intended to support a broader claim? What remains undetectable?
- If a practical decision margin is required, who accepts its rationale and
  before which outcomes are exposed? What will be concluded if it cannot be
  justified or met?
- What artifact/version, exact environment, run details, per-unit outcomes,
  uncertainty method, costs, deviations, failures, and synthetic-only evidence
  will be retained for inspection?
- What result would stop the proposed workbench or falsify its claimed value?
  What result would merely leave the question unresolved?

No later design is ready for freeze while any answer depends on seeing the
outcome, silently substitutes a source/policy revision, treats repeated
observations as independent without justification, or turns a documentary
decision into execution or publication authority.

## Outcome vocabulary for later use

| Label | Required state | Permitted interpretation |
| --- | --- | --- |
| **Valid null pattern** | Study ran under its declared protocol; endpoint is valid and scorable. A bounded no-benefit or practical-equivalence conclusion additionally requires an a priori decision margin and sufficient precision for it. | Report observed estimate and uncertainty. A nonsignificant test or zero point estimate alone does not show no meaningful benefit. A fixed-set replay null is bounded to that enumerated profile. |
| **Inconclusive** | Study ran and endpoint is valid, but uncertainty, missing scorable cases, or limited coverage cannot distinguish useful benefit from a decision-relevant alternative. | State what remains compatible with the evidence. Do not label it equivalence, no effect, or a pass. |
| **Invalid endpoint** | The rubric, cases, condition contrast, or scoring process cannot measure the declared construct or discriminate the conditions; examples include leakage, unreviewed expected answers, or a score insensitive to relevant failure. | Do not treat resulting scores as evidence for or against utility. Preserve the diagnosis; revise and review a new protocol before any new study. |
| **Execution failure** | Required study steps or artifacts did not complete because of an operational fault, timeout, missing prerequisite, or corrupt/incomplete record. | Report the failure and retained artifacts separately from task outcomes. It is neither a negative result nor an implicit retry authorization. |

Also report supported-profile exclusions and explicit rejections separately:
they can be valid bounded behavior under a reviewed rule, whereas a broken
endpoint or an incomplete run cannot be promoted to success by a plausible
answer.

## Limits and unresolved decisions

These sources justify transparent protocol records, clear exploratory versus
confirmatory labels, dependence-aware units, honest precision claims, and
auditable benchmark reporting. They do not choose the EMS estimand, case set,
scorer, user population, implementation, model, sample size, analysis method,
practical margin, power target, or resource budget. The single-maintainer Q3
study can only provide bounded within-person evidence. Any agent Q4 study would
require a distinct design, review, and authorization. G1–G7 remain unaccepted;
no protocol is frozen and no experiment has been run.
