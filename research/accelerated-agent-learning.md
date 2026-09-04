# Accelerated Agent Learning through Explicit Strategic Learning

## Status and reading contract

**Incubated non-normative research track.**

This document frames questions, boundaries, and evidence requirements. It does
not describe a working learning system, prescribe an architecture, establish a
standard, or claim that an agent can learn faster, transfer better, or remain
aligned. It is governed by
[Decision 0004](../docs/decisions/0004-incubating-strategic-agent-learning.md).

## Research motivation

An agent may retain source-bound evidence without becoming better at approaching
unfamiliar problems. Conversely, a system may appear to improve at a task while
leaving no inspectable account of what was tried, what changed, or which
evidence supports the result. These are separate problems.

This track asks whether a problem-solving transformation can be made explicit
enough to test its incremental contribution under reproducible conditions. It
does not assume that every useful strategy is explicit, discrete, stable, or
transferable.

## Three layers of learning

| Layer | Question | Example evidence | Boundary |
| --- | --- | --- | --- |
| Parametric | What changes inside a trained model? | Training data, checkpoints, and weight-update evaluations. | Outside this repository's current scope. |
| Epistemic | What is recorded, with which provenance, and how is it assessed? | Source-bound observations, experimental outcomes, policy revisions. | Does not choose or apply strategies. |
| Strategic | How does an agent improve its problem-solving approach? | Preregistered comparisons of candidate approaches against controls. | Does not imply weight updates or a production controller. |

The proposed bridge is deliberately one-way: an experiment can emit evidence;
a named policy can assess that evidence; later research can use a bounded
assessment when selecting a candidate. The evidence record never silently
becomes the selection policy.

## Candidate strategic operators

A **candidate strategic operator** is a reusable transformation of a problem
representation or problem-solving process whose incremental contribution can
be tested on preregistered held-out tasks against declared baselines and
controls.

The phrase marks a hypothesis, not an object model. It prevents an experiment
from treating a prompt, example, tool call, retrieved solution, skill, policy,
reasoning trace, or latent direction as proof that an operator exists. Those
may be experimental materials, confounds, comparison points, or possible
implementations.

Four research activities remain distinct:

1. **Discovery:** generate or identify candidate transformations.
2. **Selection:** choose a candidate for a declared context under a stated
   policy and budget.
3. **Evaluation:** measure incremental outcomes against preregistered
   baselines and controls.
4. **Revision:** update applicability hypotheses from provenance-bound
   evidence without rewriting the observed record.

Conflating these activities allows selection bias to masquerade as learning.

## What counts as acceleration

“Accelerated” is not a synonym for “better.” Every experiment must choose one
or more primary dimensions and report relevant regressions at the same declared
budget:

| Candidate dimension | Example unit | Required comparison |
| --- | --- | --- |
| Data efficiency | Examples or interactions needed | Matched baseline task family. |
| Feedback efficiency | Human feedback events needed | Same feedback policy and task budget. |
| Token efficiency | Input and output tokens | Same model, context, and outcome target. |
| Compute efficiency | Wall time, FLOPs, or energy proxy | Declared hardware and execution limits. |
| Adaptation speed | Time or trials to threshold | Frozen threshold and starting state. |
| Held-out transfer | Outcome on withheld families | Grouped family split and source-blind primary arm. |
| Retention | Loss on prior tasks | Explicit pre/post task protocol. |
| Outcome quality | Task-specific scored outcome | Equal budget and blind or independent evaluation where feasible. |

A result can support only the exact measured proposition. Token savings do not
prove transfer; an outcome gain does not prove causal use; a speed gain that
reduces safety, retention, or outcome quality must report that cost.

