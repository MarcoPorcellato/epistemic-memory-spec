# Maintainer action plan — 2026-09-12

**Bound snapshot:** `3bf173396a2c1ad91d53280c0dd6eac09b3daab7`
**Status:** ordered proposals only. Every row needs the stated fresh
authorisation; none grants a later row, an experiment, source acquisition,
implementation, release, or GitHub mutation.

## Decision rule

Prioritise actions that reduce the largest claim-to-evidence gap with the least
irreversible scope. Effort is qualitative planning effort, not a time, cost, or
resource estimate. “Small” means a narrow, reviewable documentation change;
“medium” means cross-document scientific judgment; “large” means a future
independent artefact/review cycle. No row implies a model run.

## Ordered actions

| Order | Proposed action | Why this is powerful | Dependencies | Acceptance gate | Falsifier / stop condition | Main risks | Effort | Minimum next authorisation |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | Decide CFF representation and research-snapshot route; repair/validate `CITATION.cff` and README navigation. | Removes a concrete citation defect and a current dead snapshot link without expanding science claims. Live 2026-09-12 read-back found prerelease `v0.0.0-research`, but `/releases/latest` returns 404 while README uses it (`README.md:99`). | Maintainer chooses truthful CFF representation and whether snapshot navigation should name that explicit prerelease tag or promise a different stable-release policy; retain `LICENSE.md` allocation boundary. | YAML 1.2 plus CFF 1.2.0 schema valid; snapshot link resolves to its stated artifact; citation output reviewed; no release/compatibility/blanket-license implication. | `type: research` retained; `/releases/latest` retained without a stable latest release; fix implies released software or singular license; hosted output assumed without read-back. | Controlled CFF vocabulary may force misleading classification; an explicit prerelease link becomes stale after a later snapshot unless navigation policy is maintained. | Small. | Authorise one metadata/navigation-only edit and validation packet. |
| 2 | Add one compact, linked portfolio-status index in an existing authority page. | Makes Track 14/15 and decision/authorisation distinctions harder to misread; reduces navigation drift. | Reconcile Decision 0002–0005 and `STATUS.md`; decision records remain authoritative. | Every row states governing decision, portfolio status, next gate, and non-claim; README/START_HERE link rather than duplicate. | Any row says approved/active/validated without scope, or contradicts a decision. | A second status authority can itself drift. | Small. | Authorise a narrow navigation/status documentation proposal. |
| 3 | Create a Tracks 4, 8, and 12 boundary-planning packet: privacy/retention plus policy/time vocabulary and synthetic-vector design. | Resolves prerequisites that prevent honest replay, revision, and assessment work; follows Decision 0003's required order. | Prior-art overlap matrix; no source payloads; no schema/runtime commitment. | Each field has semantics, scope, valid/invalid examples, expected replay output/error, privacy/retention condition, and closest prior-art distinction. | Undeclared fallback, ambient score, filesystem timestamp, source-write path, or personal data enters design. | Scope may become a de facto hidden protocol or universal reasoning model. | Medium. | Authorise one outcome-free research-planning document set, no fixtures or implementation. |
| 4 | Derive a Tracks 2–3/6 dependency ledger from that packet: closed-envelope choices, canonicalisation, malformed vectors, replay/failure gates. | Turns abstract “ledger” language into a falsifiable sequence before any reference implementation claim. | Action 3; Decision 0002 privacy decision; pinned canonicalisation candidate. | Explicit event/replay/error cases, sequence/parent/scope/policy rejection cases, synthetic-only data, independent-review plan. | Unknown revision/order accepted; projection alters canonical event; privacy or authority boundary remains unspecified. | Prematurely selecting JSON/JCS as a complete semantics or transport solution. | Medium. | Authorise a separate specification/vector planning review after Action 3 acceptance. |
| 5 | Conduct independent Track 14 pre-freeze audit of separability, controls, and conditional `P` arm. | Tests whether the proposed candidate is independently stated or merely a procedure/prompt bundle before any task/outcome exposure. | Track 14 Phase 0 record; proposal head rebound to current main; no outcomes accessed. | Independent reviewer maps candidate, direct/process/ablation controls, adjacent explanations, parity, and whether `P` is mandatory. | Reviewer cannot state transformation apart from ordered prompt steps; matched procedure explains it; review finds uncontrolled exposure/parity. | Reviewer independence or access scope may be unclear; a review can be mistaken for Phase 1 freeze. | Medium. | Authorise one read-only independent protocol review only. |
| 6 | If Action 5 passes, complete Track 14 freeze record and precision/cost plan; if it fails, classify/contain it. | Converts symbolic quantitative claims into a reviewable decision envelope, or ends an unsupported operator claim early. | Action 5; maintainer-selected task/model/measurement governance; no execution authority. | Exact model/environment, grammar/verifier, prompts, parity, `delta`, interval method, precision simulation, `n_total`, ITT, call cap, cost ceiling, labels, provenance, stop rules. | Any Phase 1 blocker remains; finite-sample plan fails; `P` required but omitted; cost/call ceiling cannot be responsibly selected. | Frozen choices can create confirmation pressure; no result may be accessed while resolving them. | Medium–large. | Authorise a revised outcome-free preregistration review, not task generation or evaluation. |
| 7 | Maintain Track 15 bounded incubation and decide whether to authorise a dedicated construct-separability Phase 0. | Keeps a maintainer-interest question visible without assigning it unearned scientific meaning. | Decision 0005; explicitly separate from Track 14 and no model/task selection. | A named treatment makes a prediction not fully captured by prompt/retrieval/tool/procedure/renderer/capability/operator terminology; fidelity and exposure controls can be stated outcome-free. | If the named treatment is fully captured by an adjacent term or a predicate cannot be specified, retain incubation without experiment authority; a later decision may contain, rename, or retire that specific construct. | A broad “multimodal” label can hide multiple interventions and create untestable scope. | Medium. | Separate maintainer decision whether to authorise Phase 0 review; no portfolio-status change is implied. |
| 8 | Improve issue-form evidence fields and sensitive-report routing. | Captures source, counterexample, and affected-section material that existing contribution rules already require. | Action 2 status terminology; `SECURITY.md` boundary. | Prior-art form collects source title/URL/date; proposal form collects proposed change and test/counterexample; examples are public-safe. | Form requests credentials, private data, undisclosed vulnerabilities, or treats issue acceptance as normative approval. | Extra required fields can deter useful casual feedback. | Small. | Authorise a scoped issue-template documentation/configuration change. |
| 9 | Plan independent implementation/review only after vector and policy gates. | Independent replay is indispensable for a future portability/interoperability claim, but premature code would hide unresolved semantics. | Actions 3–4; exact vector suite; privacy decision; independent reviewer/implementer scope. | Independent result reports exact inputs, output/error comparison, deviations, and limitations. | Shared implementation assumptions, unavailable fixtures, or any compatibility/certification claim beyond exact profile. | Implementer may reproduce ambiguity rather than expose it. | Large. | Authorise only a review protocol after Actions 3–4, not an implementation. |
| 10 | Keep Track 13 and archival DOI/release work explicitly blocked pending separate decisions and live remote inspection. | Protects high-risk authority/identity/privacy claims and prevents publication metadata from becoming evidence of maturity. Current read-back confirms a prerelease but not DOI/Zenodo state; PR #16 is open with zero checks, not PASS. | Dedicated multi-agent governance decision; fresh remote GitHub/Zenodo read-back for archival work. | Track 13: identity, authentication, authority, consent, disclosure, conflict, minimisation, abuse cases. Archive: exact tag/commit, pre-standard metadata, verified remote record. | Single-user record presented as coordination proof; live remote state unavailable; archival action treated as scientific validation. | External publication freezes a snapshot and can falsely signal maturity. | Large / external. | Separate exact authorisation after prerequisites; no current action. |

