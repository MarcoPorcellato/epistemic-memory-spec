# Track 14 and Track 15 continuation proposal

**Proposed research plan; no freeze or experiment authorised.** This document
links the [portfolio proposal](../docs/proposals/track14-15-research-portfolio.md)
to the [core design decisions](core-design-decisions-proposal.md), [comparison](core-design-comparison-proposal.md),
and [verification cases](core-verification-cases-proposal.md).

## Candidate versus procedure

For any future Track 14 study, the candidate strategic operator must predict an
observable difference beyond a prompt, heuristic, retrieved example, tool
invocation, skill, procedure, policy, or model capability. State the proposed
operator and prediction before observing outcomes.

**Collapse condition:** if an existing category predicts the same outcomes and
no independent prediction remains, classify the treatment under that category
and do not claim a distinct operator.

## Conditional multimodal question

Track 15 remains separately named and active under [Decision 0005](../docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md).
Its research question asks whether a modality-specific representation has a
separately testable contribution after information, renderer, exposure, and
model capability are controlled. It may be studied alongside Track 14 only
after an outcome-free plan defines a distinct prediction and governance need.

**Collapse condition:** if the proposed treatment is fully explained as a
representation, prompt, procedure, tool, or candidate operator with no
incremental prediction or governance need, report that result and propose a
maintainer decision on portfolio placement. Do not silently cancel, defer, or
contain Track 15.

## Controls required before any preregistration

| Concern | Evidence required before protocol freeze | Falsifier |
| --- | --- | --- |
| Information fidelity | Independent comparison showing each arm preserves the same task facts, relations, quantities, contradictions, and temporal content. | Any unmeasured semantic loss or gain makes the comparison uninterpretable. |
| Renderer and modality | Frozen renderer description, output constraints, and matched presentation budgets. | A difference caused by renderer behavior cannot be attributed to a strategic operator or modality alone. |
| Capability | Documented model, tool, and modality capability controls. | An arm receives capability unavailable to its comparator. |
| Exposure and parity | Matched examples, retrieval, feedback, time, tokens, compute, and human effort, with leakage checks. | Unmatched exposure or leakage blocks transfer, retention, or acceleration claims. |
| Metrics and baselines | Declared estimand, metrics, matched baseline, uncertainty, stopping rule, and regressions before outcomes. | Post-hoc metric or baseline selection blocks performance claims. |
| Access and independence | Reviewer access, conflicts, author involvement, and material custody declared; independent review arranged where claimed. | Same-team model review is not independent replication. |

## Gate sequence

1. Complete prior-art and terminology comparison, including collapse tests.
2. Prepare outcome-free preregistration with exact materials, controls, metrics,
   budgets, exclusions, and failure states.
3. Seek separate authority for synthetic materials and bounded evaluation.
4. Preserve null, negative, failed, and non-interpretable outcomes.
5. Obtain independent review or replication before claims requiring it.
6. Ask for a later maintainer continuation, containment, retirement, or
   extraction decision.

Each stage requires its applicable authority. This proposal creates no task,
held-out set, asset, model run, evaluation, freeze, schema, or implementation.
