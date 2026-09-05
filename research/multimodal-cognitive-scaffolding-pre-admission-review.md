# Multimodal cognitive scaffolding: pre-admission evidence review

## Status and reading contract

**Pre-admission, non-normative review.** This document supplies evidence and
terminology for a maintainer decision about whether multimodal cognitive
scaffolding is a distinct research object. It does not admit a numbered track,
define a schema, create a runtime entity, authorise an experiment or benchmark,
or change Matryca Plumber.

This review follows the [multimodal cognitive scaffolding pre-admission
programme](multimodal-cognitive-scaffolding-programme.md), [Decision
0004](../docs/decisions/0004-incubating-strategic-agent-learning.md), and the
[Track 14 Phase 0 review](explicit-strategic-learning-phase-0-review.md).
Decision 0004 keeps the epistemic core unchanged, distinguishes evidence from
policy-derived assessment and truth, and makes candidate strategic operators
provisional research constructs. Its existing Track 14 Phase 1 CSP proposal is
not a multimodal protocol and remains outside this review.

The review records source facts, synthesis, hypotheses, and unknowns. A
source fact is bounded to its cited method, model, data, and measurement. A
synthesis is a proposed boundary, not a result. A hypothesis is a later
testable proposition. An unknown is not permission to infer a favourable
answer. A future policy-derived assessment, if any, must remain distinct from
source facts and experimental outcomes.

## Research question

> Can an explicitly specified transformation of the same frozen task
> information into a visual, spatial, auditory, temporal, or affective
> representation make a separately testable contribution to a preregistered
> task metric under semantically audited controls and matched exposure budgets?

This is a candidate question, not a claim of visual, auditory, mnemonic, or
affective benefit. It must first survive comparison with prompting, retrieval,
tool use, representation learning, human-computer interaction, and Decision
0004's candidate strategic operator construct.

## Evidence taxonomy

| Label | Meaning in this review | It cannot establish |
| --- | --- | --- |
| Source fact | A bounded statement attributable to a cited source with its publication type and tested scope stated. | A result outside the source's tested setting, causal mechanism not tested there, transfer, safety, alignment, novelty, or performance in a new setting. |
| Synthesis | A terminology or experimental boundary inferred from source facts and repository governance. | Empirical efficacy or a separately valid construct. |
| Hypothesis | A falsifiable proposition for a later preregistered study. | An implemented mechanism, model update, or positive outcome. |
| Unknown | A material unanswered question. | A default affirmative answer or a reason to bypass a gate. |
| Non-interpretable outcome | A comparison invalidated by a declared confound, execution failure, or missing evidence. | A null result, a favourable result, or evidence of an operator. |

## Terminology matrix

The terms below are experimental vocabulary only. None is a data entity,
schema field, runtime abstraction, or default policy.

