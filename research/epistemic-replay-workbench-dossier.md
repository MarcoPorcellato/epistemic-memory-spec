# Epistemic Replay Workbench: documentary research dossier

## Status and scope

**Prepared for public review; non-normative documentary research proposal,
unfrozen, with no original experimental results. All G1–G7 gates remain
UNACCEPTED.** This dossier describes a possible future, synthetic-only,
single-user Epistemic Replay Workbench. It authorises no schema, fixture,
executable, installation, runtime,
real-data, repository-integration, or publication work. It does not change the
research status in [STATUS.md](../STATUS.md), [Decision 0002](../docs/decisions/0002-substrate-independent-reference-design.md),
or [Decision 0003](../docs/decisions/0003-pluggable-assessment-and-revision-research.md).

The proposed workbench is a small research instrument for inspecting declared
evidence relations and replay decisions. It has no Matryca Plumber integration,
no authority over canonical sources, and no agent or multi-user behavior.
Portable contract correctness and exploratory maintainer utility are separate
questions with separate evidence. Documentary preparation is not gate
acceptance. No experimental result exists.

This version incorporates a bounded review of `mem`, operational provenance in
Beads, and adjacent memory research. The accompanying
[methodology and prior-art study](mem-methodology-prior-art.md) identifies
verified primary sources, reading depth, and report-only candidates. The
earlier documentary PASS applies only to its recorded dossier digest, not
automatically to this expanded version.

## Executive decision

Keep the idea at documentary-preparation stage. The next useful research
question is whether a tiny, explicit, deterministic replay contract can make
source revision, evidence relation, policy revision, and replay failure
inspectable without converting derived assessment into truth or write
authority. In parallel, a bounded maintainer study may ask whether that
inspection surface helps resolve synthetic cases enough to justify its setup,
review, and maintenance burden.

The immediate documentary question is falsifiable: **Can a bounded contract
specify an unambiguous result or rejection for each proposed synthetic case
while retaining opaque revision bindings and explicit reconstruction limits?**
Failure to specify a bounded result, explicit unresolved/unsupported state, or
rejection before profile freeze prevents documentary readiness. A later, separately
authorized implementation study may ask whether independent implementations
agree with independently reviewed expected outcomes. Agreement alone cannot
exclude a shared mistake. Maintainer utility remains a separate question: if a
fixed-evidence manual baseline meets the bounded need with less burden, the
workbench may not be worth building.

This question tests composition, not novelty. Provenance models, truth
maintenance, belief revision, event replay, versioned data, and issue-tracking
systems already cover parts of this territory. Decision 0003 rejects claims to
have invented provenance, revision, evidence weighting, or uncertainty. No new
algorithm, priority, compatibility, safety, performance, or general-utility
claim is made.

## Evidence language

Use these labels in any later research record:

| Label | Meaning here |
| --- | --- |
| **Source fact** | Directly stated by a cited primary source or repository authority, bounded to that source and version. |
| **Synthesis** | A comparison or consequence drawn from identified source facts; not itself a source statement. |
| **Hypothesis** | A proposed behavior or value claim that requires a later test. |
| **Unknown** | A decision, implementation fact, or result not established by current evidence. |

Repository fact: this remains a pre-standard draft without released protocol,
stable schema, reference implementation, conformance suite, or compatibility
programme. Decisions 0002 and 0003 propose an ordered event design and named,
versioned assessment policies; neither accepts this workbench contract. Tracks
2, 3, 4, 6, 8, and 12 are relevant. Tracks 14 and 15 remain active and
separate, unvalidated by this proposal.