Continual-learning research treats stability, plasticity, generalisability, and
resource efficiency as distinct tensions rather than a single “learning”
number. See Wang et al., [*A Comprehensive Survey of Continual Learning*](https://arxiv.org/abs/2302.00487),
and Parisi et al., [*Continual Lifelong Learning with Neural Networks*](https://arxiv.org/abs/1802.07569).

## Evidence record versus assessment

An experiment should record bounded facts such as:

```text
experiment: E17
candidate strategy: X
context: C
task family: T
baseline: B
outcome delta: Δ
provenance: P
```

It must not directly assert `strategy X works`. A future policy may assess the
record as “X appears supported under conditions C,” provided that its identity,
revision, inputs, failure behaviour, and limits are declared. This preserves:

> Evidence is not assessment, and assessment is not truth.

The resulting research loop is:

```text
problem
candidate-strategy selection
application
outcome
evidence
epistemic assessment
strategy applicability revision
future selection
```

This could support a form of external, long-lived strategy learning without
altering model weights. That is a hypothesis about an evaluation architecture,
not evidence that the system has achieved lifelong learning.

## Candidate sources of hypotheses

### Modern research families

The initial literature review must compare the track with existing research on
continual and lifelong learning, transfer, active learning, planning,
meta-learning, programme synthesis, tool use, deliberation, and evaluation.
No terminology should be presented as new until this comparison is complete.

### TRIZ and OTSM

TRIZ and OTSM may provide candidate problem representations, contradiction
forms, or transformation hypotheses. They are not a privileged operator set or
a substitute for controlled evaluation. Any operator-level claim must meet the
same construct, surface-control, held-out-transfer, causal, capability, and
replication requirements used by the
[Latent-TRIZ falsification contract](https://github.com/MarcoPorcellato/Latent-TRIZ/blob/a2d2b5647524b81a746b2d375bf542e7ae190a0a/docs/HYPOTHESES_AND_FALSIFICATION.md).

OTSM sources are prior-art material for review, including
[Khomenko's OTSM-TRIZ collection](https://otsm-triz.org/en/book). They are not
an implementation dependency or evidence of cross-domain transfer.

### Trivium and Quadrivium

The Trivium and Quadrivium are candidate functional decompositions to compare
against contemporary architectures, not historical claims about artificial
intelligence. The comparison question is practical: does a decomposition such
as representation, reasoning, situated action, quantity, structure, temporal
pattern, and dynamic world model improve experimental diagnosis, modularity, or
transfer measurement?

If it does not improve an explicit comparison, discard it. If it does, report
the limited operational benefit rather than a cultural or historical verdict.

### Human learning traditions

Suggestopedia is a historical learning tradition associated with Georgi Lozanov
and the Institute of Suggestology in Sofia, Bulgaria. Its documentation may
motivate questions about presentation, feedback, context, and learner state;
it does not provide a validated method for artificial agents. See the
[archived overview](https://files.eric.ed.gov/fulltext/ED119063.pdf).

No human-learning result transfers to an agent setting without a matched,
controlled protocol.

## Experimental programme

### Phase 0 — prior art and terminology

Produce a terminology matrix: candidate strategic operator, heuristic, skill,
policy, procedure, prompt, retrieved example, tool invocation, latent feature,
reasoning trace, and model update. For each, identify closest prior art,
proposed difference, and a counterexample that would collapse the distinction.

### Phase 1 — preregistered experiment design

Define a task family, source-exposure policy, candidates, budget, primary and
secondary metrics, baselines, controls, stopping rules, and outcome labels
(`positive`, `null`, `failed`, `non_interpretable`). Freeze these before access
to evaluation outcomes.

### Phase 2 — synthetic task suite

Publish only safe, reproducible tasks. When transfer is a target metric, use
held-out grouped task families and keep source-exposed and source-blind arms
separate.

### Phase 3 — bounded evaluation

Measure discovery, selection, evaluation, and revision separately. Preserve
negative and inconclusive outcomes. Do not rescue a failed primary result with
a post-hoc metric, a different operator, or a source-exposed example.

### Phase 4 — independent review

Require replication or independent review of exact tasks, controls, and
analysis before promotion. A decodable representation or plausible explanation
does not establish causal use.

### Phase 5 — extraction decision

Propose a separate Explicit Strategic Learning project only if terminology,
protocol, baselines and controls, and architectural separation are each mature
enough to carry their own governance.

## Failure modes to seek deliberately

- surface, lexical, template, source, or domain shortcuts;
- selection on the test set or post-hoc task changes;
- treating a reasoning trace as causal explanation;
- reporting one efficiency gain while concealing quality, safety, or retention
  regressions;
- pooling source-exposed competence with source-blind transfer;
- replacing an outcome record with a conclusion about a strategy;
- declaring “lifelong learning” from a single short-horizon benchmark; and
- moving a research construct into a runtime or schema before the protocol is
  coherent.

## Exit criteria and non-goals

This research remains in incubation until it has stable terminology, a
reproducible experimental protocol, at least one coherent baseline/control
family, and a concrete architectural reason to separate it from epistemic
memory research.

Until then it does not create:

- a `CognitiveOperator` schema or runtime entity;
- a Plumber feature, Shadow acceleration policy, Logseq integration, or write
  path;
- a model-training, reinforcement-learning, or autonomous-agent framework;
- a normative standard, benchmark authority, certification, or compatibility
  claim; or
- a claim of alignment, safety, or universal agent improvement.