| Term | Operational boundary | Adjacent term | Evidence needed before a research claim | Collapse or falsification condition |
| --- | --- | --- | --- | --- |
| **canonical task information** | Frozen content from which every arm's presentation is derived. | Source record or task input. | Content digest, declared semantics, and arm-by-arm difference audit. | Misleading if an arm silently adds, removes, reorders, resolves, or hints at information. |
| **scaffold-generation procedure** | Versioned method that transforms canonical task information into a presentation or asset. | Prompt template, renderer, retrieval operation, or tool invocation. | Procedure revision, inputs, generator/renderer identity, and reproducible output record. | Collapse into the adjacent term if it fully describes the intervention and no extra prediction follows. |
| **candidate multimodal scaffold** | Research treatment consisting of an explicitly specified modality-specific representation derived from the same task information. It is not evidence, source, assessment, or entity type. | Different input format or prompt. | Independently specified transform, semantically audited control, matched budgets, and predeclared incremental comparison. | Remove term if it predicts no more than a different format or cannot vary independently of procedure and exposure budget. |
| **scaffold asset** | One concrete visual, spatial, auditory, temporal, or affective artefact presented in an arm. | Ordinary task input. | Asset digest, derivation record, modality parameters, and presentation log. | Do not distinguish it when derivation, modality, and exposure have no bearing on comparison. |
| **representation treatment** | Complete material delivered in one arm, including task ordering, context position, and exposure budget. | Prompt or tool treatment. | Frozen arm specification and a parity audit. | Collapse to prompt or tool treatment if modality is never independently varied. |
| **candidate strategic operator** | Decision 0004's reusable transformation of problem representation or problem-solving process with testable incremental contribution. Autonomous selection is not required. | Scaffold, procedure, policy, heuristic, prompt, or tool access. | Preregistered reusable specification, held-out comparison, matched controls, and declared failure state. | Classify as an adjacent term if no independently specified reusable transformation remains. A scaffold can be tested as a possible operator; neither label presumes the other. |
| **selection policy** | Rule deciding whether, when, and which scaffold or operator to use. | Fixed treatment assignment. | Policy identity, inputs, objectives, constraints, and logs, separately from treatment effect. | Omit when allocation is fixed. Never make selection a defining condition of scaffold or operator. |
| **mnemonic recoding** | Declared mapping from task items or sequences to other representational cues. | Retrieved example or answer-bearing encoding. | Mapping table, source-fidelity audit, and controls for imagery, interaction, novelty, and spatial layout. | Reclassify as retrieval or example exposure if mapping supplies answer-relevant external knowledge. |
| **affective salience** | Declared valence-, arousal-, dominance-, novelty-, or goal-relevance-related treatment property. | Formatting intensity or model emotion. | Manipulation specification, independent manipulation check, and bias/calibration/source-fidelity outcomes. | Reject affective terminology if only unmeasured formatting changes. Never equate salience with confidence, truth, reliability, authority, importance, safety, or felt emotion. |
| **audio-temporal cue** | Audio presentation whose transcript, duration, order, prosody, rhythm, melody, timbre, and other declared properties can be controlled separately. | Text presentation or duration effect. | Audio asset and transcript digests, duration and level measurements, preprocessing record, and matched-text control. | Collapse to text if transcript reproduces effect, or to duration if time is unmatched. |
| **cross-modal alignment** | Measured correspondence between representations in different modalities. | Cross-modal retrieval or joint embedding. | Defined alignment measure, model/layer identity, held-out evaluation, and model-specific scope. | Do not infer reasoning, retention, workspace entry, or causal use from alignment alone. |
| **workspace claim** | Model-specific claim that a representation is reportable, controllable, flexibly reusable, and causally involved under declared tests. | Probe, concept direction, decodable feature, or sensitivity measure. | Activation access, intervention and necessity tests, flexible-reuse test, model/revision record, and independent review. | Stop at decodability, correlation, or sensitivity if causal or flexible-reuse evidence is absent; never generalise to another architecture. |
| **learning regime** | Explicit distinction among same-turn conditioning, within-context retention, external-memory support, non-parametric persistent state, and parametric update. | Immediate task performance. | Bound starting/ending model state, retrieval state, retention interval, and artifact availability. | Do not use “learning” when benefit requires current scaffold or retrieval, or model state is unbound. |

## Primary-source map

The table provides bounded anchors, not a systematic-review claim or a novelty
claim. Preprints and official research articles remain labelled as such.

