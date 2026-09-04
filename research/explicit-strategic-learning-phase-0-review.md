# Explicit Strategic Learning: Phase 0 prior-art and terminology review

## Status and reading contract

**Incubated, non-normative research review.** This document records source
facts, constrained synthesis, hypotheses, and unknowns for Track 14. It does
not define a schema, runtime entity, implementation, benchmark, policy,
standard, interoperability commitment, or performance result. It does not
authorise any change to Matryca Plumber.

The governing boundary is [Decision 0004](../docs/decisions/0004-incubating-strategic-agent-learning.md), at repository commit
`393ca4272aedfa7f0ddec840f39683374d262989`. Track 14 is stated in
[OPEN_RESEARCH.md](../OPEN_RESEARCH.md); the existing research framing is
[Accelerated Agent Learning through Explicit Strategic Learning](accelerated-agent-learning.md).
Contributions must distinguish observed evidence from interpretation, preserve
reproducibility, and remain non-normative under [CONTRIBUTING.md](../CONTRIBUTING.md).
The maintainer-led, non-standards boundary is recorded in
[GOVERNANCE.md](../GOVERNANCE.md); repository maturity and non-normative status
are recorded in [STATUS.md](../STATUS.md).

`candidate strategic operator` remains a provisional research construct only:
a reusable transformation of a problem representation or problem-solving
process whose incremental contribution can be tested on preregistered held-out
tasks against declared baselines and controls. It is not a data entity, schema
field, runtime abstraction, or claim about a model's internal representation.

Trivium, Quadrivium, Suggestopedia, TRIZ, and OTSM are comparison or hypothesis
lenses only, never architecture or proof. No human-learning result transfers to
agents without matched controlled evidence.

## Evidence taxonomy

| Label | Meaning in this review | What it cannot establish |
| --- | --- | --- |
| Source fact | A bounded statement attributable to a cited source whose type is recorded, including a primary paper, proceedings page, survey, textbook, technical report, publisher page, or maintained primary archive. | A result beyond that source's task, setup, and evaluation. |
| Synthesis | A comparison or proposed terminology boundary drawn from source facts and Decision 0004. | Novelty, causality, transfer, safety, alignment, or performance. |
| Hypothesis | A falsifiable proposition for a later preregistered experiment. | An implemented mechanism or a positive result. |
| Unknown | A question not resolved by the reviewed sources or repository evidence. | Permission to infer a favourable answer. |

## Terminology matrix

The matrix distinguishes experimental materials and mechanisms from the
provisional construct. The listed evidence is a minimum for using a distinction
in a later protocol, not evidence that any item exists or helps.

