# Repository inventory — 2026-09-12

## Scope and result

Inventory is bound to branch `research/triz-repository-analysis-20260912` at HEAD `3bf173396a2c1ad91d53280c0dd6eac09b3daab7`. The analyzed snapshot was clean; its tracking ref resolved to the same commit, with zero commits ahead or behind. The inventory covers all 36 tracked files at that HEAD; this report is additional to that tracked-file count.

The repository is a documentation-only, pre-standard research record. It defines epistemic-memory concepts and fifteen research questions, but contains no executable workflow, schema, fixture, runtime, package, conformance test, or implementation. Therefore zero executable checks were found; this is an absence, not a passing result or evidence of runtime behavior.

## Tracked-file inventory

| Path | Role and observed state | Risk or limitation |
| --- | --- | --- |
| `.github/ISSUE_TEMPLATE/config.yml` | Disables blank issues and directs open discussion to Discussions. | GitHub setting and destination state are remote and unverified. |
| `.github/ISSUE_TEMPLATE/counterexample.yml` | Structured counterexample intake with evidence, affected section, and privacy acknowledgement. | Template presence does not prove current remote activation. |
| `.github/ISSUE_TEMPLATE/implementation-feedback.yml` | Structured independent implementation/review feedback intake. | Template presence does not prove current remote activation or an implementation exists. |
| `.github/ISSUE_TEMPLATE/prior-art.yml` | Structured prior-art and terminology intake. | Template presence does not establish source review. |
| `.github/ISSUE_TEMPLATE/specification-proposal.yml` | Structured bounded research-draft proposal intake. | Template presence does not create normative change authority. |
| `.well-known/llms.txt` | Machine-readable navigation copy. | Local copy is byte-identical to root `llms.txt`; remote deployment unknown. |
| `CHARTER.md` | Scope, design discipline, change process, and external-engagement limits. | Documentation only; no standards or consensus authority. |
| `CITATION.cff` | Citation metadata, including version `0.0.0-research`. | Version matches the GitHub tag and published prerelease; see [live state](REMOTE_STATE.md). |
| `CODE_OF_CONDUCT.md` | Contributor expectations and maintainer enforcement route. | Remote enforcement configuration not inspected. |
| `CONTRIBUTING.md` | Evidence, privacy, issue-first, and non-normative contribution rules. | Describes process; no evidence that every remote contribution follows it. |
| `GOVERNANCE.md` | Maintainer-led governance and conditions before normative status. | Explicitly no consensus, voting, standards body, certification, or compatibility programme. |
| `LICENSE.md` | License allocation: maintained prose under CC-BY-4.0; future schemas, fixtures, examples, and reference code under Apache-2.0. | Allocation is a repository declaration; no legal opinion made. Full license texts are in the two `LICENSES/` files and are not duplicated here. |
| `LICENSES/Apache-2.0.txt` | Complete Apache License 2.0 text, preserved as source. | License text only; does not imply code exists. |
| `LICENSES/CC-BY-4.0.txt` | Complete Creative Commons Attribution 4.0 International text, preserved as source. | License text only; does not imply research has been independently validated. |
| `OPEN_RESEARCH.md` | Canonical agenda of fifteen tracks, each with a question and required evidence. | Agenda is not completion evidence; tracks 14 and 15 have separate decision boundaries. |
| `PROVENANCE.md` | Public Plumber antecedent anchors and prior-art families. | Explicitly disclaims runtime qualification, legal priority, ownership, and standards claims. |
| `README.md` | Research orientation and navigation; labels Tracks 14 and 15 as incubation. | Orientation only; subordinate to maintained status/governance documents. |
| `SECURITY.md` | States no production runtime, hosted service, or deployable package; gives safe reporting guidance. | No executable product surface is present to test. |
| `START_HERE.md` | Reader paths for researchers, future implementers, and critical reviewers. | Gives no implementation or conformance authority. |
| `STATUS.md` | Current maturity: “Research Draft — pre-standard”; enumerates advancement gates and non-claims. | Current status is source text at the bound HEAD, not a remote-release claim. |
| `VERSIONING.md` | Defines draft, research snapshot, and candidate-specification maturity terms. | No candidate specification is present. |
| `docs/decisions/0002-substrate-independent-reference-design.md` | Proposed substrate-independent event-ledger research design and alternatives. | Proposal only; its JSON/schema/ledger language is not an implemented schema or runtime. |
| `docs/decisions/0003-pluggable-assessment-and-revision-research.md` | Research boundary for versioned policy plug-ins, assessment, uncertainty, and revision. | Proposed contract only; no plug-in, policy implementation, or fixtures exist. |
| `docs/decisions/0004-incubating-strategic-agent-learning.md` | Incubates Track 14 and sets conceptual boundaries and later research gates. | Incubation does not authorize a preregistered experiment, runtime, or product change. |
| `docs/decisions/0005-incubating-multimodal-cognitive-scaffolding.md` | Records bounded Track 15 incubation, while preserving the pre-admission DEFER evidence and non-authorization boundary. | Incubation is a portfolio/documentation decision, not evidence of a distinct construct or benefit and not experiment authority. |
| `docs/evidence-and-review.md` | Distinguishes source facts, synthesis, hypotheses, unknowns, review, and evidence limits. | Method guidance only; no test results are supplied by its existence. |
| `docs/research-map.md` | States document authority and reader order. | Navigation/authority map only. |
| `research/accelerated-agent-learning.md` | Non-normative Track 14 research framing and construct boundaries. | Does not establish accelerated learning or empirical efficacy. |
| `research/explicit-strategic-learning-next-phases-plan.md` | Gated Track 14 phases after Phase 0, with separate authorization boundaries. | Future phases remain proposals; no execution or result evidence is bundled. |
| `research/explicit-strategic-learning-phase-0-issue-draft.md` | Draft issue scope and acceptance/exit conditions for Track 14 Phase 0. | Issue draft is a record, not live GitHub issue state or authorization. |
| `research/explicit-strategic-learning-phase-0-review.md` | Track 14 Phase 0 terminology/prior-art review and outcome. | Review evidence is bounded to its stated sources and date; it does not prove Phase 1 execution. |
| `research/multimodal-cognitive-scaffolding-admission-review.md` | Admission memorandum recording DEFER because six admission predicates were not established at admission strength. | Present as historical admission evidence; later Decision 0005 changes portfolio status to bounded incubation without superseding the DEFER finding or authorizing experiments. |
| `research/multimodal-cognitive-scaffolding-pre-admission-review.md` | Source-classified prior-art and construct-separability review for Track 15. | Dated review; cited external/GitHub state is not live-verified in this inventory. |
| `research/multimodal-cognitive-scaffolding-programme.md` | Canonical pre-admission packet plan, milestones, evidence boundaries, and completed documentation checklist. | Contains dated 2026-09-05 observations and older GitHub anchors; these are historical claims, not current remote state. |
| `spec/epistemic-memory-research-draft-v0.md` | Non-normative vocabulary and conceptual constraints for an epistemic-memory research direction. | Explicitly not a product API, protocol, conformance claim, or implementation. |
| `llms.txt` | Root machine-readable navigation and safety boundary. | Byte-identical to `.well-known/llms.txt`; navigation only, not an authority source. |

