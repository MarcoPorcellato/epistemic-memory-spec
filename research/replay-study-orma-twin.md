# Adjacent study: Metodo ORMA and ORMA Twin

**Scope:** Non-normative documentary comparison for the
[Epistemic Replay Research Programme](replay-study-programme.md).
Sources consulted 2026-11-05. No product access, personal profile collection,
implementation inspection, or experimental replication was performed.

## Attribution and evidence

Francesco Paolo D’Amico is identified as the founder of damico.ai and the
creator of Metodo ORMA by [Consumerismo’s institutional profile][bio].
D’Amico’s [first-person description][twin] identifies **ORMA Twin** as an
application of that method. This identification applies to damico.ai’s project;
shared names are not grounds for attributing other ORMA products or publications
to D’Amico.

- **Metodo ORMA** is the method. D’Amico describes four areas—*Osservazione,
  Risorse, Motivazione, Azione*—and a professional-context audit used to elicit
  recurring decision criteria and concerns. [Author description][twin]
- **ORMA Twin** is the resulting collaboration setup in the author’s
  description. It uses an existing language model with configured instructions,
  criteria, skills, projects and checks informed by the person and their work
  context. The author positions it as decision support, explicitly rejecting
  the idea of a clone or a new model. This is evidence of the claimed design,
  not an implementation audit. [Author description][twin]
- **Audience and scope.** damico.ai describes services for professionals,
  entrepreneurs and small and medium-sized businesses. Designing an assistant
  for someone working in a company does not establish a company-level replica,
  an autonomous representative or fidelity to an individual’s future decisions.
  [Project profile][project] · [Author description][twin]
- **Modalità Zero** is described by damico.ai as a rule of conduct: make missing
  evidence and uncertainty visible instead of filling gaps with a plausible
  answer. This is a documented intent; no enforcement mechanism or measured
  abstention behaviour was established. [Project explanation][zero]

damico.ai also describes a personalised offering called *Bussola AI*.
Its [founding ethical code][code] sets out intended assistant behaviour,
including asking clarifying questions and reminding the user of previously
declared goals. It does not establish how those goals are recorded or how a
later correction overrides them. The reviewed sources do not establish
whether Bussola AI and ORMA Twin share the same implementation.

## What the 2025 white paper documents

- **Elicitation and configuration.** The report describes four questionnaire
  dimensions and an ORMA Sequence derived from the ordered responses. The
  sequence informs a narrative profile and instructions for the Bussola AI,
  including tone, priorities and when to ask questions. The ChatGPT example
  uses custom instructions and an initial request to save the profile and
  instructions in the host platform’s conversational memory. This documents
  the author’s setup procedure. Cross-session persistence remains an
  author-reported behaviour. [White paper, pp. 11–14 and 24–28][orma-pdf]
- **Early feedback.** The author reports 10 completed analyses and five
  personalised Bussola AI deliveries in a selected group. The outcomes
  section presents feedback from those users and selected case narratives.
  It gives no matched comparison or psychometric reliability estimates from
  which to assess decision quality or instrument validity.
  [White paper, pp. 29–32][orma-pdf]
- **Comparing profiles over time.** The report describes a *Twin
  Comportamentale* in development, intended to compare profiles from two
  assessment periods. Repeat questionnaires and updated assistants appear as
  proposed follow-ups. The later ORMA Twin announcement describes a
  collaboration setup. The sources leave open whether that offering
  implements the temporal comparison described in 2025.
  [White paper, p. 38][orma-pdf] · [Later author description][twin]

## Relevance to epistemic replay

ORMA is a useful adjacent example of **eliciting decision criteria for an
assistant**. A replay workbench asks a separate question: **can a reader
reconstruct why a declared policy produced an assessment from particular
evidence at particular revisions?** One system could do both, but
personalisation and replay require different evidence.

| Comparison question | Documentary implication for EMS | Counterexample or limit |
| --- | --- | --- |
| What was explicitly stated, and what was inferred? | Distinguish a person’s statement from a derived preference, rule or policy. Bind role, context and effective period before reuse. | An inferred preference that sounds plausible can contradict the person’s explicit instruction. Agreement with their style does not validate the inference. |
| What happens when a declared goal changes? | Distinguish a historical statement from a currently effective constraint. Keep correction and withdrawal attributable to their source. | Correctly recalling an earlier goal becomes misleading if a later explicit withdrawal is ignored. |
| Who may decide or act? | Keep a decision aid’s suggestions, human authorisation and the resulting action separate. A company use case does not collapse individual and organisational authority. | A profile recommends an action which the user has no authority to approve. Matching the profile cannot supply permission. |
| How are evidence gaps handled? | Separate language expressing uncertainty from a recorded assessment derived under a declared policy. | A fluent answer that labels itself uncertain still fails a provenance check if no inspectable sources or policy revision support it. Conversely, an explicit insufficiency result may be correct even if it is less helpful in conversation. |
| Does structure add value? | Treat any advantage of structured elicitation or representation as a hypothesis. An eventual comparison would need matched information, model, task, effort and decision criteria. | If an ordinary, equally informed brief yields equivalent inspection outcomes within a declared margin, the additional structure has no demonstrated benefit on that endpoint. |

The white paper’s sequence-to-profile transformation makes the first two
questions concrete. If a later questionnaire yields a different profile, a
reader would need the source responses, dates and derivation rules to
distinguish a change in the person’s answers from a change in interpretation.
Comparing two profiles and reproducing an assessment from its source
revisions are separate operations.