| Term | Operational distinction | Closest prior art | Evidence needed before a research claim | Falsification or collapse condition |
| --- | --- | --- | --- | --- |
| **candidate strategic operator** | A reusable, explicitly stated transformation of a problem representation or problem-solving process, evaluated for incremental effect. It is a research construct, not an artefact type. | Heuristic search; program abstraction; planning; meta-learning. | Preregistered specification, matched baseline and control, held-out task family, source-exposure record, outcome record, and declared failure state. | Remove term if every candidate is fully described by an adjacent term and abstraction makes no separately testable prediction. |
| **heuristic** | A search or decision guide that may be useful without guaranteeing a correct result. A candidate operator may be a heuristic but need not be one. | Newell and Simon's heuristic problem-solving account. | Operational rule, task context, budget, comparison with a non-heuristic or alternate heuristic control. | Collapse to heuristic if construct is only an unguaranteed rule of thumb and no broader transformation is testable. |
| **skill** | An observed capability or competence to perform a task; it is an outcome-level property, not necessarily a mechanism. | Learned skills in reinforcement learning and program/library learning. | Task definition, success measure, retention and generalisation conditions where claimed. | Collapse distinction if no separable transformation is manipulated and claim is only that an agent performs task X. |
| **procedure** | A declared sequence of steps, possibly deterministic or conditional. It can implement a candidate operator but does not establish incremental value by being written down. | Algorithms, workflows, and program synthesis. | Exact steps, inputs, execution conditions, and ablation against an alternate procedure. | Collapse to procedure if candidate is exactly one sequence and no independently varied transformation remains. |
| **policy** | A rule mapping context, objectives, and constraints to candidate or action selection. It belongs to selection, not to the selected transformation. | Reinforcement-learning policies; active-learning query strategies. | Policy identity/version, inputs, objectives, constraints, selection logs, and separate operator ablation. | Collapse distinction if policy and candidate always co-vary or no selection decision is present. |
| **prompt** | Textual conditioning supplied to a model. It can instantiate an experimental treatment but does not prove a reusable transformation. | Few-shot and chain-of-thought prompting. | Exact prompt family, context/token budget, model configuration, prompt-only and matched-context controls. | Collapse to prompt engineering if a fixed wording is sole intervention and no prompt-independent transformation is specified. |
| **retrieved example** | An external item retrieved into context. It is source exposure and may be a confound, not proof of learning or transfer. | Retrieval-augmented generation; in-context exemplars. | Retrieval corpus/version, query and ranker, access logs, provenance, source-blind and retrieval-parity controls. | Collapse claim if effect disappears with retrieval parity or source-blind evaluation, or if candidate merely retrieves an exact solution. |
| **tool invocation** | A concrete environment action with program, arguments, result, and execution conditions. It may implement a transformation but is not automatically one. | Tool-using language models and planning agents. | Tool contract, availability, arguments, results, failures, tool-budget parity, and alternate-tool or no-tool control. | Collapse to tool access if fixed API availability/call alone explains result and representation/process transformation is not independently varied. |
| **reasoning trace** | A generated or recorded intermediate sequence. It may be an experimental observable or executable plan, but is not presumed to be a causal explanation. | Chain-of-thought and ReAct traces; faithfulness evaluation. | Trace retention policy, intervention or ablation, causal test, and evaluator blinded where feasible. | Reject causal interpretation if trace is only plausible narration or trace intervention shows no relevant effect. |
| **latent feature or direction** | An inferred activation-space pattern or concept activation vector. It can be an internal proxy but is not an explicit operator merely because it is decodable, sensitive, or correlated. | Concept activation vectors and interpretability work. | Reproducible extraction, intervention, behavioural effect, and external operator specification. | Collapse to latent correlation or sensitivity if no external reusable specification or causal manipulation exists. |
| **model update** | A change to weights, optimiser state, or another parametric learning state. It is distinct from an external strategic representation. | Gradient-based meta-learning and continual learning. | Exact starting state, update rule/data/budget, checkpoint provenance, and a no-update or matched-update control. | Collapse into parametric learning if only measured difference is a model update and no explicit transformation is independently specified. |

### Evidence and policy-derived assessment remain separate

An experiment records bounded evidence: candidate, context, task family,
baseline, treatment, measured outcome, uncertainty, and provenance. A named,
versioned policy may later derive a bounded assessment such as “appears
supported under declared conditions.” It must declare identity, inputs,
revision, and failure behaviour. Evidence is not assessment, and assessment is
not truth. Neither record is a strategy-selection policy by default.

## Prior-art map