## Dependency view

```text
Metadata and navigation:  1, 2, 8

Foundation lane:          3 (privacy + policy + time)
                              then 4 (envelope + vectors + replay plan)
                              then 9 (independent-review protocol)

Track protocol lane:      5 (Track 14 separability audit)
                              then 6 (freeze record, or contain/collapse)
                           7 (Track 15 remains incubated; separate Phase 0 decision)

High-risk external work:  10 only after independent prerequisites and live state
```

Actions 1, 2, and 8 are operational hygiene. They are intentionally not
evidence substitutes for Actions 3–7. Actions 3 and 5/7 are parallel,
independently authorised lanes: Action 3 has highest leverage for replay,
revision, dependency, and question-selection claims; Actions 5 and 7 preserve
bounded Track 14/15 construct discipline without waiting for a complete core.

## Gates for any future claim

| Claim type | Minimum evidence needed | Insufficient evidence |
| --- | --- | --- |
| Canonical replay | Pinned profile/schema/policy, synthetic vectors, expected output/error, independent replay. | Hash chain, prose design, or one local implementation. |
| Revision/dependency | Declared semantics for conflict/supersession/redaction/time/scope plus counterexample vectors. | TMS/AGM/provenance citation alone. |
| Token efficiency | Pinned projection and corpus, named tokenizer/encoder, digest equivalence, round-trip/negative vectors. | Smaller file size or one tokenizer result. |
| Candidate operator | Frozen candidate, matched budget/control, source-blind held-out task family, primary estimand, regressions, provenance, independent review. | A plausible prompt, trace, higher score, or one positive metric. |
| Multimodal scaffold | Frozen canonical information, representation treatment, fidelity audits, matched exposure/renderer/capability controls, distinct prediction. | A diagram/audio asset, alignment/probe result, or human-learning analogy. |
| Transfer/retention/learning | Declared regime/state/source exposure, structured held-out/retention protocol, exact metric, negative outcomes. | Same-turn improvement or current-context assistance. |
| Multi-agent coordination | Separate identity, authority, consent, disclosure, privacy, conflict, and abuse evidence. | Single-user provenance/replay record. |
| Archive/DOI | Exact selected release/tag and live GitHub/Zenodo read-back. | Local tag/CFF presence or documentation merge. |

## Recommended minimum next authorisation

The narrowest operational next authorization is **Action 1 only**: decide and
correct citation metadata plus the research-snapshot navigation target, then
validate those two files. This does not authorize commit or publication.

For substantive research, choose between **two separately bounded
authorisations**, not one blended project:

1. **Foundation lane — Action 3:** an outcome-free Tracks 4, 8, and 12
   privacy/policy/time vocabulary and synthetic-vector plan. It defines no
   executable protocol, schema, fixture, model, or source acquisition.
2. **Track protocol lane — Action 5:** a read-only independent Track 14
   separability/control audit. Track 15 stays visibly incubated under Action 7;
   its dedicated Phase 0 review needs a later, separate maintainer decision.

The foundation lane advances falsifiability for Tracks 2, 3, 6, and 8–13. The
protocol lane does not wait for core completion, but cannot access outcomes,
generate tasks, or create evaluation authority. If the maintainer instead wants
only low-risk operational work, authorise Action 1 as a separate metadata-only
change; do not combine it with a scientific claim.

## Non-claims

This plan does not rate the repository as stellar, complete, production-ready,
safe, aligned, interoperable, or scientifically validated. It does not assert
that any policy, ledger, candidate operator, or multimodal scaffold exists or
works. It preserves the repository's stated rule that research-track completion
adds evidence only and creates neither standard nor authority
(`OPEN_RESEARCH.md:3-7`).
