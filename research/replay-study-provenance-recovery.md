# Replay study: provenance, retries, and recovery boundaries

## Status and authority

This is non-normative documentary research prepared for public review on
2026-10-04 against repository snapshot `cdeff0fbec369b440f70c2cfb7cc3b8cdee12fc5`.
It reports no original experimental results; external findings remain
attributed to their sources. All G1–G7 gates remain UNACCEPTED.
It proposes no schema, fixture, code, integration, runtime test, or product
choice. It accepts no gate in [Decision 0002](../docs/decisions/0002-substrate-independent-reference-design.md)
or [Decision 0003](../docs/decisions/0003-pluggable-assessment-and-revision-research.md).
It does not change source authority or grant an external effect authority.

The narrow question is: what minimum record can distinguish durable work,
procedure state, provenance, payload integrity, and real-world effects when
an attempt ends with an unknown outcome?

The answer from this documentary pass is a set of distinctions and testable
recommendations, not a system design. Existing Beads, Dolt, Temporal, and Gas
City material addresses overlapping operational problems. None is a required
substrate for EMS, and none establishes an epistemic assessment contract.
This is optional downstream research for a consumer that explicitly has
external effects. It does not add reference-core requirements, alter the
first agent-free/no-effect workbench, or create an integration gate.

## Evidence labels

- **Source fact** means a statement directly bounded to an identified source
  and revision or to the dated official documentation snapshot below.
- **Synthesis** means a consequence drawn from those source facts. It is not a
  claim made by the source itself.
- **Recommendation** means a candidate for later review, not an accepted
  requirement.
- **Unknown** means this inspection did not establish the behavior or decision.

No software was installed or executed. No external implementation was run.
No Beads, Dolt, Temporal, or Gas City version is inferred to be installed.

## Source register

The register is limited to ten primary documents. The four Beads files listed
below were fetched from the exact pinned ref on 2026-10-04 and read in full;
the SHA values identify the returned source blobs. Mutable official web
documentation was read on 2026-10-04. Those pages are an as-accessed snapshot,
not a software version or compatibility claim.