| Research family | Source facts | Phase 0 synthesis and limit |
| --- | --- | --- |
| Continual and lifelong learning | Kirkpatrick et al. evaluate sequential task learning and catastrophic forgetting. Parisi et al. review continual/lifelong learning dimensions and methods. | Retention, plasticity, and resource use are distinct measurements. A short evaluation cannot support a lifelong-learning claim. |
| Transfer and generalisation | Pan and Yang survey transfer-learning settings. WILDS reports distribution shifts and evaluates methods under defined shifts. | “Transfer” requires a declared held-out grouped family and exposure boundary. IID or leaked splits support only their stated evaluation. |
| Meta-learning | Finn, Abbeel, and Levine train parameters so a small number of gradient steps can adapt to a new task. | Meta-trained parameter adaptation is a direct adjacent explanation. It does not show an external candidate operator exists. |
| Planning and tool use | ReAct interleaves generated reasoning traces and actions. Toolformer trains decisions about API calls, timing, arguments, and result incorporation. | Control tool availability, outputs, and budgets before attributing an effect to a transformation. Planning trace and tool call are distinct artefacts. |
| Active learning | Cohn, Atlas, and Ladner evaluate an active-learning approach for generalisation under their specified setup; Settles surveys active-learning query settings and methods. | Separate query/feedback selection policy from candidate transformation. Equalise feedback and interaction budgets before calling a result accelerated. |
| Programme synthesis | FlashFill synthesises string transformations from input-output examples. DreamCoder grows symbolic abstractions and searches programs. | A candidate expressed as executable program/library item needs program-synthesis or library-learning baselines; it is not new by label alone. |
| Agent evaluation | AgentBench evaluates language-model agents across several interactive environments. | One benchmark score cannot establish general agent improvement. Task, evaluator, tool, model, and budget need explicit binding. |
| Prompts, retrieved examples, and traces | Brown et al. evaluate in-context few-shot conditioning. Lewis et al. combine retrieval with generation. Wei et al. evaluate chain-of-thought prompting; Turpin et al. give evidence that explanations can omit causally influential factors. | Treat each as material, mechanism candidate, or confound under test. Do not treat a trace as proof of internal causal reasoning. |
| Latent features or directions | Kim et al. introduce concept activation vectors and a directional-derivative sensitivity test. | Sensitivity or correlation alone does not establish an explicit reusable transformation or causal use. |
| TRIZ and OTSM | The OTSM-TRIZ archive is historical prior-art material for contradiction and representation hypotheses. | TRIZ and OTSM are candidate hypothesis sources only. They are neither architecture nor proof and receive no privileged operator status. |

## Acceleration discipline

“Accelerated” has no default scalar meaning. A later experiment must
preregister one or more primary dimensions, unit, starting state, threshold
when relevant, and matched baseline at the same declared budget:

- examples or interactions needed;
- human-feedback events needed;
- input and output tokens;
- compute, wall time, FLOPs, or declared energy proxy;
- trials or time to an adaptation threshold;
- held-out grouped-family outcome;
- retention loss on earlier tasks; or
- independently scored task outcome quality.

The report must also disclose relevant regressions. A token reduction does not
establish transfer; a task-outcome gain does not establish causal use; a faster
run with a lower-quality, less-retentive, or otherwise degraded outcome is not
an unqualified acceleration result.

## Phase 0 hypotheses and unknowns

**Hypothesis:** An explicitly stated transformation can sometimes be evaluated
as a separable treatment rather than inferred from a prompt, retrieved example,
tool invocation, trace, latent proxy, or model update.

**Falsifier:** On preregistered tasks, no candidate remains separable after
matched controls for these adjacent artefacts, or no candidate improves a
declared primary metric without an unacceptable preregistered regression.

**Unknowns:** Whether any candidate will survive these controls; which task
families support a legitimate grouped held-out transfer test; which metrics are
practicable and meaningful; and whether an eventual experimental programme
would warrant extraction from this repository. No reviewed source answers
these questions for Track 14.

## Bibliography and source limits