Source fact: W3C PROV-DM models provenance through entities, activities, and
agents ([W3C Recommendation](https://www.w3.org/TR/2013/REC-prov-dm-20130430/)).
Synthesis: this vocabulary does not supply source-authority, assessment,
retention, or replay policy. RFC 8785 defines JCS with I-JSON constraints:
unique object member names, binary64-compatible numbers, and Unicode strings
preserved without normalisation ([RFC 8785](https://www.rfc-editor.org/rfc/rfc8785.html)).
Citing these sources does not settle event schema, identity, policy binding,
sequence, errors, or privacy. RFC 8785 is Informational, not an Internet
Standard.

Source fact: Dolt describes a version-controlled SQL database ([Dolt docs](https://www.dolthub.com/docs/introduction/what-is-dolt/)). Beads' primary README describes Dolt-powered storage with optional Git integration and a Git-free usage mode; calling it simply “Git-backed” would be inaccurate ([storage modes](https://github.com/gastownhall/beads#storage-modes), [Git-free usage](https://github.com/gastownhall/beads#git-free-usage)). Gas City issue #3005 discusses durable effect receipts and replay-or-fork for retries ([issue](https://github.com/gastownhall/gascity/issues/3005)); v1.4.2 notes Beads 1.3.0 compatibility ([release](https://github.com/gastownhall/gascity/releases/tag/v1.4.2)). Synthesis: these are adjacent concerns, not evidence for epistemic assessment or compatibility here. No external implementation was run.

Unknown: whether a minimal profile can avoid overfitting the proposed ledger,
help maintainers, define defensible retention and withdrawal, or produce
agreement across future independent implementations.

## Vocabulary boundary

The following are proposed record roles for later discussion, not a schema:

| Role | Candidate meaning | Must not imply |
| --- | --- | --- |
| **Source** | User- or source-system-owned canonical assertion or artifact. | Truth, reliability, currentness, or permission for a derived system to write. |
| **Observation** | A bounded observation of a particular source revision, with separately declared observation and recorded times. | Verification, source authority, or valid time. |
| **Claim** | A normalized proposition considered by a named policy. | Source text, truth, or independent evidence. |
| **Evidence** | A declared, revision-bound relation from an observation or claim to a claim under review. | Causal support, independence, or truth. |
| **Assessment** | Output produced by an identified policy revision over identified inputs. | Evidence itself, a universal conclusion, or probability. |
| **Procedural status** | Workflow state, such as proposed, reviewed, or withdrawn. | Assessment, truth, consent, or authority. |
| **Time** | Separate observation, recorded, assessment, and claim-valid times when available. | A single interchangeable timestamp or causal order. |

Source authority is about which record governs a source; it is not a guarantee
that the source is true. A source reference is opaque and revision-bound. A
source update creates or identifies another revision; it does not silently
rewrite the old observation or automatically falsify claims derived from it.

After admissible, scoped inputs are selected, a simple v0 relation-presence
candidate can be described using the draft's existing qualitative vocabulary.
These candidate outputs report declared relations to one claim; none asserts
truth:

| Explicit support relation present? | Explicit challenge relation present? | Candidate qualitative result |
| --- | --- | --- |
| Yes | No | `supported` |
| No | Yes | `challenged` |
| No | No | `insufficient_evidence` |
| Yes | Yes | `conflicted` |

These are illustrative only, not an accepted policy or feature commitment.
`insufficient_evidence` means no support or challenge relation was declared in
the selected scope, not evidence of falsity. A pair of separately supported
claims is not automatically a conflict. Any relation mapping must be declared
by a human for each synthetic example; no automatic NLP, embedding, or model
judgment may create one. Retrieval rank and repeated copies do not establish
support or independent corroboration.

## Minimal proposed workflow

```text
synthetic source revisions
          |
          v
human-declared, revision-bound evidence links
          |
          v
pinned-policy deterministic optional projection
          |
          v
inspectable explanation, result or explicit error
```

Every stage is read-only with respect to source records. Before assessment,
select and partition by claim, component, source/event scope, historical
cut-off, and valid-time interval; only then consider declared relations.
Incompatible scopes and disjoint intervals stay separate. A historical view
recorded under one policy is distinct from a later policy's assessment about an
earlier valid-time interval. A future optional browser or notebook could render
a projection, but no interface or tool choice is adopted here. Optional
feature failure must not disable otherwise available baseline source access;
it cannot restore an unavailable source. Output should identify exact source
revisions, event identities and order, policy identity/revision, result or
rejection, and explanation limits. If used, assessment time is declared input,
never replay-time wall clock. No source write is allowed.

Decision 0002 proposes explicit sequence and parent-digest integrity for a
future event stream. Decision 0003 distinguishes observation, recorded,
assessment, and valid time. This dossier does not replace either with a
Plumber-specific design or timestamp sorting. The exact ordering contract
remains open; timestamps describe time, never implicit order or tie-breaks.

## Threat, privacy, and retention boundary

Any eventual experiment must use synthetic content only. Exclude genuine
source text, identities, credentials, user prompts, personal data, customer
data, private vault references, and absolute local paths. Synthetic identifiers
and digests can still be linkable metadata: keep scope narrow, avoid stable
cross-case identifiers, and document what a hash reveals about equality or
known candidate content. Do not treat hashing as anonymisation.

Before implementation, a reviewed threat and retention decision must address
source-reference leakage, malicious or malformed input, scope confusion,
policy substitution, parser disagreement, replay denial of service, export and
backup copies, derived indexes, and operator error. Bound input size and
processing work in any later profile. Unknown scope, unknown policy, malformed
history, or unavailable required source revision must fail closed for the
optional projection. It must not disable otherwise available baseline source
access, and cannot restore source material that is unavailable.

The following threat matrix is a documentary checklist, not a security review,
compliance claim, or accepted control set:

| Hazard | Candidate boundary | Later rejection verification | Remaining limit |
| --- | --- | --- | --- |
| Synthetic identifiers or digests enable cross-case linkage. | Use case-local identifiers; disclose equality/linkability limits; never call hashes anonymous. | Review exported synthetic cases for stable cross-case identifiers and test known-content digest exposure. | Metadata may still be linkable within a case or through external knowledge. |
| Scope mix-up joins unrelated claims, components, sources, or periods. | Bind declared scope before relation assessment; partition incompatible scopes and disjoint intervals. | Negative vectors combine mismatched scopes and disjoint times; reject or preserve separation. | Scope declarations can be wrong or incomplete. |
| Malformed, oversized, or adversarial inputs exploit parser or replay differences. | Reject unknown structure and bound bytes, nesting, counts, and work under a later profile. | Independent parser/replay review exercises malformed and limit-exceeding synthetic cases. | Bounded checks do not establish absence of all parser or resource attacks. |
| Policy substitution or hidden fallback changes assessment meaning. | Bind policy identity/revision; reject mismatch and prohibit implicit default fallback. | Negative vector supplies a different/unknown bound policy and expects explicit rejection. | Policy correctness and governance remain separate questions. |
| Withdrawal is mistaken for deletion from history, backups, or exports. | Separate view withdrawal, payload redaction, retained tombstone, and erasure claims. | Review export/backup scenarios; reject any unqualified complete-erasure claim. | No actual deletion, backup purge, or legal retention behavior is established. |

Immutable history and withdrawal are different operations. A later withdrawal,
supersession, or redaction event may change a future projection under a declared
policy; it does not establish that retained history, backups, exports, or
derived data were erased. No actual deletion, erasure, authorisation, or
retention guarantee is proposed. A future design must state whether it can
withdraw a claim from a view, redact payload bytes, preserve an integrity
tombstone, or only mark reconstruction unavailable. These choices are
unresolved and require owner review before any implementation.

Missing required material may produce a bounded validation or reconstruction
result, but never a claim of completed assessment when required inputs are
unavailable. A later specification must order validation checks and define
which single error wins when one input has multiple defects.

## Gate 2 contract questions

Decision 0002 makes a closed JSON event envelope and pinned canonicalisation a
research direction. These unresolved questions must be decided before any
machine-readable schema or generated artifacts are considered:

| Question | Required discussion before selection |
| --- | --- |
| Canonical bytes | Is RFC 8785 the profile, with a fully identified revision and implementation constraints? What exact bytes are hashed? |
| Received versus canonical bytes | Are duplicate transport payloads compared as raw bytes before parsing, as canonical event bytes after validation, or both? Define each boundary and record identity. |
| Duplicate keys | Reject before canonicalisation; how will parser differentials be detected? JCS requires no duplicate object member names. |
| Numbers | Restrict to interoperable binary64 values, or represent larger/exact values as strings under declared semantics? Reject non-finite values. |
| Unicode | Preserve input strings as-is per JCS, with no silent normalisation; how are invalid Unicode and cross-parser discrepancies rejected? |
| Digest and identity | Is `event_id` inside or outside bytes covered by the event digest? Define payload digest, absent/redacted payload representation, and domain separation. |
| Policy binding | Which records require policy identity/revision? A mismatch with bound policy must reject; define unknown-policy failure and prohibit implicit fallback. |
| Ordering | Define stream, sequence, parent digest, root, contiguous order, scope, historical cut-off, and valid interval. Do not derive order from timestamps. |
| Repetition | Separate exact raw transport redelivery before assembly from canonical stream events. Decision 0002 rejects duplicate sequence numbers; conflicting ID/sequence bytes must reject. Freeze both boundaries. |
| Multiple defects | Define validation order and stable error precedence when one input has several defects; do not report a complete assessment if required material is structurally invalid. |
| Schema evolution | Unknown schema, extension fields, and unknown event kinds: reject or explicitly version a compatibility rule? No silent ignore. |
| Limits | Declare maximum event count, byte size, nesting, string size, and replay work, with stable bounded failures. |
| Scope and privacy | Bind stream and source-reference scope; define disclosure, retention, backup, export, redaction, and withdrawal semantics. |

Candidate choices above are proposals for review, not accepted behavior. Do not
generate a machine schema, fixtures, executable examples, or implementation
from this list. Any incompatible alternative must be recorded with its tradeoff
and rejected only by a later reviewed gate decision.

## Additional methodological controls from adjacent research

The new study narrows, rather than expands, what an initial workbench could
claim. The following source facts were examined at declared revisions; their
application to this dossier is a synthesis, not a replication result.

- `mem`'s [Decision 23](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/architecture-decisions.md)
  distinguishes a retrieval condition prepared with historical target-trace
  errors from a task-text-triggered condition. Proposed control: document what
  information was available at the inspection cutoff. A later trial cannot
  call target-hindsight retrieval autonomous error recognition.
- [`verifyFixEvidence`](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/distill/verify.ts)
  admits non-null resolution material; it does not itself execute the fix's
  tests. Proposed control: material availability, reported verification,
  executed verification, and assessment must not substitute for one another.
- Beads' pinned [provenance identity implementation](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/internal/storage/issueops/provenance.go)
  implements an operational deduplication identity, not a digest covering every
  payload field. Proposed control: record identity and canonical payload
  integrity are different questions; an event label such as `land` does not
  supply epistemic assessment or acceptance authority.
- `mem`'s [dual-confidence note](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/memory-prediction-and-dual-confidence.md)
  is a proposal separating retrieval usefulness from content correctness.
  This is relevant overlap, not a new EMS distinction. The dossier adopts
  neither numerical confidence fields nor an age-based truth-decay policy.
- `mem`'s pinned [adoption report](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/adoption-harness/RESULTS.md)
  separates observed Beads adoption from task-completion benefit. Its
  [endpoint diagnosis](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/finding-goal-endpoint-unscoreable.md)
  describes refusals of implausible synthetic configuration and an endpoint
  that could not discriminate the memory conditions. These are source-reported
  findings, not independently rerun results or proof that every refusal was
  correct. Proposed control: separate process uptake from utility and review
  scoreability before treating an action endpoint as a memory test.

Historical correctness, current applicability, and information availability
need separate annotations in a later case specification. A synthetic record
that a test passed at revision A need not become false with age; it does not
establish that the test passes at revision B. Information recorded after an
inspection cutoff cannot silently become evidence available before that cutoff.
The derived workbench must not treat inactivity alone as revocation of an
explicit permission or human constraint, or override an owner-declared expiry
rule.

[MemLineage](https://arxiv.org/abs/2605.14421v1),
[MemConflict](https://arxiv.org/abs/2605.20926v1), and
[STALE](https://arxiv.org/abs/2605.06527v1) provide adjacent questions about
lineage, temporal/factual/contextual conflicts, and obsolete premises. Only
their primary abstracts and attribution were checked for this integration;
methods, numeric findings, and general effectiveness were not established.
These are the respective authors' works, not papers authored by Jarmak.
The supplied report associates them with her reading list; that curatorial
attribution was not independently verified. No algorithm or sensitive-action
gate is adopted here.

## Proposed vector plan

The table is a coverage plan, not a corpus. It contains no frozen fixture bytes,
expected output bytes, test data, or results. Each case should later state its
scope, inputs, pinned policy, one bounded expected output or rejection class,
and its falsifier. Cases should remain synthetic and small enough for manual
inspection.

| ID | Proposed input variation | Bounded expected observation or rejection | Confound to control / falsifier |
| --- | --- | --- | --- |
| V01 | Same claim, component and time interval, explicit support only. | Candidate projection reports declared relation and policy-scoped assessment. | Label is not truth; unsupported promotion falsifies boundary. |
| V02 | Same claim, component and interval, explicit challenge only. | Candidate projection retains challenge relation; no automatic deletion. | Source wording ambiguity; lost challenge falsifies provenance. |
| V03 | Same claim/component/interval, explicit support and challenge. | `conflicted` candidate or explicit policy conflict result. | Conflict is relation to one claim; separate supported claims do not conflict automatically. |
| V04 | Same component with disjoint half-open intervals `[from,to)`. | Keep temporal records separate; do not invent conflict. | Time-zone or endpoint convention; overlap result falsifies interval rule. |
| V05 | One or both times unknown. | Preserve ambiguity; do not merge or infer conflict solely by proximity. | Missing-time defaults; inferred timestamp falsifies rule. |
| V06 | Exact raw transport payload redelivered before canonical stream assembly. | Candidate transport ingestion is idempotent; assemble one event only. | Raw-versus-canonical equality policy is unresolved; two canonical sequence entries falsify. |
| V07 | Canonical stream repeats sequence/ID, with exact or conflicting bytes. | Reject duplicate canonical sequence per Decision 0002; reject conflicting identity. | Do not silently deduplicate malformed canonical history. |
| V08 | Repeated observations may be correlated; dependence is unknown. | Unknown dependence is not independence; no independent-corroboration claim. | No dependence-metadata schema is promised; assuming independence falsifies interpretation. |
| V09 | Source changes after observation. | Retain old revision binding; new revision does not automatically mark old claim false. | Accidental “latest” lookup; source substitution falsifies. |
| V10 | Pinned source revision cannot be reconstructed. | Distinguish ledger-structure validation from source reconstruction; report the latter unavailable. | Cached or current source fallback; claiming full reconstruction falsifies. |
| V11 | Withdrawal or supersession event. | Result follows only a later explicit policy rule; otherwise reject or mark unresolved. | Unspecified semantics; silent history rewrite falsifies. |
| V12 | Bound policy ID/revision is unknown or differs from requested policy. | Reject mismatch; no implicit fallback or substitution. | Hidden default policy; any assessment under the wrong bound policy falsifies. |
| V13 | Separately supported policy profile assesses earlier valid-time interval. | Only a future supported profile may emit a distinct, policy-labelled derived result; preserve historical assessment. Unsupported by initial candidate profile. | Silent replacement or fallback falsifies; no feature commitment. |
| V14 | Complete unique transport set arrives shuffled, or canonical stream itself is malformed. | Assembly may place unique events in declared valid sequence; malformed canonical order rejects. | Sorting malformed history or using timestamps falsifies. |
| V15 | Broken parent, unknown schema, malformed JSON, wrong scope, or oversize input. | Reject optional record; otherwise available baseline access remains usable. | Partial acceptance or disabling baseline access falsifies boundary. |
| V16 | Rebuild projection from identical declared bytes, policy, and versions. | Later replay spec requires canonical output bytes or same declared rejection. | Runtime/version drift; unexplained difference falsifies reproducibility claim. |
| V17 | Optional ledger is unavailable while baseline source remains available. | Report optional feature unavailable; preserve otherwise available baseline reading. | Do not imply missing source can be restored or optional failure can block baseline access. |
| V18 | Redaction with retained history, backup, or export unknown. | State exact known deletion boundary; never promise complete erasure. | Undocumented copies; unqualified erase claim falsifies. |
| V19 | Dependency cycle in optional evidence relations. | Initially unsupported or explicitly rejected; no automatic support propagation. | No dependency metadata schema is promised; treating a cycle as evidence falsifies. |
| V20 | A synthetic verification record refers to revision A; the question asks about revision B. | Preserve the A-bound statement; do not promote it into verification of B or falsify it merely because it is older. | Revision identity is not recency; a current-success claim without B evidence falsifies the boundary. |
| V21 | Evidence is introduced after the declared inspection cutoff. | Distinguish later reconstruction from information available at the cutoff; exclude post-cutoff evidence from an earlier-availability answer. | Valid time is not availability time; hindsight presented as prior knowledge falsifies the interpretation. |
| V22 | A synthetic operational deduplication ID is unchanged while declared payload material differs. | Do not infer full-payload integrity from the ID; require the selected contract's byte/digest validation or reject the binding. | Operational event identity is not a canonical content digest; silent payload substitution falsifies the boundary. |
| V23 | Resolution material exists, but no executed verification result is supplied. | Report inspectable material and the missing verification separately; do not claim tested success or acceptance. | A transcript or diff is not a passing test; promotion of availability to verification falsifies interpretation. |
| V24 | A question contains an obsolete premise or asks for an action without declared authority. | Preserve the evidence and authority limits; a later reviewed rubric may expect correction, clarification, or abstention rather than action. | No permission engine is introduced. Scoring every non-action as failure, or treating correct content as authority, invalidates that endpoint. |

Duplicate transport delivery and duplicate canonical sequence are different
conditions. Only pre-assembly transport deduplication is a candidate; the
canonical stream must contain unique sequence numbers under Decision 0002.
Shuffled transport may be assembled into a valid declared order, but cannot
repair malformed canonical history. V11, V13, and V19 remain explicitly
unsupported until policy semantics are reviewed.

V20–V24 are additional proposed counterexamples motivated by the new research,
not imported benchmark data or executable fixtures. Their exact semantics,
expected outcomes, and eligibility remain subject to G1–G4. They add no source
adapter, assessment engine, automatic conflict resolution, or action authority.

## Correctness and utility evaluation boundary

**Contract correctness** asks whether declared bytes, source revisions, policy
identity, ordering, and errors are handled as specified. Gate 4 is a reviewed
specification of deterministic replay/failure semantics, canonical outputs,
error precedence, and ledger validation versus source reconstruction. It does
not require executed replay results. Later, separately authorised Gate 5 work
could compare independent implementations against independently reviewed
expected outcomes. Agreement alone cannot exclude a shared mistake, and an
internal model review is not independent execution. No correctness result
exists. Zero mismatches may be proposed for accepted vectors, not reported as
measured or general evidence.

**Exploratory maintainer utility** asks whether a small explanation surface
helps a maintainer inspect bounded cases. Baseline B0 is manual inspection using
identical evidence, source revisions, policy text, time information, questions,
and update history. A later candidate workbench adds only a structured trace
and replay explanation. Compare correctness and review effort separately.
Score separately whether a case's source revision, declared relation,
temporal scope, policy identity, and expected failure were correctly
identified or traced. Report correct/scorable and scorable/assigned ratios;
keep errors, omissions, timeouts, and unscorable cases distinct. Measure setup,
maintenance, and task time separately. Use matched cases and counterbalance
order where feasible; record familiarity and learning, which counterbalancing
does not eliminate. Freeze task limits and a practical burden threshold before
any future human study. A small maintainer study cannot generalise to users,
domains, products, or populations.

Before any study, freeze case selection, task wording, scoring rubric,
denominators, missing-data handling, task limits, burden threshold, and
decision rules, then hold back new cases for later review. If B0 meets the
bounded need with less burden, stop or simplify the workbench. This is a
narrow decision rule, not universal falsification of replay or provenance
research. No such comparison has run.

### Stage-specific observability, not an adoption score

For a later authorised study, use the following distinctions to diagnose where
a failure occurs. In the present dossier they are measurement questions only,
not new event fields, schemas, or runtime instrumentation.

| Stage | Separate observation to specify later | Inference that is not justified |
| --- | --- | --- |
| Capture and binding | Was the intended synthetic source revision recorded, and was provenance captured at origin or reconstructed later? | More stored records mean better memory. |
| Retrieval and exposure | Was relevant material available at the cutoff and actually supplied to the reader? | A retrieval call or citation proves applicability or use. |
| Applicability and interpretation | Were component, revision, interval, dependencies, and policy interpreted correctly? | Recency, rank, or repeated copies prove truth. |
| Use and authority | In a separately authorised agent study, was material used, and was a proposed action within declared authority? | Tool adoption or a correct answer grants permission. |
| Outcome and burden | Was the bounded question answered or appropriately left unresolved, at what total cost? | Success after retrieval proves retrieval caused success. |

The initial synthetic workbench need not run agents to exercise these
distinctions. Agent adoption, memory-trigger behavior, task-completion effects,
and persistent orchestration are later research questions with separate
authorisation, protocols, and matched budgets and permissions. Optional future
controls could compare no extra memory, source evidence, and an epistemic
explanation under identical underlying information, including cases where the
necessary information is already present. These conditions are not frozen or
implemented here and do not replace the manual B0 comparison.

A later rubric should distinguish a genuine task error from justified
abstention and from an invalid or unscorable endpoint. Proposed refusal labels
need independently reviewed case criteria; refusals are not automatically
correct. Report eligibility and scorable/assigned coverage as well as scores,
and retain every exclusion, timeout, amendment, and negative result. A protocol
amendment creates a new version; it cannot retroactively improve an earlier
result or turn an information-privileged arm into a fair baseline.

## Advancement gates

Hash identity alone is not implementation evidence; no reference implementation
is validated here. All gates below are **UNACCEPTED**. Documentary preparation may clarify
candidate questions for Gates 1–4; it does not satisfy or accept them. Gate 5
requires separate implementation authorisation. Gate 6 requires separate
Plumber design and integration authorisation. Gate 7 requires evidence from an
independent implementation or consumer; internal model review is not
independent interoperability evidence. Maintainer review cannot auto-promote a
gate. Every gate needs its own explicit evidence record, review, and decision.

| Gate | Required deliverable and acceptance evidence | Status |
| --- | --- | --- |
| G1 — threat and privacy | Reviewed threat model; synthetic-only boundary; scope, retention, backup, export, redaction, withdrawal, and failure semantics. | UNACCEPTED |
| G2 — closed contract | Reviewed closed envelope and canonicalisation profile; exact identity, digest, ordering, policy-binding, limits, and rejection decisions. | UNACCEPTED |
| G3 — synthetic vectors | Versioned positive, negative, temporal, malformed, privacy, and counterexample vectors with provenance and expected outcomes. | UNACCEPTED |
| G4 — replay semantics | Reviewed deterministic replay and failure-semantics specification, including canonical output requirements, error precedence, and ledger validation versus source reconstruction. | UNACCEPTED |
| G5 — independent implementation | Separately authorised execution over synthetic data, with reproducible notes, exact versions, and comparison to independently reviewed expected outcomes. No current reference implementation is validated. | UNACCEPTED |
| G6 — Plumber boundary | Separately reviewed adapter/projection design and evidence preserving Plumber source authority; requires separate authorisation. | UNACCEPTED |
| G7 — independent evidence | Independent implementation or consumer evidence against the exact frozen contract and vectors; no internal model review can satisfy this gate. | UNACCEPTED |

Passing one gate would not authorise real-data work, runtime installation,
Plumber changes, publication, or the next gate. Track 14 and Track 15 remain
separate and unvalidated. Any change in scope, including multi-user records,
agent actions, a live source adapter, or public corpus, requires its own
decision and evidence.

## Open decisions, in order

1. **Owner: maintainer.** Is the falsifiable question narrow and useful enough
   to continue documentary work? If not, stop or rewrite the question.
2. **Owner: maintainer with privacy review.** Which threat, scope, retention,
   withdrawal, and backup constraints must be resolved before contract design?
3. **Owner: maintainer.** Which exact canonical bytes, event identity, policy
   binding, ordering, duplicate behavior, and parser rejection rules define a
   coherent Gate 2 proposal?
4. **Owner: maintainer.** Which vector cases need one expected answer now, and
   which (notably withdrawal, dependency cycles, and source reconstruction)
   must remain out until their semantics are selected?
5. **Owner: maintainer.** What bounded manual B0 task set and burden measure
   could make a later utility study informative without overclaiming?
6. **Recommended next documentary request, requiring separate maintainer authorisation:** prepare a G1 threat, scope, retention, and failure-semantics memorandum.
   This request authorises neither the memorandum now nor any implementation;
   it is not gate acceptance or G2–G4 completion.
7. **Owner: maintainer, at a later gate.** Is there a reason to authorise
   implementation, Plumber integration, or external evidence? This dossier
   does not supply that authority.

Reviewers may improve wording, propose alternatives, or add sourced
counterexamples. Such feedback does not accept a gate or resolve an owner
decision unless the maintainer records a separate decision.

## Sources and related records

Repository source snapshot reviewed for this dossier: `epistemic-memory-spec`
commit `cdeff0fbec369b440f70c2cfb7cc3b8cdee12fc5`. Core repository references:
[STATUS](../STATUS.md), [Decision 0002](../docs/decisions/0002-substrate-independent-reference-design.md),
[Decision 0003](../docs/decisions/0003-pluggable-assessment-and-revision-research.md),
[research map](../docs/research-map.md), [open research agenda](../OPEN_RESEARCH.md),
and [evidence and review](../docs/evidence-and-review.md).

The [methodology and prior-art study](mem-methodology-prior-art.md) records
the bounded `mem` and Beads source pins, author attribution, and unverified
parts of the supplied research report. It does not attest to a census of an
author's corpus or to all numerical results in that report.

Primary external sources consulted 2026-10-04; URLs are mutable, and these
references do not establish current compatibility:

- [RFC 8785: JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785.html).
- [W3C PROV-DM: The PROV Data Model](https://www.w3.org/TR/2013/REC-prov-dm-20130430/).
- [Dolt: What Is Dolt?](https://www.dolthub.com/docs/introduction/what-is-dolt/).
- [Beads repository](https://github.com/gastownhall/beads).
- [Gas City issue #3005: Effect receipts and replay-or-fork](https://github.com/gastownhall/gascity/issues/3005).
- [Gas City v1.4.2 release: Beads 1.3.0 compatibility](https://github.com/gastownhall/gascity/releases/tag/v1.4.2).

This source list supports only the bounded descriptions above. It is not a
complete prior-art review. The companion
[documentary review record](epistemic-replay-workbench-documentary-review.md)
is a separate maintainer review artifact; its existence or outcome does not
change the gate statuses recorded here.
