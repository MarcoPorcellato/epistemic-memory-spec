# Governance and discovery review

Review date: 2026-09-12

Repository snapshot: `3bf173396a2c1ad91d53280c0dd6eac09b3daab7`

Scope: repository governance, navigation, contribution, status discoverability, citation metadata, licensing boundaries, and low-cost maintainer improvements.

## Executive finding

The repository states explicit boundaries for a pre-standard research project: `STATUS.md`, `CHARTER.md`, `GOVERNANCE.md`, `VERSIONING.md`, the decision records, and the evidence documents repeatedly distinguish research acceptance from scientific validation, implementation, conformance, and authority. Track 15's incubation status and the separate authorization boundary for its next phase are reflected consistently in Decision 0005, the research map, and the README map. No material contradiction was found among those current governance anchors in this snapshot. This is not a comparative maturity ranking.

The highest-value correction is mechanical: root `CITATION.cff` declares `type: research`, which is not a valid value for CFF 1.2.0's top-level `type` field (`software` or `dataset`). GitHub's citation feature parses this file to produce citations, and Zenodo also consumes it in some release workflows. Correcting the metadata and adding a small validation check would improve citation reliability without changing research claims. The other strong opportunity is to reduce drift among several human-maintained navigation/status summaries and to make issue forms collect the source and test information already requested by `CONTRIBUTING.md`.

## Evidence and interpretation

### Status and governance

- **Observed:** `STATUS.md` says the repository is a research draft, pre-standard, with no released protocol, stable schema, conformance suite, reference implementation, or standards governance. It also states advancement gates. `CHARTER.md` and `GOVERNANCE.md` independently deny consensus, certification, compatibility, and automatic normative force.
- **Observed:** Decision 0005 records Track 15 as accepted for bounded incubation and explicitly says that acceptance does not authorize Phase 0 execution. `docs/research-map.md` and the README map retain that boundary. Decision 0004 similarly distinguishes incubation from later authorization.
- **Observed:** `README.md`, `START_HERE.md`, `docs/research-map.md`, `OPEN_RESEARCH.md`, and track-specific research files all act as entry points or summaries. The repository has a clear authority order in the research map, but no single concise per-track status table linked by every entry point.
- **Assessment:** status duplication is currently coherent, not evidence of a status error. It creates a predictable future maintenance hazard: a decision can change while a map or overview stays stale. The right improvement is a small canonical portfolio summary or a check that compares only intentionally repeated status facts, rather than treating all prose as generated data.
- **Observed on reconciliation:** the local tag `v0.0.0-research` exists. The subsequent [live GitHub review](REMOTE_STATE.md) confirms a matching prerelease, open PR #16 and issue #15, and tag rules. Earlier failed network reads do not establish missing remote resources. Discussion settings, DOI state and hosted rendering remain outside the verified scope.

### Discoverability and contribution path

- **Observed:** `README.md` provides content links and routes readers to `START_HERE.md`, the research map, evidence policy, issue chooser, discussion, and citation/license pages. `START_HERE.md` separates researcher, future-implementer, and critical-reviewer paths. `llms.txt` and `.well-known/llms.txt` have identical SHA-256 (`52738225a6cccbacfc6b648db188fe7285825293c1548de096a8ddb8e2546af6`) in this snapshot.
- **Observed:** `CONTRIBUTING.md` asks for the affected document/section, sources or reproducible counterexamples, test implications, privacy-safe examples, and an issue before a pull request. The issue forms cover specification proposals, prior art, counterexamples, and implementation feedback, with required summary, evidence/reproduction, affected section, and a public-safe checkbox.
- **Assessment:** the route is reasonably safe but asks contributors to infer what belongs in “Evidence or reproduction.” The prior-art form lacks a dedicated source URL/title and date field; the proposal form lacks a dedicated proposed change and test/counterexample field. These omissions increase maintainer clarification cycles and reduce the structured value of issues.
- **Observed:** `SECURITY.md` distinguishes public research feedback from sensitive reports and points people to private vulnerability reporting when available. This is compatible with the public-safe checkbox, but the checkbox should not imply that GitHub issues are a safe place to ask how to disclose sensitive details.
- **Unknown:** whether the public GitHub issue forms and their labels currently render as expected was not tested in GitHub's hosted UI.

### Citation and licensing boundaries

