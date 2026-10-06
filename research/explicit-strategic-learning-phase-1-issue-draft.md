# Issue record — Track 14 Phase 1: review bounded CSP preregistration proposal

**Status:** Published as [issue #15](https://github.com/MarcoPorcellato/epistemic-memory-spec/issues/15).
This file preserves the proposed issue text; publication does not freeze the
protocol or authorise task generation, model execution, or evaluation.

## Review request

Review the proposed preregistration for one bounded synthetic finite-domain
constraint-satisfaction family. The candidate treatment is explicit constraint
normalisation plus contradiction inventory. The proposed primary comparison is
full treatment against a matched generic-decomposition control on source-blind,
held-out cactus-graph structural groups.

The review asks whether the candidate remains a falsifiable representation
transformation after controls for procedure, prompt wording, added deliberation,
trace, tool, retrieval, model-update, and structural-leakage confounds. It does
not request task generation, benchmark creation, model execution, or a claim of
usefulness.

## Acceptance and freeze-blocker checklist

- [ ] Candidate can be stated independently of exact prompt wording and ordered
      procedure by an independent reviewer; otherwise stop and classify it as
      procedure-level.
- [ ] If that reviewer specifies a representation-distinct but procedure-
      equivalent workflow, conditional `P` is added as a freeze-blocker
      diagnostic. It raises minimum calls from `n_total × 5` to `n_total × 6`
      and cannot rescue a failed `T-C` primary comparison.
- [ ] Development single-cycle and held-out cactus groups are defined by frozen
      latent generator parameters. Leakage audit has zero exact instance,
      solution, certificate, or rendered-string overlap and discloses remaining
      motif, path, contradiction, and template overlap.
- [ ] `D`, `C`, `N`, `I`, and `T` arms match task, final output, model,
      context, tool, retrieval, feedback, token, time, and scoring conditions.
- [ ] All arms have identical final SAT/UNSAT certificate requirements and
      guidance; compared arms have frozen intermediate-slot and planned
      token/time parity, with actual burden retained. Otherwise `T-C` is only
      treatment-bundle evidence or is `non_interpretable`.
- [ ] Prompt-family, trace, external-artifact, and order confounds are either
      controlled or explicitly prevent stronger causal interpretation.
- [ ] Primary family-level estimand, secondary/regression disclosures,
      randomisation, blinding, analysis, labels, stopping, and provenance rules
      are reviewable before outcomes.
- [ ] `n_total` is equal-allocated across cactus subfamilies and SAT/UNSAT
      strata; finite-sample confirmation supports its conservative planning
      bound; missing and invalid blocks have frozen intention-to-treat handling.
- [ ] Positive form is frozen: lower bound of the two-sided `T-C` interval
      exceeds `delta`; `delta`, coverage, interval method, and multiplicity
      handling are explicit blockers.
- [ ] Transport-only retry means no response body, token usage, or model output;
      partial output is an outcome.
- [ ] Concrete model identifier/revision, verifier grammar, task envelope,
      prompts, budgets, `delta`, interval half-width, coverage, sample size,
      call ceiling, and cost envelope are recorded.
- [ ] Missing any item above remains a freeze blocker, not an implementation
      choice to make during evaluation.

## Non-goals

No task suite, generator, schema, runtime, benchmark, model update, tool use,
retrieval, evaluation run, Matryca Plumber change, public issue, commit, push,
or pull request. No claim of safety, alignment, novelty, general transfer,
lifelong learning, or performance.

## Exit condition

Maintainer review either approves a fully specified Phase 1 preregistration for
separate Phase 2 consideration or records a freeze blocker or construct
collapse. Neither outcome authorises task creation, evaluation, publication, or
extraction into a separate project.