## Research-track coverage

`OPEN_RESEARCH.md` contains all fifteen numbered tracks and states each track adds research evidence only. The other files provide context or gated evidence as follows:

| Tracks | Present coverage | State boundary |
| --- | --- | --- |
| 1–5 | Agenda questions and required evidence in `OPEN_RESEARCH.md`; general prior-art families in `PROVENANCE.md`; advancement gates in `STATUS.md`. | Agenda-level coverage; no track-specific implementation or conformance suite. |
| 6 | `docs/decisions/0002-substrate-independent-reference-design.md` and the research draft. | Proposed architecture and evaluation criteria only. |
| 7 | Track 7 agenda; token-projection discussion in Decision 0002. | No encoder, corpus, tokenizer measurements, fixtures, or benchmark. |
| 8–9 | `docs/decisions/0003-pluggable-assessment-and-revision-research.md` and the research draft. | Policy and revision research boundary only; no policy runtime or replay tests. |
| 10–13 | Agenda questions and evidence criteria in `OPEN_RESEARCH.md`; related candidate families in Decision 0003. | Agenda-level coverage; no track-specific empirical result found. |
| 14 | Decision 0004, `research/accelerated-agent-learning.md`, Phase 0 review/issue draft, and gated next-phases plan. | Incubated; review and proposal records do not establish experiment execution or efficacy. PR #16 remains open and has no reported checks; see [live state](REMOTE_STATE.md). |
| 15 | Decision 0005, pre-admission review, admission DEFER memorandum, and pre-admission programme. | Accepted for bounded incubation after a DEFER admission review; no experiment, benchmark, schema, runtime, new repository, or Plumber change authorized. Historical GitHub anchors in this packet remain separately dated. |

No contradictory broken link was found. The Track 15 DEFER memorandum and later bounded-incubation decision are distinct, compatible records: the later decision permits documentation/incubation while preserving that admission predicates and experiment authority were not established.

## Deterministic checks and limits

The snapshot was checked at the exact HEAD above; the status was clean and the tracking ref matched it, with zero commits ahead or behind. Thirty-six tracked files were enumerated. A standard-library scan of their Markdown links found 95 inline relative links and no missing destinations or heading fragments; external, reference-style, and raw-HTML links were outside that scan. The two `llms.txt` copies were byte-identical, with SHA-256 `52738225a6cccbacfc6b648db188fe7285825293c1548de096a8ddb8e2546af6` and comparison exit status 0. A fence scan covered 30 Markdown/text files and found no unbalanced triple-backtick fences. The whitespace check was clean. The citation version matches the published GitHub tag and prerelease; latest-release endpoint reports no non-prerelease latest release. Full remote observations and URLs are in [REMOTE_STATE.md](REMOTE_STATE.md).

The file scan found only Markdown/text, `CITATION.cff`, and five issue-template YAML files. No workflow, schema, executable source, fixture, test, package manifest, or runtime was tracked. The five YAML files configure issue intake; they are not executable CI workflows. Zero executable checks is absence, not PASS.

No supplementary code-index context was available for this repository, so graph
context, process impact, and graph-based change detection were unavailable; no
index was created. Because this was a Markdown/YAML review, no supplementary
semantic-analysis coverage is claimed.

Initial sandboxed GitHub requests failed to connect. Subsequent read-only queries succeeded with narrowly scoped network permission; their live findings supersede those historical failed requests and are recorded in [REMOTE_STATE.md](REMOTE_STATE.md). This inventory reports source-tree and bounded remote evidence only; it does not establish external-link availability, scientific validity, implementation behavior, or passing executable tests.
