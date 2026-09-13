# English and Matryca-Knowledge alignment plan

## Status

**Inspectable editorial plan — 2026-09-12.** This plan authorises no commit,
push, pull request, issue, schema, runtime, model, Matryca-Knowledge, or
Matryca Plumber change.

## Scope

1. Locate Italian prose in the baseline and dated analysis archive; translate
   maintained explanatory prose to international English.
2. Keep historical quotations, source titles, names, legal texts, URLs, hashes,
   and third-party credits in their original form where translation would change
   attribution or meaning. Do not edit `LICENSES/` texts.
3. Establish English as the maintenance language for new maintained prose in
   `CONTRIBUTING.md`, and link that policy from the root README.
4. Add a narrow authorship statement: Marco Porcellato is the sole named human
   author, originator, and maintainer of his original contributions, and states
   that those contributions are personally held and have not been assigned to
   Matryca.
   This is not a legal title opinion, a claim of exclusive rights, a change to
   CC-BY/Apache allocations, or an override of third-party attribution.
5. State a future aspiration to develop a candidate technical specification for
   human-governed agentic memory. Do not call the present repository a candidate
   standard or alter existing advancement gates.
6. Use reviewed maintainer-accessible material to add a voluntary, static
   five-path documentation surface and a bounded alignment note. Do not claim
   ingestion, compatibility, synchronisation, federation, admission, or
   runtime integration without direct evidence.

## Checklist and gates

| Gate | Required evidence | Stop condition |
| --- | --- | --- |
| English inventory | Search results identify every maintained Italian passage. | Any remaining maintained Italian prose is unaccounted for. |
| Translation review | Meaning, non-claims, names, citations, links, hashes, and decision status remain unchanged. | Translation strengthens a scientific, legal, standards, or product claim. |
| Authorship boundary | `AUTHORSHIP.md` preserves licence allocations and third-party credits. | It claims legal exclusivity, removes attribution, or implies Matryca ownership. |
| Future-specification language | README/status/governance distinguish future aspiration from current maturity. | Text labels the current repository a standard or candidate standard. |
| Knowledge alignment | The reviewed source's exact revision and limits are retained in the private local checkpoint; public documentation stays minimised. | Any local statement implies ingestion, compatibility, federation, admission, or live integration without proof. |
| Editorial verification | Markdown links, whitespace, language scan, and changed-file review pass. | A check is described as scientific, legal, remote-state, or runtime validation. |

## Sequencing

Translation and authorship/future-language edits use the baseline and archive
inventory. The alignment note and five-path surface are a static local design.
They are local and `not_audited`; they neither create a source profile nor
request admission.

## Alignment and verification scope

This repository voluntarily provides five maintained navigation entry points:
`docs/index.md`, `docs/README.md`, `docs/log.md`, `docs/reference/index.md`,
and `docs/decisions/index.md`. Each uses the fields `type`, `title`,
`description`, `status`, and `last_verified`. The surface is local and static;
it is neither a source profile nor evidence of admission, federation,
compatibility, synchronisation, or integration with another project.

The repository has no clean immutable-snapshot audit or external registration.
Accordingly, `not_audited` is an explicit local disclosure, while `active`
describes document maintenance only. Exact provenance for the
maintainer-accessible review is kept in a separate local operational checkpoint,
not in this public repository worktree. Before any publication of a derivation
from that review, perform a privacy review and obtain explicit authorisation.

Verification in this follow-up is editorial: frontmatter presence, local links,
English-language inventory, whitespace, and changed-file review. It is not a
scientific validation, legal determination, remote-state validation, runtime
test, compatibility test, or Matryca-Knowledge ingestion/refresh operation.

## Final editorial verification — completed 2026-09-12

**Result: PASS within the stated editorial boundary.** The verified repository
baseline is `3bf173396a2c1ad91d53280c0dd6eac09b3daab7`. This verification
record did not itself publish or commit the local changes.

### Exact editorial scope

Modified repository files:

- `README.md`
- `CONTRIBUTING.md`
- `GOVERNANCE.md`
- `PROVENANCE.md`
- `research/analysis-2026-09-12/README.md`
- `research/analysis-2026-09-12/COMPLETION_REVIEW.md`

New repository files:

- `AUTHORSHIP.md`
- `docs/english-and-knowledge-alignment-plan.md`
- `docs/index.md`
- `docs/README.md`
- `docs/log.md`
- `docs/reference/index.md`
- `docs/decisions/index.md`

Local-only historical companions are retained separately from this public
repository worktree. Their contents and operational locations are not
enumerated here.

The Italian checkpoint originals, `SHA256SUMS`, archives, licence texts,
`CITATION.cff`, the epistemic core, and Decisions 0002–0005 were not changed
by this follow-up.

### Checks recorded

- A deterministic scan covered 160 relative links across 43 Markdown files and
  found no missing target or heading fragment.
- The five documentation entry points contain all required metadata fields and
  the literal verification date `2026-09-12`.
- All five frontmatter blocks parsed successfully; the required five fields
  were present and dates were ISO-formatted with the literal date `2026-09-12`.
- The maintained-prose language scan found no Italian remaining. Historical
  Italian checkpoint originals are deliberately retained with English
  companions.
- The two `llms.txt` mirrors remain unchanged.
- `git diff --check` passed.

### Residual limits and publication gate

No external URL or rendered-page check was run. These checks do not establish
formal conformance, source admission, federation, runtime behaviour,
compatibility, scientific validity, or a legal conclusion. No commit, push,
release, or other publication occurred at final editorial verification. Before
publishing any derivation of the maintainer-accessible source review, perform a
privacy review and obtain explicit authorisation.