| ID | Primary source, version, date, and reading depth |
| --- | --- |
| B1 | [Beads `internal/storage/issueops/provenance.go`](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/internal/storage/issueops/provenance.go), exact commit `c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c`; full-file exact-ref read on 2026-10-04; returned blob SHA-1 `59c15a38f22f4e6c6f88991a09d7854327c608e8`; read validation, identity derivation, insert, and read paths. |
| B2 | [Beads `internal/storage/dolt/provenance.go`](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/internal/storage/dolt/provenance.go), same exact commit; full-file exact-ref read on 2026-10-04; returned blob SHA-1 `8c4c39566c72ae958237a33a00356a3f28268fb1`; read call order, conditional branch, and error path for `withRetryTx` and `doltAddAndCommit`; helper bodies were not inspected. |
| B3 | [Beads `cmd/bd/provenance.go`](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/cmd/bd/provenance.go), same exact commit; full-file exact-ref read on 2026-10-04; returned blob SHA-1 `a7d7e7038fc39743f3f0da6c5f4a7f5bf915f2ce`; read CLI record/log/by-reference dispatch and write signaling. |
| B4 | [Beads provenance migration](https://github.com/gastownhall/beads/blob/c1c4b642ac1c08d8c828007a1c2f96e47e43ef7c/internal/storage/schema/migrations/0063_create_provenance_events.up.sql), same exact commit; full-file exact-ref read on 2026-10-04; returned blob SHA-1 `91fafbe676894096bc43c84e6042239e87cf3166`; read columns, indexes, and foreign-key actions. |
| D1 | [Dolt Transactions](https://www.dolthub.com/docs/concepts/dolt/sql/transaction/), official mutable docs read 2026-10-04; read transaction visibility, isolation description, SQL transaction versus Dolt version-control commit. |
| D2 | [Dolt SQL Procedures](https://www.dolthub.com/docs/sql-reference/version-control/dolt-sql-procedures/), official mutable docs read 2026-10-04; read `DOLT_COMMIT`, `DOLT_GC`, and `DOLT_SQUASH_HISTORY` behavior and notes. |
| T1 | [Temporal Tasks](https://docs.temporal.io/tasks), official mutable docs read 2026-10-04; read workflow replay from history, workflow-task retry, workflow-execution retry, activity-attempt, and history-recorded outcomes. |
| G1 | [Gas City issue #3005](https://github.com/gastownhall/gascity/issues/3005), project issue opened 2026-06-03 and read 2026-10-04; read problem report and receipt/replay-or-fork proposal. Issue text is not implementation evidence. |
| P1 | [W3C PROV Constraints](https://www.w3.org/TR/2013/REC-prov-constraints-20130430/), W3C Recommendation dated 2013-04-30; read validity, uniqueness, event ordering, entity generation/use/invalidation constraints. |
| J1 | [RFC 8785: JSON Canonicalization Scheme](https://www.rfc-editor.org/rfc/rfc8785.html), June 2020, Informational RFC; read I-JSON input constraints, canonical serialization, string preservation, and security considerations. |

## Source facts and bounded synthesis

### Durable work is not the same as procedure replay

**Source fact — Beads.** The pinned provenance feature is opt-in operational
recording attached to an issue. Its event kinds include work events such as
`cut`, `claim`, `suspend`, `resume`, `handoff`, `commit`, `land`, and `used`.
The event can carry an opaque actor, reference, reference kind, payload,
source, occurred time, and created time. The store validates selected
structural values; it does not interpret the actor or reference as truth,
trust, or authority. The CLI record path invokes the recorder; it does not
execute or prove the referenced operation. See B1–B4.

**Source fact — Temporal.** Temporal's Workflow Worker replays Workflow code
against Event History to recreate workflow state; prior Activity results are
read from history during Workflow replay. An Activity Task Execution is one
attempt. The Activity Execution can involve several attempts, and history
records the outcomes returned to the Temporal Service. The docs describe
workflow-task failures and workflow-execution failures as distinct retry
paths. See T1.

**Source fact — Gas City issue.** Issue #3005 reports a retry window where a
step may land an external effect and fail before its attempt closes; a later
attempt can repeat that effect. Its proposed receipt and replay-or-fork
mechanism is a design proposal in an issue record, not evidence that the
proposal shipped. See G1.

**Synthesis.** A durable work item says what work is open or complete. A
durable procedure history can say which transitions and task results the
orchestrator recorded. Neither alone proves whether a remote side effect
committed between the last observed response and a worker failure. That gap
requires a separate effect record or reconciliation against the system that
owns the effect.

### An idempotency key is not a payload integrity digest

**Source fact — Beads.** At the pinned ref, provenance identity is derived
from source, issue ID, kind, and either the reference or occurrence time. The
identity basis is colon-joined without escaping. The reference-free path
requires caller-supplied occurrence time; the recorded time is truncated to
seconds. The SHA-256 identity hash is truncated to its first 16 bytes and
formatted as a UUID-shaped value. This is a deduplication key, not a digest
of the full event payload. A duplicate `INSERT IGNORE` reports
`inserted=false` and does not
compare the supplied actor, reference kind, or payload with the stored row;
the first payload stored for that identity remains the observed row. The
migration declares a 255-character reference column and a `TEXT` payload,
without an application-level payload byte limit established in these files.
See B1, B2, and B4.

**Unknown — Beads.** The inspected validation requires nonempty source and
issue values but does not establish that every identity component excludes
the colon separator. This pass therefore does not claim that the serialized
identity basis is injective for every accepted input; nor does it establish
whether other caller layers narrow those inputs.

**Synthesis.** This answers “have we already recorded this identity?” It does
not answer “are all payload fields byte-identical?”, “did the actor's
authority hold?”, or “did the external effect happen?”. If actor, ref kind,
or payload changes while identity components remain constant, an ignored
duplicate does not report a mismatch. A deterministic key may suppress
duplicate recording while still leaving the supplied content unverified.

**Source fact — JCS.** RFC 8785 defines a canonical serialization profile
for eligible JSON data. It requires I-JSON-compatible input, including no
duplicate property names, Unicode strings preserved as-is, and numbers
representable as IEEE 754 binary64. It specifies deterministic property
ordering and serialization for hashing or signing input. It does not define
event identity, schema semantics, or business authority. See J1.

**Synthesis.** If an EMS profile later needs payload integrity, it should bind
the exact declared event bytes or an explicitly canonical payload digest in
addition to any deduplication key. Equality of canonical bytes does not prove
truth or authorization. A key collision or key reuse must not silently stand
in for content verification.

### SQL atomicity is not Dolt history retention

**Source fact — Dolt.** SQL `BEGIN`/`COMMIT` transactions isolate writes and
provide rollback; Dolt documents Read Committed behavior. SQL transaction
commits and Dolt version-control commits are separate layers. By default, a
SQL transaction commit does not create a Dolt commit. See D1.

**Source fact — Beads.** The migration declares the provenance row's
`issue_id` foreign key with `ON DELETE CASCADE ON UPDATE CASCADE`; the
provenance code describes events as append-only and the inspected API offers
no individual update/delete operation. The Dolt store calls `withRetryTx`
with a callback that invokes the row-insert helper. If that call returns
without error and `inserted` is true, the method separately calls
`doltAddAndCommit` for `provenance_events`. Errors from the latter call are
returned. The CLI exposes record/log/read commands, not an external-effect
executor. See B2–B4; helper bodies were not inspected.

**Source fact — Dolt.** `DOLT_SQUASH_HISTORY` rewrites a range on the current
branch into a new commit while leaving data at HEAD unchanged. Other branches
continue to reference their old history. Squash does not garbage-collect
orphaned commits; `DOLT_GC('--full')` is documented for reclaiming
unreferenced data. `DOLT_GC` cleans unreferenced data and may affect server
connections. See D2.

**Synthesis.** The Beads row's `ON DELETE CASCADE` describes current relational
row lifecycle. It does not alone establish deletion of a previously committed
Dolt row version, an old commit reachable from another ref, a remote copy, a
backup, JSONL/export, or derived index. Conversely, Dolt version history is
not immutable archival retention: refs can be rewritten and unreferenced
objects can be reclaimed. Storage history is a property of current refs and
storage operations, not an automatic retention policy.

**Synthesis — Beads atomicity boundary.** The inspected source expresses two
sequential calls: `withRetryTx` runs the row-insert callback, then a separate
`doltAddAndCommit` call is made for a newly inserted row. The inspected
method does not establish a single atomic transaction spanning the SQL row,
Dolt commit, and any external effect. The exact residual state after a
process crash or commit error between those calls is not established by this
source read or a runtime reproduction. In particular, the code does not by
itself prove what a subsequent duplicate record call will repair; it only
shows the Dolt add-and-commit branch is conditional on `inserted` being true.
See B2 and D1.

**Unknown.** This memorandum did not run Beads against Dolt or verify the
exact effect of deleting an issue at every commit/ref/backup layer. It does
not claim that current Beads deployment retains or erases any particular
history. Database configuration, branch topology, remotes, backups, exports,
and maintenance policy are not established here.

### Provenance constraints do not confer truth or authority

**Source fact — W3C.** PROV Constraints define validity rules for provenance
instances, including uniqueness and event-order requirements. For example,
generation precedes usage, usage precedes invalidation, and derivation has
ordering constraints. PROV uses “invalidation” for the end of an entity's
availability in the provenance model. See P1.

**Synthesis.** A PROV-valid graph can still describe a false assertion, an
untrusted actor, an unauthorized action, or incomplete evidence. Its
event-order constraints can help reject internally inconsistent histories;
they do not authenticate actors, decide source authority, set consent, or
settle data-retention duties. Model-level invalidation is not a storage
erasure procedure.

### Retry orchestration does not make outside effects exactly once

**Source fact — Temporal.** Workflow replay reconstructs procedure state from
history; it does not re-run completed Activity calls during Workflow replay.
Activity Task attempts, however, are separate worker executions. The API's
“effectively once” description concerns scheduling an Activity Execution,
even where several Activity attempts may take place. See T1.

**Source fact — Gas City issue.** The issue describes control-plane retry
state and downstream effect completion as separate concerns: an attempt can
repeat an external effect when its completion receipt is missing. It proposes
recorded outputs, replay, fork, and compensation as possible parts of a
future contract. These are proposal terms, not adopted EMS vocabulary. See
G1.

**Synthesis.** A timeout after request transmission is an unknown outcome,
not evidence of failure. In a later named scope, considering a retry requires
an explicit receiver idempotency/query contract and separate authorization
for the operation; reconciliation can inform that decision but does not
authorize it. Neither condition proves general safety. “Exactly once” must
be scoped to a named boundary; idempotent workflow transitions do not make
email, payment, publication, or model spending transactional with the
workflow database.

## Candidate recovery vocabulary

These terms are optional explanatory proposals only. They add no schema
fields or reference-core requirements and apply only if a later consumer study
explicitly includes external effects.

| Term | Candidate meaning | Must not imply |
| --- | --- | --- |
| Work item | Durable description and lifecycle of a unit of work. | Execution, effect, correctness, or truth. |
| Procedure event | Recorded state transition or attempt observation. | Complete history or remote-system outcome. |
| Effect intent | Declared external operation and stable logical identity. | Authorization to perform it. |
| Effect receipt | Evidence returned by the effect-owning system or a trusted reconciler. | That receipt content is truthful or complete without source policy. |
| Idempotency key | Receiver-recognized key for deduplicating one logical operation. | Digest of request content or proof of identical payload. |
| Payload digest | Integrity binding to defined bytes or canonical data. | Deduplication, truth, authorship, or permission. |
| Reconciliation | Read or query against the effect-owning authority after an ambiguous result. | A retry or compensation decision by itself. |
| Provenance relation | Declared link among source, activity, actor, and derived record. | Trust, source authority, truth, or consent. |
| Withdrawal | Policy-scoped removal from a view or use path. | Erasure from history, backups, exports, replicas, or indexes. |

If a later consumer study includes external effects, its bounded profile
should state whether intent is recorded before the external call, what
response counts as a receipt, where that receipt is stored, and how a crash
between remote commit and local receipt is handled. The receiving system
remains the authority for whether its effect exists. None of these records
authorizes an operation or proves general safety.

## Minimal baseline for a documentary case set

If that downstream question is selected, the lightest useful baseline is a
hand-reviewed table, not a new service or workflow engine. For each synthetic
operation, record: logical operation key; request-content digest; attempt
number; last known procedure event; effect authority queried; receipt or
reconciliation result; and next action considered. Keep keys and payload
digests separate, and use one synthetic source per case. This table does not
grant authority to take the considered action.

The bounded cases should include:

1. The receiver reports rejection before commit; a same-key retry is eligible
   for consideration only under an explicit receiver contract and separate
   operation authorization.
2. The effect commits and a receipt reaches the procedure log.
3. The effect commits but the response is lost before the worker records it.
4. A retry uses the same key but changed payload bytes.
5. A second producer submits the same key with different actor or metadata.
6. A record is withdrawn while a committed history or export still refers to it.
7. A prior commit is reachable on another branch or backup after current-row deletion.
8. The effect owner has no lookup or idempotency API, so recovery must stop as
   unresolved rather than assert success or failure.

For every case, the expected outcome is either a specific result, a declared
reconciliation path, or a stable unresolved/rejected state. “Retry because
timeout” and “delete because withdrawn” are not acceptable expected outcomes.
This table would test whether a later, bounded consumer contract is clear; it
would not demonstrate that a production integration is safe or authorize an
effect.

## Recommendations with falsifiers

Each item is a proposal for later review. Baselines stay manual and
synthetic unless a later owner decision authorizes more.

| Candidate recommendation | Lightest useful baseline | Counterexample or falsifier |
| --- | --- | --- |
| R1. Name work state, procedure state, and external effect state separately. | Hand-label one small synthetic case table with those three columns. | If every permitted case can be represented without conflation using existing repository terms and no reader mistakes one state for another, adding a new distinction adds no value. |
| R2. Keep deduplication identity separate from payload integrity. | Store a synthetic operation key beside the canonical request digest; compare both on duplicate submission. | If the receiver's documented idempotency mechanism binds and rejects any changed request body for the same key, a second local integrity mechanism may be redundant for that boundary. |
| R3. Treat timeout-after-send as unknown until reconciled. | For each fake endpoint, record its documented query and idempotency contract, then separately mark whether retry, stop, or compensation has been authorized for the synthetic case. | If a selected scope excludes ambiguous external outcomes or its receiver contract resolves them, this recovery state may be unnecessary for that scope. |
| R4. Bind receipts to the effect-owning authority and attempt lineage. | One synthetic receipt row naming authority, stable operation key, attempt, and response digest. | If the procedure's source event already contains an independently verifiable authority receipt and complete attempt lineage, a separate receipt layer is redundant. |
| R5. Treat Beads-style event logs as operational provenance, not epistemic assessment. | Compare one operational “land” record with one source-bound claim and ask reviewers what each establishes. | If a concrete record format supplies source revision, declared evidence relation, policy revision, and replay result, and reviewers do not infer more, the distinction may need no extra documentation. |
| R6. Specify withdrawal, current-row deletion, history rewriting, and copy purging as different operations. | Draw one inventory covering current table, commit refs, remotes/backups, exports, and derived views; leave unknowns marked. | If owner requirements explicitly forbid retained history and the chosen store can prove complete purge across all named copies, the proposed unresolved/withdrawn state may be overbroad. |
| R7. Keep retry, authority, and retention semantics not covered by PROV or JCS in a separately declared consumer contract. | Review one synthetic event chain and one canonical JSON byte pair against the exact property and existing consumer contract. | If a named existing consumer contract already supplies these semantics for every permitted case, an additional contract layer is redundant. Cite that contract rather than attributing its guarantees to PROV ordering or JCS canonicalization alone. |
| R8. Keep Dolt, Temporal, and Gas City as optional prior art, not EMS prerequisites. | Compare the manual table against each project's narrow contribution and record only needed concepts. | If a separately approved EMS evaluation demonstrates one system is indispensable to the stated contract and alternatives cannot meet it, revisit optionality for that scope. |

These falsifiers can narrow or reject a recommendation. They do not establish
universal safety, novelty, compatibility, or utility. In particular, a
synthetic case set cannot prove that a real provider exposes reliable
idempotency or lookup semantics.

## Open questions and stop boundary

**Unknown:** whether EMS needs an external-effect recovery contract at all, or
whether this belongs entirely to a downstream consumer. Decision 0002 keeps
the reference design substrate-independent; Decision 0003 keeps assessment
policy-scoped and authority separately governed. An assessment policy cannot
make a permission decision. Neither decision accepts a workflow runtime.

**Unknown:** whether any future source payload is retained by reference,
copied into a ledger, or represented by digest only. These choices change
withdrawal and reconstruction properties. A digest cannot reconstruct source
content, and an opaque reference does not guarantee its target remains
available.

**Unknown:** required retention duration, backup treatment, remote-history
policy, lawful withdrawal behavior, and whether a tombstone must outlive
payload deletion. No legal or deployment conclusion follows from this
documentary review.

The next minimum owner decision, if this line continues, is whether to prepare
a synthetic-only recovery vocabulary and case matrix for a later G1 review.
That choice would still not authorize implementation, integration, runtime
execution, real-data access, or publication.
