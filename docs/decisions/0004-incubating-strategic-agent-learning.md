# Decision 0004: Incubating strategic agent learning without expanding the epistemic core

## Status

**Proposed research design.**

This decision records an incubation boundary. It adds no schema, runtime,
implementation, protocol, conformance programme, interoperability claim, or
claim that any system learns faster or better.

## Context

Epistemic memory asks a narrow question: how can a system preserve
provenance-bound evidence and policy-scoped assessments without replacing the
authority of a human or host-owned source? It does not answer how an agent
should discover, select, test, or revise approaches to solving new problems.

Those questions deserve research, but they must not be smuggled into the
epistemic core as an unexplained operator record, an implicit recommender, or
an automatic learning engine. Existing work on continual learning, transfer,
active learning, planning, meta-learning, programme synthesis, tool use, and
heuristics already covers substantial parts of this landscape. Historical
frameworks such as the Trivium, Quadrivium, TRIZ, and OTSM may offer questions
or candidate decompositions; they are not evidence of an artificial-learning
architecture.

The research question is deliberately limited:

> Can explicitly represented and experimentally evaluated problem-solving
> transformations improve one or more declared learning-efficiency, reliability,
> transfer, or outcome metrics against declared baselines and controls?

The phrase **Accelerated Agent Learning** is a research label for that
question. It is not a performance claim.

## Decision

Incubate **Explicit Strategic Learning** as a separate, non-normative research
track. Keep the epistemic core unchanged.

The track studies three distinct layers:

| Layer | Research question | Not implied |
| --- | --- | --- |
| Parametric learning | What changes inside a trained model? | This repository trains or modifies model weights. |
| Epistemic learning | What evidence, claim, assessment, and uncertainty can be recorded and replayed? | Evidence becomes a learning policy or truth. |
| Strategic learning | How can an agent improve its approach to unfamiliar problems under declared controls? | An operator exists, transfers, or causes improvement. |

The relationship is evidence-bounded:

```text
problem
candidate-strategy selection
application
outcome
provenance-bound evidence
policy-derived assessment
applicability revision
future selection
```

This is a research loop, not a deployed control loop. A result may show that a
declared candidate helped or failed under bounded conditions. It does not make
the candidate true, generally useful, safe, or eligible for autonomous use.

## Candidate strategic operator boundary

A **candidate strategic operator** is a reusable transformation of a problem
representation or problem-solving process whose incremental contribution can
be tested on preregistered held-out tasks against declared baselines and
controls.

This is a provisional, falsifiable research construct. It is not a data
entity, a schema field, a runtime abstraction, or a claim about an internal
model representation.

It is not, by itself:

- a prompt, retrieved example, memorised solution, reasoning trace, or latent
  direction;
- a heuristic, procedure, skill, policy, tool invocation, or tool result; or
- proof of transfer, causal use, novelty, safety, or human-equivalent thought.

An experiment may later test whether one or more of those artefacts implements,
approximates, or confounds a candidate strategic operator. It must not assume
the answer in advance.

## What “accelerated” means

Acceleration has no default scalar meaning. Each experiment must preregister
one or more independent target dimensions and compare them with an appropriate
baseline at the same declared budget:

- fewer examples or interactions;
- less human feedback;
- fewer tokens;
- less compute;
- shorter adaptation time;
- stronger held-out transfer;
- lower catastrophic forgetting; or
- higher outcome quality at equal budget.

The testable thesis is narrow: Explicit Strategic Learning is useful only when
it improves one or more declared learning-efficiency, reliability, transfer,
retention, or outcome-quality metrics against appropriate baselines, controls,
and failure criteria. A gain on one axis does not compensate for an unreported
regression on another.

## Separation between outcome and assessment

The epistemic layer must record bounded experimental evidence, not a direct
statement that a strategy works. A future experimental record might identify:

```text
experiment: E17
candidate strategy: X
context: C
task family: T
baseline: B
outcome delta: Δ
provenance: P
```

Only a named, versioned policy could later derive an assessment such as
“X appears supported under conditions C.” The assessment remains distinct from
the observed outcome and from truth.

> Epistemic Memory does not become the learning engine. It records
> provenance-bound evidence about whether a declared strategy helped or failed.

This preserves the existing distinction: **evidence is not assessment, and
assessment is not truth.**

## Research boundary and responsibilities