| Area and source | Publication type and tested scope | Bounded source fact | Limitation | Forbidden inference |
| --- | --- | --- | --- | --- |
| Diagrammatic scratchpads: [Hsu et al., 2023](https://proceedings.mlr.press/v239/hsu23a.html) | NeurIPS 2023 workshop proceedings, PMLR 239; diagram execution and readout around an LLM. | Visual-Scratchpad outperformed the authors' inference-only LLM comparator but underperformed one fine-tuned LLM. | Diagram generation, visual readout, optional expert iteration, and training are bundled. | No general visual-reasoning advantage, learning result, or isolated representation effect. |
| Diagram comprehension: [Hou et al., 2025](https://proceedings.mlr.press/v267/hou25c.html) | ICML 2025 proceedings; synthetic and real diagram comprehension test suite over six LVLMs. | The authors report limited relational diagram understanding and background-knowledge shortcuts in evaluated models. | A defined test suite and model set; not all diagram forms or models. | No claim that diagrams cannot help, or that every diagram result is leakage. |
| Knowledge-graph prompting and mind-map terminology: [Wen, Wang, and Sun, 2024](https://aclanthology.org/2024.acl-long.558/) | ACL 2024 long paper; knowledge-graph prompting for QA, especially medical tasks. | MindMap combines KG inputs, external/implicit knowledge, prompting, and QA; authors report results in those settings. | Retrieval, graph content, prompt, and task are combined. | No direct evidence for raster mind maps, a causal internal path, or a new construct. |
| Visual graph guidance: [Lei, Xiao, and Wei, 2026](https://arxiv.org/abs/2606.02673) | arXiv preprint, 1 June 2026; teacher-student multi-hop QA with graph mind maps rewritten from teacher traces. | Authors report that visual graph guidance retained benefit in their abstract-guidance pipeline; their paper also reports that direct teacher-CoT training outperformed image guidance. | Preprint; teacher reasoning, rendering, condition-specific valid outputs, and fine-tuning/distillation confound attribution. | No general visual advantage, durable learning, or claim that a visual asset alone caused improvement. |
| Multimodal chain-of-thought: [Zhang et al., 2024](https://mlanthology.org/tmlr/2024/zhang2024tmlr-multimodal/) | Transactions on Machine Learning Research article; trained multimodal rationale-and-answer model evaluated on ScienceQA. | Authors evaluate a two-stage model using visual and textual rationale information. | Model architecture, training, rationale generation, and benchmark are inseparable. | No support for an external scaffold, provenance fidelity, or transfer beyond tested tasks. |
| Concept and knowledge maps: [Nesbit and Adesope, 2006](https://doi.org/10.3102/00346543076003413) | Peer-reviewed human-learning meta-analysis; 55 experimental or quasi-experimental studies. | The review reports heterogeneous retention and transfer associations for people using or viewing node-link maps. | Human studies and mixed controls; this is not primary agent evidence. | No transfer of map benefit to artificial agents or conclusion that concept maps are strategic operators. |
| Spatial mnemonic recoding: [Maguire et al., 2003](https://doi.org/10.1038/nn988) | Peer-reviewed human neuroimaging study of people known for memory feats. | The studied superior memorizers used a spatial learning strategy. | Human neural and behavioural evidence, not multimodal-model evidence. | No claim about a model's mechanism, persistent memory, or a spatial architecture. |
| Keyword method: [Mastropieri, Scruggs, and Fulk, 1990](https://doi.org/10.1177/002221949002300203) | Peer-reviewed randomized human study; 25 adolescents learning 16 vocabulary words. | In this sample, keyword mnemonic instruction exceeded rehearsal on recall and comprehension tests. | Small specialised human sample and vocabulary task. | No parameter-update, source-fidelity, or agent-transfer conclusion. |
| Loci-method synthesis: [Twomey and Kroneisen, 2021](https://doi.org/10.1177/1747021821993457) | Peer-reviewed human-learning meta-analysis of 13 RCTs. | Authors report positive recall effects while identifying high risk of experimental bias. | Human evidence and study-quality variation. | No default spatial-recoding condition or AI-memory claim. |
| Audio-temporal evaluation: [Bhattacharya, Kulkarni, and Ganapathy, 2025](https://www.isca-archive.org/interspeech_2025/bhattacharya25b_interspeech.pdf) | Interspeech 2025 proceedings; TREA order, duration, and count tasks for selected open LALMs. | The authors report that accuracy and perturbation-based uncertainty did not necessarily agree. | Benchmark-specific audio compositions and evaluated model set. | No claim that audio scaffolding improves reasoning or that uncertainty transfers to another protocol. |
| Multimodal alignment: [Girdhar et al., 2023](https://openaccess.thecvf.com/content/CVPR2023/html/Girdhar_ImageBind_One_Embedding_Space_To_Bind_Them_All_CVPR_2023_paper.html) | CVPR 2023 proceedings; learned joint embedding across image, text, audio, depth, thermal, and IMU. | ImageBind demonstrates cross-modal alignment under its training and evaluation setup. | Alignment is a representation-learning result. | No scaffold efficacy, workspace participation, reasoning, retention, or epistemic-authority inference. |
| Audio-visual latent reasoning: [Dai et al., 2026](https://arxiv.org/abs/2605.22012) | arXiv preprint, 21 May 2026; a trained system interleaving text and audio-visual latent states. | The paper reports benchmark comparisons with its explicit-text-CoT baseline. | Preprint; new supervision, training data, architecture, and evaluation are bundled. | No evidence for external audio scaffolds, a generic latent workspace, or general performance. |
| Affective representations: [Maheswaran and Desarkar, 2026](https://aclanthology.org/2026.eacl-long.165/) | EACL 2026 long-paper proceedings; emotion-direction analysis in tested language models. | Authors report dataset-transferable emotion directions while also reporting limits on complex emotion reasoning. | Model-, dataset-, and task-specific representational analysis. | No model emotion, general controllability, safety, or decision-quality claim. |
| Language-based emotion intervention: [Li et al., 2024](https://doi.org/10.1016/j.isci.2024.111401) | Peer-reviewed *iScience* article; interventions on language-model neuron populations in emotion-inference tasks. | The study tests functional validity of reported language-specific emotion-concept representations through specified neuron manipulations. | Language-model and emotion-inference scope, not multimodal task performance. | No claim that affective cues improve an agent, or that model representations are felt emotions. |
| Concept directions: [Kim et al., 2018](https://proceedings.mlr.press/v80/kim18d.html) | ICML 2018 proceedings; concept activation vectors and directional-derivative sensitivity for classifiers. | TCAV quantifies sensitivity of a model output to a user-defined concept direction. | Sensitivity is not a causal necessity test. | No operator, faithful explanation, workspace, or cross-modal mechanism claim. |
| Causal representation testing: [Geiger et al., 2021](https://proceedings.neurips.cc/paper/2021/hash/4f5c422f4d49a5a807eda27434231040-Abstract.html) | NeurIPS 2021 proceedings; causal-abstraction method in a natural-language-inference case study. | Interchange interventions can test whether aligned representations have proposed causal roles. | A bounded method and case study, not a generic certificate. | No causal claim for a probe, scaffold, or latent direction without an appropriate intervention. |
| Workspace-like representations: [Gurnee et al., 2026](https://transformer-circuits.pub/2026/workspace/index.html) | Official research article and arXiv preprint, July 2026; Jacobian-lens analysis of studied language models. | Authors report reportability, directed modulation, causal intermediate reasoning, flexible reuse, and selectivity for J-space representations in their studied systems. | Official research article/preprint, model-specific and primarily language-modal. | No visual or audio workspace-entry claim, consciousness claim, or evidence that an external mind map reaches a workspace. |

## Human-evidence quarantine

The following are **hypothesis sources only**. They do not supply evidence for
artificial-agent architecture, learning, transfer, performance, safety, or
alignment. Any later agent claim requires direct controlled evidence under its
own frozen protocol.

| Human or historical material | Permitted use | Not permitted |
| --- | --- | --- |
| Concept maps and mind-map traditions | Suggest compare typed relational graphs, outlines, radial layouts, and labelled propositions while holding canonical information fixed. | Treat a human educational association as a model effect or a preferred architecture. |
| Spatial mnemonics and loci methods | Suggest delayed recall, relation recall, source recall, and positional controls. | Infer model spatial memory or persistent retention. |
| Keyword methods and mnemonic recoding | Suggest decomposing code mapping, imagery, interaction, and retrieval tests. | Supply an answer-bearing code or call the condition learning by default. |
| Bizarreness | Suggest separately manipulating unusualness and measuring source/context fidelity alongside item recall. | Assume unusual imagery helps, or describe it as source-preserving. |
| Sung-versus-spoken presentation, rhythm, and music | Suggest matching transcript, presentation duration, order, acoustic level, rhythm, and melody before comparison. | Claim that music or rhythm benefits a model, or use Quadrivium as proof. |
| Suggestopedia | Historical source for questions about presentation and attention only. | Treat it as evidence, architecture, or an agent intervention. |
| Trivium and Quadrivium | Comparison lenses for representation, inference, interaction, quantity, structure, temporal sequence, and dynamic-state questions. | Claim that they anticipate, validate, or specify an artificial-learning architecture. |
| TRIZ and OTSM | Hypothesis sources for representation and contradiction questions. | Grant privileged operator status, create an implementation dependency, or infer empirical efficacy. |

No human-learning result transfers to artificial agents without direct,
controlled, semantically audited evidence. A human source may motivate a
negative outcome measure as readily as a candidate benefit.

## Confound register and failure conditions

| Confound or failure | Required later control | Non-interpretable condition |
| --- | --- | --- |
| Content leakage | Freeze canonical task information and inspect every arm against it. | Any undeclared added fact, omitted constraint, answer, answer-bearing paraphrase, or solved example. |
| Relation fidelity | Score entity-relation correspondence separately from item recall. | A map or audio treatment changes edges, direction, qualifiers, or dependency structure without disclosure. |
| Source fidelity | Bind claims to source identifiers and score source association separately. | A treatment loses, substitutes, or makes a source salient without matching it across arms. |
| Numerical fidelity | Audit values, units, precision, and numeric ordering. | Rendering, recoding, or narration changes a number, unit, or comparison. |
| Contradiction fidelity | Freeze contradiction identity and score detection independently. | An arm resolves, conceals, or highlights a contradiction beyond declared treatment. |
| Temporal fidelity | Bind event order, duration, interval, and time reference. | Audio, animation, or layout changes time semantics or exposure time without a matched control. |
| Task ordering and context position | Randomise or counterbalance frozen order and context position. | Ordering, recency, or context-window differences co-vary with treatment. |
| Answer hints | Audit titles, labels, colour, topology, examples, filenames, and formatting. | Any condition provides a direct or indirect answer cue unavailable to controls. |
| Generator and renderer effects | Freeze generator, revision, seed policy, rendering pipeline, and asset-validity rule. | Invalid generation, model-specific rendering artefacts, or selective regeneration changes the arm population. |
| Exposure budgets | Match or explicitly model tokens, pixels, frames, samples, duration, context position, and output allowance. | Treatment has a materially different unaccounted exposure burden. |
| Preprocessing and model capability | Bind model/revision, modality encoder, decoding, preprocessing, context window, and accessibility support. | Different capability, preprocessing, or model state is available to compared arms. |
| Tool, retrieval, example, and feedback exposure | Log and equalise tool availability, retrieval corpus, examples, feedback, and cross-arm state. | An arm receives unique retrieval, tool output, model feedback, or prior-arm output. |
| Latency, compute, and human effort | Record wall time, compute proxy, generation cost, renderer time, and human preparation/review. | A claimed efficiency result omits a material cost or uses unmatched budget. |
| Invalid or missing generation | Predeclare validity checks, reserve rule, and intention-to-treat handling. | Outcome-seen invalid assets are repaired, discarded, or replaced selectively. |
| Multiple comparisons | Freeze one primary estimand, multiplicity method, secondary labels, and regression disclosures. | Exploratory or selectively reported comparisons are presented as primary evidence. |

An “accelerated” claim would additionally require a declared unit, starting
state, metric, uncertainty treatment, matched baseline, matched budget, and
reported regressions. A reduction on one cost dimension does not compensate
for an undisclosed decline in fidelity, quality, retention, or another declared
outcome.

## Learning regimes

| Regime | What a later protocol would observe | Maximum claim before further evidence |
| --- | --- | --- |
| Same-turn conditioning | Model sees a scaffold and answers in that context. | Use of the provided treatment in that turn. |
| Within-context retention | Scaffold remains in available context and is recalled later in the same context. | Context retention, not persistent learning. |
| External-memory support | Scaffold is stored and retrieved in a later session. | Support from external retrieval, not internal retention. |
| Non-parametric persistent state | A declared non-weight state persists between interactions. | Persistent external or runtime state under its declared mechanism. |
| Parametric update | Bound model parameters change, and a benefit persists with no scaffold or retrieval. | A model-update result restricted to model, data, task, and measurement. |

No regime establishes transfer unless source exposure and a relevant held-out
family are declared and audited. Same-turn performance is not learning.

## Workspace claim ladder

Each rung requires all lower rungs. Passing one rung does not pass the next.

1. **Input availability:** an image, audio asset, or other treatment was
   presented. This is delivery evidence only.
2. **Decodability:** a probe can predict a property from a defined activation.
   This is correlation under a defined probe and data split.
3. **Cross-modal alignment:** a measured correspondence exists across defined
   modality representations. This is not reasoning or causal use.
4. **Behavioural contribution:** a preregistered treatment comparison changes a
   bounded task metric with matched controls. This does not locate a mechanism.
5. **Causal representation role:** a model-specific intervention and necessity
   test support a proposed role under declared tasks.
6. **Workspace participation:** reportability, directed modulation, flexible
   reuse, causal intermediate reasoning, and selectivity are tested in the
   same model and setting.
7. **Persistent retention or learning:** an independently defined retention or
   model-update result survives without the scaffold or retrieval.

Rungs 5–7 require model access and evidence beyond a closed behavioural API.
No rung supports a consciousness, safety, alignment, or general-agent claim.

## Original-proposal disposition

The original integration proposal is **deferred**, not admitted or rejected.
Its strongest contribution is a disciplined candidate question about derived
representations with semantic, relational, source, numerical, contradiction,
and temporal fidelity controls. Its proposed scaffold/operator separation is
reformulated: a reusable representation transform can be a candidate strategic
operator under Decision 0004, but is not one merely by being a representation.
Selection policy is separate and is not required for either term.

The proposal's visual-graph and latent-audio-visual citations support specific
research directions, not universal benefit. Its J-space material supports a
model-specific research direction, not an image/audio workspace claim. Its
human mnemonic, musical, affective, Trivium, Quadrivium,
Suggestopedia, TRIZ, and OTSM material remains quarantined as hypothesis
sources.

The review therefore recommends **deferral** rather than a new numbered track.
It recommends no new track unless the construct survives terminology collapse
and a separate architectural reason is established. A narrower future
representation-transformation question might instead be contained under an
existing track only after an explicit maintainer decision and a separately
reviewed protocol.

## Hypotheses

1. A precisely defined multimodal representation treatment may make an
   incremental contribution to at least one bounded task metric after semantic
   and exposure parity controls. This is untested.
2. Representation, generation procedure, treatment, selection policy, and
   candidate strategic operator may make separable predictions in at least one
   later protocol. If they cannot, their separate labels should collapse.
3. A highly memorable presentation may improve item recall while reducing
   source, relation, contradiction, or temporal fidelity. This is a possible
   negative outcome, not an expected effect.
4. Cross-modal alignment or a decodable direction may fail to predict causal
   use or workspace participation. This is why the claim ladder requires
   intervention and necessity evidence.

## Unknowns

- Whether any scaffold treatment survives matched content, exposure, renderer,
  and capability controls.
- Which task family can separately measure semantic, relation, source,
  numerical, contradiction, and temporal fidelity without adding answer hints.
- Whether any apparent result is better explained by a prompt, retrieval,
  tool, procedure, model capability, or external example.
- Whether a bounded representation-transform question requires its own
  governance rather than containment under Decision 0004.
- Whether model-specific workspace methods apply to multimodal models and, if
  so, under what access and intervention conditions.
- Whether a later protocol can support a legitimate held-out transfer or
  retention claim at all.

## Admission test

A separate-track recommendation requires all of the following, reviewed before
any track, decision, schema, runtime, benchmark, or evaluation is proposed:

1. At least one term survives collapse by making a prediction not fully
   captured by prompt, retrieval, tool, representation-learning, or candidate
   strategic-operator terminology.
2. A bounded question identifies canonical task information, representation
   treatment, matched semantic and exposure controls, one primary estimand,
   and negative/non-interpretable outcomes.
3. A protocol can separately audit semantic, relational, source, numerical,
   contradiction, and temporal fidelity where relevant.
4. Learning-regime labels, source exposure, model state, tool/retrieval/example
   access, generator/renderer effects, and budget limits can be frozen before
   outcomes are accessed.
5. A distinct architectural reason shows why the work cannot be governed as a
   narrower existing-track representation-transform study.
6. An independent reviewer verifies source-to-claim correspondence and finds
   no unsupported safety, alignment, transfer, novelty, retention, workspace,
   learning, acceleration, or performance assertion.

Failure of any condition produces deferral, containment, collapse, or
rejection; it does not authorise a weaker claim or a post-hoc protocol.

## References

- Bhattacharya, D., Kulkarni, A., and Ganapathy, S. (2025). [Benchmarking and
  Confidence Evaluation of LALMs for Temporal Reasoning](https://www.isca-archive.org/interspeech_2025/bhattacharya25b_interspeech.pdf).
  Interspeech 2025. DOI: [10.21437/Interspeech.2025-1228](https://doi.org/10.21437/Interspeech.2025-1228).
- Dai, Y., et al. (2026). [LatentOmni: Rethinking Omni-Modal Understanding via
  Unified Audio-Visual Latent Reasoning](https://arxiv.org/abs/2605.22012).
  arXiv preprint.
- Geiger, A., Lu, H., Icard, T., and Potts, C. (2021). [Causal Abstractions of
  Neural Networks](https://proceedings.neurips.cc/paper/2021/hash/4f5c422f4d49a5a807eda27434231040-Abstract.html).
  NeurIPS 2021.
- Girdhar, R., et al. (2023). [ImageBind: One Embedding Space To Bind Them
  All](https://openaccess.thecvf.com/content/CVPR2023/html/Girdhar_ImageBind_One_Embedding_Space_To_Bind_Them_All_CVPR_2023_paper.html).
  CVPR 2023.
- Gurnee, W., et al. (2026). [Verbalizable Representations Form a Global
  Workspace in Language Models](https://transformer-circuits.pub/2026/workspace/index.html).
  Transformer Circuits research article and arXiv preprint.
- Hou, Y., Giledereli, B., Tu, Y., and Sachan, M. (2025). [Do Vision-Language
  Models Really Understand Visual Language?](https://proceedings.mlr.press/v267/hou25c.html).
  ICML 2025.
- Hsu, J., Poesia, G., Wu, J., and Goodman, N. (2023). [Can Visual Scratchpads
  With Diagrammatic Abstractions Augment LLM Reasoning?](https://proceedings.mlr.press/v239/hsu23a.html).
  NeurIPS 2023 workshop proceedings.
- Kim, B., et al. (2018). [Interpretability Beyond Feature Attribution:
  Quantitative Testing with Concept Activation Vectors](https://proceedings.mlr.press/v80/kim18d.html).
  ICML 2018.
- Lei, R., Xiao, X., and Wei, Z. (2026). [Visual Graph Scaffolds for Structural
  Reasoning in Large Language Models](https://arxiv.org/abs/2606.02673). arXiv
  preprint.
- Li, M., Su, Y.-S., and Huang, H.-Y., et al. (2024). [Language-specific
  representation of emotion-concept knowledge causally supports emotion
  inference](https://doi.org/10.1016/j.isci.2024.111401). *iScience*.
- Maguire, E. A., Valentine, E. R., Wilding, J. M., and Kapur, N. (2003).
  [Routes to remembering: the brains behind superior memory](https://doi.org/10.1038/nn988).
  *Nature Neuroscience*.
- Maheswaran, J., and Desarkar, M. S. (2026). [EACL 2026 long paper
  165](https://aclanthology.org/2026.eacl-long.165/). ACL Anthology.
- Mastropieri, M. A., Scruggs, T. E., and Fulk, B. J. M. (1990). [Teaching
  abstract vocabulary with the keyword method](https://doi.org/10.1177/002221949002300203).
  *Journal of Learning Disabilities*.
- Nesbit, J. C., and Adesope, O. O. (2006). [Learning with concept and
  knowledge maps: a meta-analysis](https://doi.org/10.3102/00346543076003413).
  *Review of Educational Research*.
- Twomey, C., and Kroneisen, M. (2021). [The effectiveness of the loci method
  as a mnemonic device: meta-analysis](https://doi.org/10.1177/1747021821993457).
  *Quarterly Journal of Experimental Psychology*.
- Wen, Y., Wang, Z., and Sun, J. (2024). [MindMap: Knowledge Graph Prompting
  Sparks Graph of Thoughts in Large Language Models](https://aclanthology.org/2024.acl-long.558/).
  ACL 2024. DOI: [10.18653/v1/2024.acl-long.558](https://doi.org/10.18653/v1/2024.acl-long.558).
- Zhang, Z., et al. (2024). [Multimodal Chain-of-Thought Reasoning in Language
  Models](https://mlanthology.org/tmlr/2024/zhang2024tmlr-multimodal/).
  *Transactions on Machine Learning Research*.
