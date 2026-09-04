# Explicit Strategic Learning: Phase 1 preregistration draft

> **Status: PROPOSAL — NOT FROZEN — NO OUTCOMES ACCESSED.**

## Status, scope, and governing sources

This is a maintainer-facing protocol proposal for Track 14. It is not a frozen
registration, task suite, benchmark, implementation, runtime, schema, or
evaluation authorisation. No task instances, model outcomes, evaluation
outputs, or experimental results have been accessed for this draft.

The proposed protocol is bound to current source commit
`973f2ada3d4918d2f4ce1e71149972728356c278` and is governed by:

- [Decision 0004](../docs/decisions/0004-incubating-strategic-agent-learning.md);
- [Open research agenda](../OPEN_RESEARCH.md), Track 14;
- [Phase 0 prior-art and terminology review](explicit-strategic-learning-phase-0-review.md);
- [Next gated research phases](explicit-strategic-learning-next-phases-plan.md);
- [Contribution rules](../CONTRIBUTING.md); and
- [Governance](../GOVERNANCE.md).

The candidate strategic operator remains a provisional research construct. It
is not a data entity, schema field, runtime abstraction, learned skill, policy,
prompt, retrieved example, tool invocation, reasoning trace, latent feature,
or model update. Evidence recorded by a later evaluation must remain distinct
from any named policy-derived assessment and from truth. No Matryca Plumber
change follows from this proposal.