These are research questions, not proposed profile fields, policies or new
cases. They do not alter existing replay contracts or gates. Do not infer
psychometric validity, fidelity, generalisation, safety, privacy compliance,
or performance. In the sources reviewed, we did not establish a public
implementation contract for provenance, version history, correction,
revocation, deletion or deterministic replay. The absence of such evidence
from this review does not show the features are absent.

## Selected bibliography and reading depth

- **D’Amico, Francesco Paolo.** [ORMA Twin author description][twin].
  First-person public project explanation, read in full as exposed by the
  platform. Supports attribution, positioning and described design.
- **damico.ai.** [ORMA Twin][official] and [project profile][project].
  Official product and company references. The product page identified the
  offering, but the retrieved page did not expose a technical specification.
- **damico.ai.** [Public explanation of *Modalità Zero*][zero].
  Primary source for the stated insufficient-evidence behaviour.
- **D’Amico, Francesco Paolo.** [*Codice Etico Fondativo della Bussola AI –
  Metodo damico.ai*][code], 16 June 2025. Four-page public document, read in
  full. The relationship and active-mission sections describe intended
  behaviour, not technical guarantees.
- **D’Amico, Francesco Paolo.** *All’inizio era un prompt… poi è diventata la
  mia Giulia*. StreetLib, 2025, print identifier 9791223970539.
  [Author announcement][bookauthor]; [edition metadata][book].
  Bibliographic identification and author’s description only; the book was
  not read in full and is not evidence about current ORMA Twin internals.
- **D’Amico, Francesco Paolo.** [*AI Act e Shadow AI, la vera scadenza per le
  aziende è capire chi usa già l’intelligenza artificiale*][shadow],
  Consumerismo, 10 June 2026. Practitioner commentary, read for its
  recommendation to map tools, roles, data and oversight and distinguish
  suggestions from decisions. It is not an ORMA Twin evaluation; this note
  does not rely on its legal claims.
- **D’Amico, Francesco Paolo.** *Metodo ORMA – Un approccio integrato tra AI
  e consapevolezza decisionale*. Zenodo report, v1.0, 4 September 2025.
  Version DOI `10.5281/zenodo.17057676`. The [Zenodo record][orma-record]
  and [DataCite metadata][orma-datacite] agree on title, author, date and
  version. The 40-page deposit was retrieved and checked against Zenodo’s
  file size and MD5. Sections on the method, configuration, early feedback
  and roadmap were read directly. [Version DOI][whitepaper] · [Deposited PDF][orma-pdf]
- **Mohammed, Abdul Mannan, et al.** [*A Human Digital Twin Architecture
  for Knowledge-based Interactions and Context-Aware Conversations*][hdt],
  arXiv v1, 2025. Abstract and metadata: an embodied interface for
  contextual knowledge and dialogue in human–autonomy teaming. This use
  of “twin” is distinct from ORMA's practitioner offering and does not
  establish behavioural fidelity for ORMA.
- **Park, Joon Sung, et al.** [*LLM Agents Grounded in Self-Reports Enable
  General-Purpose Simulation of Individuals*][park2026], arXiv v3, 2026
  (first submitted 2024). Abstract and metadata: individual-response
  simulation from interviews and surveys, compared against held-out items
  and a human test–retest reference. Methodological comparator only; it does
  not validate ORMA or establish proxy authority.

Remaining evidence gaps concern worked, non-sensitive examples or
evaluation protocols that distinguish user-stated criteria from inferred
criteria and show how later corrections take effect.

[bio]: https://associazione.consumerismo.it/team_member/francesco-paolo-damico/
[twin]: https://it.linkedin.com/posts/francescopaolodamico_metodoorma-ormatwin-damicoai-activity-7521191894341660672-Poj2
[project]: https://www.linkedin.com/company/damico-ai
[zero]: https://it.linkedin.com/posts/damico-ai_intelligenzaartificiale-aigovernance-aiconsapevole-activity-7509215979042689024-wwO2
[official]: https://damico.ai/twin
[bookauthor]: https://it.linkedin.com/posts/francescopaolodamico_ai-metodoorma-damicoai-activity-7388549975971917826-OW8w
[book]: https://www.lafeltrinelli.it/all-inizio-era-prompt-poi-libro-francesco-paolo-d-amico/e/9791223970539
[shadow]: https://www.consumerismo.it/ai-act-e-shadow-ai-la-vera-scadenza-per-le-aziende-e-capire-chi-usa-gia-lintelligenza-artificiale-50812.html
[whitepaper]: https://doi.org/10.5281/zenodo.17057676
[orma-record]: https://zenodo.org/records/17057676
[orma-datacite]: https://api.datacite.org/dois/10.5281/zenodo.17057676
[orma-pdf]: https://zenodo.org/api/records/17057676/files/White%20Paper%20ORMA.pdf/content
[hdt]: https://arxiv.org/abs/2504.03147v1
[code]: https://files.supersite.aruba.it/media/16721_7bd35aa69691796a7c318df5b3a9456b34c8da32.pdf/o/codice%20etico%20fondativo%20della%20bussola%20ai%20%E2%80%93%20metodo%20damico.ai.pdf
[park2026]: https://arxiv.org/abs/2411.10109v3