- **Observed:** `CITATION.cff` uses CFF version 1.2.0 but sets top-level `type: research`. The CFF 1.2.0 guide documents this field as an enum with `software` or `dataset` values. CFF validation requires the file to conform to the named schema and YAML 1.2.
- **Assessment:** this is a concrete metadata defect, not a claim that the underlying research is invalid. GitHub documents that `CITATION.cff` powers its “Cite this repository” output and supports APA and BibTeX output. Zenodo documents CFF support for GitHub software records. Invalid type metadata risks failed or degraded downstream parsing; the exact current GitHub output was not tested.
- **Observed:** `LICENSE.md` allocates maintained Markdown and both `llms.txt` copies to CC-BY-4.0, and schemas, fixtures, examples, and reference code to Apache-2.0. It says future assets should carry a file header or adjacent README and that third-party sources keep their own terms. That file-level split is more specific than a single repository-wide license value.
- **Assessment:** do not solve the CFF defect by mechanically inserting one top-level `license` value unless the maintainer has decided it accurately represents the cited work as a whole. Keep the split allocation authoritative in `LICENSE.md`; use CFF's citation role for citation metadata. If preparing Zenodo metadata later, check Zenodo's precedence rule: when both `CITATION.cff` and `.zenodo.json` exist, Zenodo says `.zenodo.json` takes precedence for release archiving.
- **Unknown:** no legal interpretation was attempted. This review does not determine copyright ownership, legal priority, or how any license applies in a dispute.

## Recommended actions

### 1. Repair and validate citation metadata

Have the maintainer choose a valid CFF representation for this research record, then validate it against CFF 1.2.0. The format's documented top-level types are `software` and `dataset`; if neither accurately describes the cited object, decide whether omitting the optional field (whose documented default is `software`) is clearer, or describe the work as software research without calling it a released software product. Preserve “research record,” “draft,” and “pre-standard” in title/abstract/message language rather than inventing a CFF enum value. Keep `LICENSE.md` as the authoritative file-allocation map.

**Acceptance checks:** the file parses as YAML 1.2; passes the CFF 1.2.0 schema; GitHub's citation prompt yields a usable APA/BibTeX citation; and no singular license claim is added unless it accurately describes the cited work.

**Failure checks:** reject `type: research`; reject any correction that implies a release, stable protocol, compatibility, or blanket license not established by the source documents.

**Tradeoff:** CFF's small controlled vocabulary cannot express every distinction of a research portfolio; narrative metadata and `LICENSE.md` must retain those boundaries.

### 2. Add a compact, canonical track-status index

Add a small table to one existing authority page (preferably `STATUS.md`) with each active track's decision anchor, portfolio status, next gate, and explicit authorization/scientific-evidence boundary. Link to it from README and START_HERE; keep detail in decision/research records. Include last-reviewed date or exact decision identifier so a reader can tell which source governs. Do not duplicate experiment findings or turn portfolio acceptance into an efficacy claim.

**Acceptance checks:** each row links to the governing decision and primary evidence; Track 14 and Track 15 labels match those records; an accepted incubation is visibly distinct from an authorized next phase; navigation pages link to, rather than restate, the status table.

**Failure checks:** fail review if an overview says “active,” “approved,” or “validated” without naming what exactly has that status, or if a stale row contradicts the decision record.

**Tradeoff:** a new summary adds a maintenance point. Keep it short and link-based; avoid a second status authority by explicitly making decision records authoritative.

### 3. Make issue forms capture contributor evidence in reusable fields

Add a source URL/citation field to the prior-art form, and a proposed change plus test implication/counterexample field to the specification form. Retain the existing privacy warning and affected-section prompt. For all forms, add concise placeholder guidance showing a public reference or synthetic reproduction and point sensitive security reports to `SECURITY.md`.

**Acceptance checks:** each form collects the minimum information stated by `CONTRIBUTING.md`; links to correct repository paths; accepts a public URL or a reproducible synthetic example; and clearly directs sensitive disclosures away from public issues.

**Failure checks:** reject form text that solicits private vault exports, real credentials, personal data, or undisclosed vulnerability details; reject a form that labels research issue acceptance as approval of a normative change.

**Tradeoff:** more required fields can deter casual feedback. Require only the fields that materially improve review; keep narrative evidence flexible.