The OSF registration guidance describes registrations as a way to record plans
and analysis decisions before data collection, and the NeurIPS paper checklist
asks authors to disclose claims, limitations, reproducibility information, and
experimental details. They are procedural guidance for this draft, not evidence
that the candidate exists, transfers, is safe, is aligned, or improves any
outcome. See [OSF registrations guidance](https://help.osf.io/article/330-welcome-to-registrations)
and the [NeurIPS paper checklist](https://neurips.cc/public/guides/PaperChecklist).

## Proposed question and bounded claim

Given the same finite-domain synthetic constraint-satisfaction task, source
exposure boundary, model state, and declared budget, does an independently
specified normalisation-and-contradiction intervention improve source-blind,
grouped held-out structural-family solving over matched decomposition and
direct-solution controls?

The only possible positive conclusion is a bounded comparison under the frozen
protocol. It would not establish novelty, causal internal model use, safety,
alignment, lifelong learning, general agent improvement, or transfer outside
the registered held-out structural family.

## Candidate transformation

The proposed candidate is **explicit constraint normalisation plus
contradiction inventory**:

1. Rewrite each constraint into a canonical representation containing subject,
   relation, and object or value.
2. Form equality classes and rewrite each constraint to a declared class
   representative.
3. Inventory incompatible assignments, prohibited equalities, and relation
   conflicts within each class.
4. Decide satisfiability and return a verifier-checkable assignment or
   contradiction certificate.

This text states a hypothesised representation transformation independently of
the exact prompt wording. It is still at risk of collapsing into a procedure or
prompting technique. The arms, prompt-family controls, output controls, and
construct-collapse gate below exist to test that risk rather than assume it is
resolved.

### Pre-freeze construct-separability gate

Before any protocol is frozen, an independent reviewer must be able to express
the transformation without copying its ordered steps or exact prompt wording.
If the reviewer cannot do so, the proposal stops and is classified as a
procedure-level intervention rather than a candidate strategic operator.

If the reviewer can specify an equivalent solver workflow with a different
representation, the frozen protocol must add the conditional `P`
procedure-equivalence diagnostic arm described below. That decision is a freeze
blocker: `P` cannot be silently omitted after the reviewer identifies an
equivalent workflow, and it cannot rescue a failed `T-C` primary comparison.

## Unit, block, and proposed task family

### Unit and block

The unit of analysis is one eligible CSP instance under one arm. A block is one
instance evaluated once under every arm in independent fresh contexts. No arm
may receive output, trace, tool result, model state, retrieval result, or
feedback from any other arm in its block.

### Proposed finite-domain CSP language

The eventual frozen task language will use finite domains and a bounded formal
grammar. The proposed relation classes are equality, inequality, unary equality,
and unary exclusion. Each instance requires one of two final forms:

- `SAT` with a complete satisfying assignment; or
- `UNSAT` with a certificate accepted by a frozen verifier.

SAT instances will have a known satisfying assignment. UNSAT instances will
contain a registered, verifier-checkable contradiction, such as an equality
path combined with an incompatible disequality or incompatible unary
requirements. The verifier may score only the final verdict and certificate or
assignment; a plausible intermediate inventory is not itself a successful
outcome.

Every arm uses the identical final-answer schema and guidance: `SAT` requires a
complete assignment in the frozen representation; `UNSAT` requires the same
frozen certificate grammar, including all required constraint identifiers and
path fields. SAT and UNSAT instances must be equally allocated within every
primary subfamily and reported separately in all primary and regression tables.

### Structural groups and split

| Split role | Proposed structural group | Access rule |
| --- | --- | --- |
| Development only | Connected single-cycle constraint graphs. | Candidate authors may inspect only this group and its registered development materials. It is never primary evidence. |
| Source-blind primary evaluation | Connected cactus graphs with at least two cycles. Primary subfamilies are: two cycles sharing an articulation vertex, and two cycles joined by a non-empty path. | Concrete instances, seeds, answers, contradiction certificates, surface serialisations, and split-manifest contents remain inaccessible until protocol freeze and later authorised evaluation. |
| Diagnostic only | Registered alternate serialisations of the same formal language. | May identify surface dependence but cannot replace primary structural-family result. |

The split is by latent generator parameters and graph structure, not by a
surface family name alone. Constraint vocabulary, ordering templates,
contradiction forms, graph motifs, and generator provenance must be reviewed
for cross-split leakage before any outcomes are accessed.

### Proposed eligibility conditions

An instance is eligible only if it:

- validates against the frozen grammar and declared finite-domain envelope;
- belongs to its frozen structural group and source-exposure split;
- has a recorded seed and instance hash;
- has a verifier-confirmed SAT assignment or UNSAT certificate before model
  evaluation;
- meets predeclared balance strata for satisfiability label and cactus
  subfamily; and
- has not appeared in development material, prompt examples, retrieval
  material, model feedback, or any prior arm output.

Instances rejected by the generator or verifier before any model output may be
replaced only through a frozen, logged reserve-instance rule. No outcome-seen
instance may be dropped, repaired, replaced, regrouped, or relabelled.

## Source exposure and confound controls

The primary source-blind arm permits no retrieval corpus, external examples,
solved demonstrations, tool result, human feedback, or model update. Every
prompt, task input, output, tool-access state, and retrieval-access state must
be retained in provenance.

Before evaluation, the maintainer must freeze and independently review:

- a split manifest and seed manifest before any held-out outcome is visible;
- a leakage audit with zero exact instance, solution, certificate, or rendered-
  string overlap across development and source-blind evaluation materials;
- disclosed graph-motif, equality-path, contradiction-form, and lexical-
  template overlap, even when it is not disqualifying;
- prompt-family membership and the assignment of paraphrases to arms;
- fresh-context isolation and absence of cross-arm state; and
- evidence that the held-out materials were not used in candidate formulation.

Any source-exposure breach, unavailable manifest, non-empty retrieval/tool
evidence, or unlogged task material makes the primary comparison
`non_interpretable`. It cannot be relabelled as a null result.

Even after a clean leakage audit, any result is restricted to the defined
structural extrapolation from single-cycle development graphs to the frozen
cactus groups. It is never a general transfer claim.

The protocol will not make a causal claim from a visible reasoning trace.
Intermediate normalisations and inventories are treatment artefacts. Their
quality may be retained as process evidence, but final solving is independently
scored. An externally supplied inventory or a hidden-scratch condition is not
part of this proposal; without a separately reviewed version that adds and
controls such conditions, no claim about trace faithfulness or causal mechanism
is permitted.

## Proposed arms and matched controls

All arms receive the same task instance, final answer schema and certificate
guidance, model/environment state, context limit, output-token ceiling, tool
access, retrieval access, feedback access, time ceiling, and scoring rule.
Exact prompts use frozen slot layouts. Where arms are compared, they receive
the same maximum and planned intermediate-slot and token burden; neutral slots
must be supplied where an arm does not use a semantic intermediate artefact.
Prompt variants are drawn from a frozen paraphrase family and balanced across
arms; a single favourable wording cannot supply a positive conclusion. Actual
input/output tokens, intermediate-slot use, and wall time are retained.

| Arm | Proposed intervention | Confounds addressed | Role |
| --- | --- | --- | --- |
| `D` | Directly decide satisfiability and return final verifier-checkable answer. | Establishes direct-solution reference at same final-answer format and budget. | Baseline. |
| `C` | Perform a generic, non-semantic decomposition: record constraint identifier and mentioned variables in a fixed, order-rotated layout, then decide and certify. | Matches added instruction, output slots, attention demand, and deliberation opportunity without semantic normalisation or contradiction inventory. | Primary matched process control. |
| `N` | Perform canonicalisation and equality-class representation, then decide and certify; do not request contradiction inventory. | Tests whether normalisation alone explains a full-treatment result. | Component ablation. |
| `I` | Inventory explicit conflicts from original constraints, then decide and certify; do not request equality-class canonicalisation. | Tests whether inventory alone explains a full-treatment result. | Component ablation. |
| `T` | Perform normalisation, equality-class rewrite, and contradiction inventory, then decide and certify. | Candidate treatment. | Primary treatment. |
| `P` | Only if the independent reviewer satisfies the pre-freeze gate: execute a reviewer-specified solver workflow that is equivalent in intended work but uses a different representation. | Distinguishes representation transformation from procedure-equivalent workflow. | Conditional diagnostic; required when specified. |

`T-C` is the only primary comparison. `T-D`, `T-N`, and `T-I` are
predeclared diagnostic comparisons and cannot rescue a failed primary outcome.
The control's layout rotation must be frozen so that a superficial ordering
effect does not remain hidden inside a single generic prompt. Candidate-order
shuffling and an externally supplied-inventory condition are not silently
assumed: they require explicit addition, matching, and approval before they can
support any stronger causal conclusion.

If the frozen slot, planned token-burden, certificate-guidance, or time-parity
criterion fails, `T-C` is evidence about a treatment bundle, not an isolated
operator. A material failure to establish or retain parity makes the comparison
`non_interpretable`; a minor, preclassified deviation may only be reported as
treatment-bundle evidence and cannot support an operator claim.

No parser, solver, checker, or external tool may be available to one arm only.
If a verifier is used after generation, it is evaluator infrastructure, not a
model-visible tool. Model-visible tool availability, call budget, arguments,
results, and failures must be identical and logged; this proposal expects all
model-visible tool budgets to be zero.

## Freeze record and budget envelope

Before primary outcomes are accessed, freeze and hash:

- repository commit, protocol revision, candidate statement, arm prompts,
  prompt-family variants, final-answer grammar, and output parser;
- task-language grammar, finite-domain and size envelope, generator version,
  verifier grammar/version, structural split manifest, seeds, and instance
  hashes;
- provider-neutral model identifier and revision, API/runtime version,
  decoding configuration, context window, seed policy, retry policy,
  fresh-context policy, execution environment, and timeout;
- arm-code mapping, randomisation seed, invocation order rule, analyst-blinding
  rule, scorer/verifier identity, and provenance-retention policy;
- input/output token accounting method, maximum input size, maximum output
  tokens, invocation count, wall-time ceiling, and optional compute/energy
  proxy; and
- zero-tool, zero-retrieval, zero-external-example, zero-human-feedback, and
  zero-model-update declarations.

Every arm has one fresh model invocation per instance unless a frozen
transport-only rule proves that no response body, token usage, or model output
was received. A retry with any response body, token usage, partial output, or
model output is an outcome and cannot be replaced.

### Explicit freeze blockers

This proposal cannot become a preregistration until it records concrete values
for all of the following:

1. model identifier and revision, environment, decoding, seed, timeout, and
   context configuration;
2. finite-domain task envelope, exact grammar, output parser, verifier grammar,
   and certificate validity rules;
3. prompt texts, paraphrase family, arm layouts, and output-token parity rule;
4. input/output token, time, compute, and total call ceilings;
5. practical threshold `delta`, confidence-interval half-width `h`, coverage,
   sample-size result, reserve-instance count, and maximum protocol attempts;
6. generator, split, seed, contamination-review, and provenance-manifest
   ownership; and
7. evaluator, blinding, deviation, and evidence-retention procedures.

If an independent reviewer identifies a representation-distinct but
procedure-equivalent workflow, the reviewer specification and `P` arm must be
frozen as an additional blocker.

These are freeze blockers, not placeholders to be chosen implicitly during
evaluation.

## Metrics, estimand, regressions, and cost decision

### Primary metric and estimand

For each source-blind cactus subfamily, calculate `verified_solve_rate`:

```text
correct SAT/UNSAT verdict and verifier-accepted assignment or certificate
--------------------------------------------------------------------------
                         eligible instances
```

Let `n_total` be the total eligible blocks across both cactus subfamilies and
both SAT/UNSAT strata. It must be divisible into equal allocation across the
four subfamily-by-label strata before outcomes are accessed. The primary
estimand is the unweighted mean, across the two frozen cactus subfamilies, of
the block-paired difference in `verified_solve_rate(T) - verified_solve_rate(C)`.
Family-level aggregation is primary; pooling all instances without the
registered subfamily summary is not permitted.

### Secondary and regression measures

Secondary measures are descriptive unless a later frozen protocol states
otherwise:

- verdict accuracy;
- valid SAT-witness rate and valid UNSAT-certificate rate;
- independently scorable contradiction-detection precision and recall, only if
  verifier grammar makes both meaningful;
- invalid, unparseable, timeout, retry, and non-completion rates;
- input tokens, output tokens, wall time, compute proxy, and model-visible tool
  calls;
- variation across source-exposed and source-blind groups, seeds, labels, and
  cactus subfamilies; and
- `T-D`, `T-N`, and `T-I` diagnostic contrasts.

Mandatory regression disclosure includes every decrease in verdict, witness, or
certificate validity; every increase in tokens, time, compute proxy, tool calls,
invalid output, timeout, or variance; and every deviation, exclusion,
replacement, failure, or non-interpretable outcome. No shorter response or
faster completion is “accelerated” unless the registered primary comparison and
matched budget support the exact limited statement.

### Candidate decision method and cost implications

No expected effect is assumed. Before outcomes, the maintainer must choose a
minimum practically relevant difference `delta`, desired two-sided interval
half-width `h`, nominal coverage, interval method, multiplicity handling, and
a conservative paired-binary precision rule. For paired block difference
`D_i ∈ {-1, 0, 1}`, the proposed conservative planning upper-bound target is:

```text
n_total_plan = 4 × ceil(ceil((z_coverage / h)^2) / 4)
n_total >= n_total_plan
```

This rounds the conservative planning upper-bound target to equal allocation
across four subfamily-by-label strata; it is not a claim that an effect exists.
Before freeze, finite-sample simulation or another documented finite-sample
confirmation must verify that the selected interval method, coverage, equal
allocation, and planned analysis achieve the intended precision. The final
protocol must also freeze intention-to-treat handling for missing or invalid
blocks; no block may be excluded after allocation because an arm fails. Missing
or invalid-block handling is a freeze blocker.

Without `P`, the minimum direct execution envelope is `n_total × 5` model calls
before permitted transport-only retries. If the pre-freeze separability gate
requires `P`, it rises to `n_total × 6` model calls. Total token, time, compute,
and monetary cost cannot be estimated until the blocked call ceiling, model
identifier, token ceilings, and execution environment are fixed. A cost
estimate must be reviewed before any Phase 3 authorisation; it is not a
cost-saving or performance claim.

## Randomisation, blinding, and analysis

Randomise anonymised arm codes within each instance block from a frozen seed;
stratify allocation by cactus subfamily and satisfiability label. Randomise
invocation order using a stable instance-hash rule. All calls use fresh contexts
and independent state.

Score final answers with frozen deterministic verifier/parser outputs before
unblinding arm labels in the analysis table. If scorer determinism, arm masking,
or analyst masking cannot be maintained, record the deviation and apply the
registered `non_interpretable` rule where attribution is undermined.

Primary analysis uses all eligible source-blind blocks under intention-to-treat.
Report, for each cactus subfamily and their unweighted aggregate: paired
contingency counts, `T-C` estimate, registered confidence interval, and result
against the frozen `delta` rule. The proposed positive form is that the lower
bound of the frozen two-sided confidence interval for `T-C` exceeds `delta`.
Exact `delta`, coverage, interval method, and multiplicity handling remain
freeze blockers. A paired binary inferential test may be named only before
outcomes and is supplementary to the declared estimand and interval. Secondary
measures remain labelled secondary; they cannot replace primary metric, task
family, candidate, baseline, or source-exposure policy.

## Labels, stop rules, and provenance

| Label | Registered meaning |
| --- | --- |
| `positive` | Primary comparison meets frozen practical and interval rule, no disqualifying protocol breach occurs, and all mandatory regressions are reported. The conclusion is limited to registered conditions. |
| `null` | Primary estimand is evaluated under intact protocol but does not meet positive rule. |
| `failed` | Operational, generator, verifier, environment, or evaluation failure prevents a valid estimand. |
| `non_interpretable` | Source exposure, split failure, unmatched budget/control, model/environment drift, scorer defect, broken randomisation/blinding, missing provenance, or material protocol deviation prevents valid attribution. |

Stop all new evaluation immediately for any source-exposure breach, unavailable
or invalid split manifest, non-zero unapproved tool/retrieval/feedback access,
model/environment freeze mismatch, unequal budget, verifier/parser defect,
scorer nondeterminism, invalid randomisation, or missing provenance. Preserve
terminal records. Never convert `failed` or `non_interpretable` into `null`.
No rerun, repair, metric change, task-family change, sample enlargement, or
candidate revision is permitted without a newly reviewed protocol version and
separate explicit authorisation.

For every instance-arm, retain task and instance hashes, seed, split label,
prompt and prompt-variant hash, arm code, model/environment fields, budget
accounting, raw output policy, parser/verifier result, completion state,
deviation record, and analysis revision. These are provenance-bound evidence,
not policy-derived assessments.

## Construct-collapse gate

The candidate must not be promoted merely because an arm produces a higher
score. It is collapsed, unnecessary, or misleading for this family if:

- `T-C` does not meet the frozen primary decision rule;
- a matched process/prompt control accounts for apparent difference;
- `N`, `I`, or `D` fully explains any `T` result, leaving no registered
  incremental contribution from the combined intervention;
- the effect depends on one exact wording, undeclared surface template,
  source-exposed material, retrieval, tool access, model update, or output
  leakage;
- the transformation cannot be stated independently of the exact prompt or
  ordered procedure; or
- a mandatory regression or `non_interpretable` condition occurs.

A result passing this gate would still support only the recorded experimental
comparison. It does not convert evidence into assessment, policy, truth, or
deployment authority.

## Authorisation boundaries

This document authorises nothing. Maintainer approval may authorise only a
frozen Phase 1 document after every blocker is resolved. Separate explicit
authorisation is required for Phase 2 task materials, and another exact
authorisation is required for any Phase 3 evaluation; that evaluation authority
must bind source commit, protocol digest, model/environment, budgets, maximum
calls, outputs, and stop boundary.

No phase of this proposal authorises a schema, runtime, benchmark publication,
model-training programme, Matryca Plumber work, issue publication, repository
creation, commit, push, pull request, or safety/alignment/transfer claim.