| Source | Type | Use and limit |
| --- | --- | --- |
| [Kirkpatrick et al., 2017, *Overcoming Catastrophic Forgetting in Neural Networks*](https://doi.org/10.1073/pnas.1611835114) | Peer-reviewed primary paper | Sequential-task forgetting context; not evidence for Track 14. |
| [Parisi et al., 2019, *Continual Lifelong Learning with Neural Networks*](https://arxiv.org/abs/1802.07569) | Survey preprint | Terminology/orientation; not a controlled evaluation of this construct. |
| [Pan and Yang, 2010, *A Survey on Transfer Learning*](https://doi.org/10.1109/TKDE.2009.191) | Peer-reviewed survey | Transfer taxonomy; not evidence of transfer here. |
| [Koh et al., 2021, *WILDS*](https://proceedings.mlr.press/v139/koh21a.html) | ICML proceedings paper | Distribution-shift evaluation example; not a Track 14 benchmark. |
| [Finn, Abbeel, Levine, 2017, *MAML*](https://proceedings.mlr.press/v70/finn17a.html) | ICML proceedings paper | Parametric fast-adaptation prior art; not evidence of explicit external strategy. |
| [Cohn, Atlas, Ladner, 1994, *Improving Generalization with Active Learning*](https://doi.org/10.1007/BF00993277) | Peer-reviewed *Machine Learning* paper | Active-learning method and evaluation in its stated setup; not evidence of agent acceleration. |
| [Settles, 2009, *Active Learning Literature Survey*](https://burrsettles.com/pub/settles.activelearning_20090109.pdf) | University technical-report survey | Query-selection terminology and orientation; not primary causal evidence for Track 14. |
| [Yao et al., 2023, *ReAct*](https://arxiv.org/abs/2210.03629) | Conference paper preprint | Trace/action interleaving prior art; no trace-faithfulness presumption. |
| [Schick et al., 2023, *Toolformer*](https://arxiv.org/abs/2302.04761) | Research preprint | Tool-use prior art; not evidence for any particular tool or agent. |
| [Gulwani, 2011, *FlashFill*](https://doi.org/10.1145/1926385.1926423) | POPL proceedings paper | Inductive synthesis baseline; limited to its specified domain and protocol. |
| [Ellis et al., 2021, *DreamCoder*](https://arxiv.org/abs/2006.08381) | ICLR paper preprint | Library-learning/program-abstraction prior art; not a claim of general transfer. |
| [Liu et al., 2024, *AgentBench*](https://proceedings.iclr.cc/paper_files/paper/2024/hash/e9df36b21ff4ee211a8b71ee8b7e9f57-Abstract-Conference.html) | ICLR proceedings paper | Multi-environment evaluation example; no universal score interpretation. |
| [Brown et al., 2020, *Language Models are Few-Shot Learners*](https://proceedings.neurips.cc/paper_files/paper/2020/hash/1457c0d6bfcb4967418bfb8ac142f64a-Abstract.html) | NeurIPS proceedings paper | Prompt/in-context conditioning prior art; not a mechanism proof. |
| [Lewis et al., 2020, *Retrieval-Augmented Generation*](https://proceedings.neurips.cc/paper/2020/hash/6b493230205f780e1bc26945df7481e5-Abstract.html) | NeurIPS proceedings paper | Retrieved-context prior art; requires retrieval-exposure controls here. |
| [Wei et al., 2022, *Chain-of-Thought Prompting*](https://proceedings.neurips.cc/paper_files/paper/2022/hash/9d5609613524ecf4f15af0f7b31abca4-Paper-Conference.html) | NeurIPS proceedings paper | Prompted trace prior art; does not prove trace causality. |
| [Turpin et al., 2023, *Language Models Don't Always Say What They Think*](https://arxiv.org/abs/2305.04388) | Research preprint | Reasoning-trace faithfulness caveat; bounded to its studied setups. |
| [Kim et al., 2018, *Interpretability Beyond Feature Attribution: Quantitative Testing with Concept Activation Vectors (TCAV)*](https://proceedings.mlr.press/v80/kim18d.html) | ICML proceedings paper | Concept activation-vector terminology and sensitivity testing; neither establishes an operator nor causal use. |
| [Newell and Simon, 1970, *Human Problem Solving*](https://doi.org/10.1037/h0030806) | Peer-reviewed theoretical paper | Heuristic-search antecedent; not an agent-learning architecture. |
| [Sutton and Barto, 2018, *Reinforcement Learning: An Introduction*](https://incompleteideas.net/book/the-book-2nd.html) | Author-maintained academic textbook | Policy terminology; not evidence for a Track 14 policy. |
| [Khomenko, OTSM-TRIZ collection](https://otsm-triz.org/en/book) | Primary historical archive | Hypothesis source only; not controlled evidence or implementation dependency. |
