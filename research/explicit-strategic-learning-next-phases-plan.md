# Explicit Strategic Learning: next gated research phases

## Status and governing boundary

This is an inspectable, non-normative research plan for Track 14 after Phase 0.
It implements no system and grants no implementation authority. Decision 0004
remains controlling: the epistemic core is unchanged; `candidate strategic
operator` remains a research construct, not a schema or runtime entity;
experimental evidence is distinct from policy-derived assessment; and no
Matryca Plumber change follows from this plan.

No phase begins merely because an earlier phase has materials. Each transition
needs the stated verification and a separate explicit authorisation. A failed,
null, or non-interpretable result is retained as evidence and stops promotion
until a separately reviewed revision is authorised.

## Phase 1 — preregistration

**Entry conditions**

- Phase 0 terminology and prior-art review has maintainer approval or records
  that the construct is not yet separable.
- One bounded task family and one candidate strategic operator hypothesis are
  stated without claiming that either is useful.

**Required frozen contents**

- Task-family generator or source, grouping rule, eligibility conditions, and
  source-exposure policy.
- Candidate specification; discovery process; selection policy; application
  procedure; and revision rule, each kept analytically distinct.
- Starting model and environment state; tool, retrieval, prompt, example,
  feedback, token, compute, and wall-time budgets.
- Primary metric with unit; secondary metrics; regressions to report; matched
  baseline and control arms; randomisation and evaluator policy.
- Stopping rules; positive, null, failed, and non-interpretable outcome labels;
  analysis plan; and provenance-retention requirements.

**Outputs and verification**

The output is a dated, reviewable preregistration. Verification checks that it
identifies exact materials, exposure boundaries, budgets, baselines, metrics,
and failure states before evaluation outcomes are accessed.

**Failure-stop and authorisation boundary**

Stop if primary metric, matched baseline, source-exposure boundary, or failure
classification is missing. Revising a frozen element requires a new reviewed
version and explicit authorisation; it cannot be silently amended after an
outcome is seen. Separate authorisation is required for Phase 2.

## Phase 2 — synthetic task suite

**Entry conditions**

- A verified Phase 1 preregistration names safe, reproducible task requirements.
- A maintainer explicitly authorises creation of the bounded task materials.

**Required work**

- Build only synthetic or otherwise reviewable tasks matched to the registered
  task family.
- Publish grouped held-out families when transfer is a primary metric.
- Keep source-exposed and source-blind arms distinct; document generated data,
  seeds, scorers, contamination checks, and known shortcuts.
- Do not create a general benchmark or make capability claims.

**Outputs and verification**

Outputs are task specifications, generators or fixtures where separately
authorised, scoring rules, split manifests, and a known-shortcut register.
Verification checks reproducibility, split integrity, safe content, scoring
determinism where expected, and absence of evaluation-source leakage.

**Failure-stop and authorisation boundary**

Stop if task grouping cannot support the registered claim, source exposure is
uncertain, a shortcut invalidates the primary comparison, or safety/review
requirements are unmet. Repair, expansion, or evaluation requires separate
authorisation; no evaluation starts from an unverified suite.

## Phase 3 — bounded evaluation

**Entry conditions**

- Verified preregistration and verified task suite.
- Explicit authorisation binds candidate, source state, model/environment,
  exact budgets, maximum run count, output location, and stop boundary.

**Required work**

- Measure discovery, selection, application, evaluation, and revision as
  distinct activities.
- Run registered matched baseline and control arms at identical declared
  budgets, including tool, retrieval, prompt, example, feedback, token,
  compute, and time access where applicable.
- Preserve raw outcomes, provenance, negative outcomes, failures, and
  non-interpretable outcomes. Do not replace outcome records with assessments.
- Report primary metric and preregistered regressions. Label every claim with
  its exact task, source exposure, budget, and evaluator conditions.

**Outputs and verification**

Outputs are bounded outcome records, run manifests, and an analysis report
that maps each conclusion to registered metric and comparison. Verification
checks arm parity, data/split identity, outcome completeness, stopping-rule
compliance, and no post-hoc substitution of candidate, task, or primary metric.

**Failure-stop and authorisation boundary**

Stop promotion on failed, null, or non-interpretable primary outcome; preserve
the result. A new candidate, metric, task family, budget, or rerun outside the
registered envelope needs a new protocol and explicit authorisation. A positive
bounded result does not authorise deployment, safety/alignment claims, transfer
claims beyond its held-out definition, or Phase 4 automatically.

## Phase 4 — independent review or replication

**Entry conditions**

- A bounded Phase 3 record exists with complete materials permitted for review.
- Independent reviewer or replicator scope, conflict handling, and access
  limits are declared.

**Required work**

- Review exact task definitions, source-exposure rules, controls, budgets,
  analysis, negative results, and provenance.
- Reproduce or independently assess the registered comparison without changing
  its primary outcome after inspection.
- Record disagreements, confounds, non-reproduction, and limitations as first
  class results.

**Outputs and verification**

Outputs are an independent review or replication record, comparison to the
registered result, and disclosed deviations. Verification establishes reviewer
independence as declared, material completeness, and whether the primary claim
was reproduced, contradicted, or remains non-interpretable.

**Failure-stop and authorisation boundary**

Stop promotion if review finds material leakage, unmatched controls, altered
primary analysis, unavailable evidence, or non-replication. Any remediation or
additional trial needs separate authorisation. Review alone does not create a
schema, runtime, benchmark authority, or external claim.

## Phase 5 — extraction decision

**Entry conditions**

- Terminology has survived Phase 0 falsification rather than merely been named.
- A reproducible protocol, at least one coherent baseline/control family, and
  Phase 4 independent review or replication record exist.
- A concrete architectural reason shows why work no longer belongs solely in
  epistemic-memory research.

**Decision record contents**

- Evidence for and against extraction, including nulls, failures, and scope
  limits.
- Proposed governance, maintainer responsibility, provenance and assessment
  boundary, and whether a separate repository is justified.
- Explicit non-transfer of authority: no Plumber change, schema, runtime,
  implementation, public benchmark, issue publication, repository creation,
  commit, push, or pull request follows without separate authorisation.

**Verification, failure-stop, and authorisation boundary**

Verification checks all exit criteria in Decision 0004 and that each claim is
bound to direct evidence. Stop and retain Track 14 in incubation if any
criterion is absent, contested, or unsupported. Only a separate explicit
maintainer decision may authorise any extraction proposal; approval would still
not prove safety, alignment, novelty, transfer, or performance.