### 4. Add lightweight repository checks for metadata and navigation

Consider one small CI workflow that validates CFF and checks a short set of stable invariants: both `llms.txt` copies are identical; README/START_HERE/research-map links to maintained core files resolve; status-summary terms point to existing decisions. GitHub Actions supports workflows triggered by pushes, pull requests, and other repository events. Keep checks deterministic and limited to docs; pin third-party actions to immutable commits if actions are used. A link checker should avoid failing on transient external websites unless the failure is clearly reported as network-dependent.

**Acceptance checks:** a deliberately invalid CFF field fails; changing one `llms.txt` copy fails; removing a linked core file fails; an ordinary external-site outage does not masquerade as a source-content defect.

**Failure checks:** fail review if CI claims semantic truth, legal validity, or status correctness from link/schema checks; reject a broad network crawler or dependency-heavy build that costs more to maintain than the documentation risk it addresses.

**Tradeoff:** CI adds maintenance and may create flaky network checks. Start with local-file/schema invariants and keep remote-link freshness as a periodic manual check.

### 5. Treat archival DOI as a separate publication decision

The README links to a “Latest research snapshot.” The subsequent [live GitHub review](REMOTE_STATE.md) confirms the existing research prerelease and a 404 from the latest-release endpoint; an existing prerelease must not be reported as absent. DOI state is unverified. Distinguish a navigation-target correction from a separate archive-publication decision. If the maintainer wants persistent archival citation, select a dated, non-normative snapshot and its metadata before enabling any release-to-archive integration. GitHub documents releases as tag-based named points in repository history; Zenodo documents issuing records/DOIs through enabled GitHub release integration. Do not create a release as part of a documentation cleanup.

**Acceptance checks:** a published snapshot is tied to an exact tag/commit, states “research snapshot — pre-standard,” and has citation metadata consistent with the actual archived contents and license map; DOI and GitHub release identifiers resolve to that snapshot.

**Failure checks:** no claim of DOI, archival, or immutable publication without checking the actual remote records; no archive publication until the maintainer has deliberately selected the exact content and release scope.

**Tradeoff:** an archive improves durable citation and discovery but freezes a dated research state and creates metadata upkeep. It is not evidence of validation, adoption, or standardization.

## Primary references consulted

1. GitHub Docs, [About CITATION files](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-citation-files) — repository citation file and supported generated citation outputs.
2. Citation File Format, [Schema guide 1.2.0](https://github.com/citation-file-format/citation-file-format/blob/main/schema-guide.md) — YAML/schema requirements, top-level `type`, metadata fields.
3. Zenodo, [Describe software](https://help.zenodo.org/docs/github/describe-software/) — GitHub-release metadata support and precedence when both CFF and `.zenodo.json` exist.
4. GitHub Docs, [Referencing and citing content](https://docs.github.com/en/repositories/archiving-a-github-repository/referencing-and-citing-content) — GitHub-to-Zenodo integration and release-triggered archive/DOI behavior.
5. Zenodo, [Archive a release from GitHub](https://help.zenodo.org/docs/github/archive-software/github-upload/) — archive processing and DOI/archive status checks.
6. GitHub Docs, [Releases](https://docs.github.com/en/repositories/releasing-projects-on-github/about-releases) — releases are based on Git tags; useful boundary between research draft and dated snapshot.
7. GitHub Docs, [Workflows](https://docs.github.com/en/actions/concepts/workflows-and-actions/workflows) — workflow events and jobs, used only to assess a lightweight documentation-check proposal.
8. Wilkinson et al., [The FAIR Guiding Principles for scientific data management and stewardship](https://doi.org/10.1038/sdata.2016.18), *Scientific Data* 3, 160018 (2016) — original primary paper considered for findability/reuse context. FAIR is a research-data framework, not a maturity score or standards-conformance test for this repository.

## Review limits

No repository graph index was available; deterministic document inspection supplied the local evidence. Language-server symbol analysis was unnecessary for this Markdown governance review. Source-content conclusions remain bound to the stated baseline. Remote release, coordination and ruleset observations are separately dated in [REMOTE_STATE.md](REMOTE_STATE.md); hosted issue and citation rendering, DOI state and unqueried settings remain unverified. This review offers evidence-backed maintainer proposals, not legal advice or authority to implement, publish, or change governance.