| Concern | Research role | Explicit boundary |
| --- | --- | --- |
| Epistemic Memory Spec | Vocabulary and future evidence/assessment discipline. | No learning engine, operator schema, or deployment policy. |
| Matryca Plumber | A possible future consumer of a separately approved evidence contract. | No current runtime, Shadow, Logseq, or source-authority change follows. |
| Latent-TRIZ | Controlled empirical work on operator-level constructs and falsification. | No result is imported as a general learning claim without its own evidence. |
| Future independent project | Potential home for coherent experimental protocols and implementations. | It does not exist yet and is not authorised by this decision. |

Latent-TRIZ's existing hypotheses remain the relevant discipline for any
operator-level claim: separate source-exposed competence from held-out
transfer, retain surface and capability controls, distinguish exploratory
proxies from construct-valid results, and require causal and replication gates
before promotion. See its
[falsification contract](https://github.com/MarcoPorcellato/Latent-TRIZ/blob/a2d2b5647524b81a746b2d375bf542e7ae190a0a/docs/HYPOTHESES_AND_FALSIFICATION.md).

## Candidate lenses, not architecture

The Trivium and Quadrivium are treated only as a candidate functional
decomposition to compare against modern cognitive and agent architectures:

| Historical label | Candidate functional question | Must be compared with |
| --- | --- | --- |
| Grammar | How are representations and concepts formed or transformed? | Representation learning and knowledge-representation approaches. |
| Logic | How are inference, contradiction, and revision bounded? | Reasoning, planning, verification, and belief-revision approaches. |
| Rhetoric | How is communication or action situated in context? | Interaction, tool-use, and policy-selection approaches. |
| Arithmetic | How are quantity and trade-offs represented? | Cost, utility, and resource-accounting approaches. |
| Geometry | How is structure represented and transformed? | Graph, spatial, relational, and compositional approaches. |
| Music | How are temporal or proportional patterns represented? | Sequence, control, and temporal-model approaches. |
| Astronomy | How is a dynamic world model represented and tested? | State estimation, simulation, and world-model approaches. |

No historical framework is asserted to anticipate artificial general
intelligence. The only research question is whether a decomposition improves
diagnosis, modularity, experimental design, or transfer measurement relative to
modern alternatives.

TRIZ and OTSM are likewise candidate sources of problem-representation and
contradiction hypotheses, not privileged universal operator libraries. The
[OTSM-TRIZ archive](https://otsm-triz.org/en/book) is an antecedent for source
review, not an implementation dependency. Suggestopedia and related human
learning traditions are historical inspirations only; no claim about human
learning efficacy transfers to agents without controlled evidence. Georgi
Lozanov's work is associated with the Institute of Suggestology in Sofia,
Bulgaria; it must not be inaccurately recast as a Russian programme.

## Research sequence and gates

1. **Terminology and prior-art review.** Distinguish candidate strategic
   operators from adjacent terms and identify modern baselines.
2. **Experimental protocol.** Preregister task families, budgets, metrics,
   baselines, controls, and null/non-interpretable outcomes.
3. **Synthetic task suite.** Publish safe, reproducible tasks with held-out
   families where transfer is a declared metric.
4. **Bounded trials.** Separate discovery, selection, evaluation, and revision;
   preserve raw outcomes and provenance.
5. **Independent review.** Test robustness, confounds, replication, and
   negative results before any promotion.
6. **Extraction decision.** Consider an independent research repository only
   when the exit criteria below are met.

No experiment may promote a candidate based on post-hoc task selection,
undeclared source exposure, a lone positive metric, or an unreproducible
reasoning trace. A failed or inconclusive result remains evidence; it must not
be hidden by later successful runs.

## Exit criteria

An autonomous Explicit Strategic Learning repository may be proposed only when
all of these conditions exist:

1. terminology stable enough to define a bounded research contract;
2. a reproducible experimental protocol with declared failure states;
3. at least one coherent family of baselines and controls; and
4. an architectural reason why the work no longer belongs to epistemic-memory
   research alone.

Until then, this remains an incubated research track. Opening a repository,
creating a schema, or implementing runtime behaviour requires a separate
decision and explicit review.

## Consequences

This decision protects the epistemic core from premature expansion while
preserving a disciplined path to investigate strategic learning. It makes room
for long-lived, externally represented strategy evidence without confusing
that record with model-weight updates, truth, or a production learning system.

The next approved work is literature and terminology review only. It must not
create schemas, runtimes, Plumber changes, normative requirements, or external
compatibility claims.
