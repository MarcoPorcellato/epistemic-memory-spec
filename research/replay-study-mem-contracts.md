# Pinned mem source study: retrieval, verification, and replay boundaries

**Status:** Prepared for public review; non-normative documentary study with no
original experimental results claimed. All G1–G7 gates remain UNACCEPTED.

**Research cut:** 2026-10-04.

**mem source pin:** sjarmak/mem commit 66967ea889eefb0d2cb7bf36902533e5655ee0ab.

This study deepens the bounded prior-art inspection recorded in
[mem-methodology-prior-art.md](mem-methodology-prior-art.md). It does not
change the status of the [Epistemic Replay Workbench
dossier](epistemic-replay-workbench-dossier.md), Decision 0002, or Decision
0003. Its purpose is to sharpen counterexamples and limits for the first
manual, synthetic EMS workbench.

No tests, benchmarks, paid runs, runtime, installation, source integration,
Beads operation, or other-repository mutation occurred. Public source text was
retrieved at the exact pinned commit. The result is a static source audit, not
a compatibility, production-behaviour, privacy, or scientific-effectiveness
claim.

## Evidence labels and inspection depth

Use four labels in this study:

| Label | Meaning |
| --- | --- |
| **Source fact** | Directly visible in the cited code or document at the pinned commit. A source comment is a fact about what the author wrote, not automatically proof of the described runtime effect. |
| **Source-reported result** | A result or event that a pinned project document reports. It was not independently rerun here. |
| **Synthesis** | An interpretation of cited source facts for EMS. It is not a statement made by mem. |
| **Unknown** | A behaviour or result that these selected files do not establish. |

The audit used twelve relevant files. Eight were read in full: the README,
exclusions module, retrieval module, memory-event schema, memory-event store,
memory-event store tests, schema tests, and verify module. The 704-line
retrieval test file was read at the temporal, exclusion, trigger, and
query-construction sections. The 229-line three-arm preregistration was read
in bounded ranges spanning its question, arms, endpoint, gates, accounting,
build plan, traps, and limitations. The synthetic-arm report module and
dual-confidence design note were read in full. Directory listings supported
file selection only. This is not a whole-repository or corpus census.

## Pinned source register

Each URL binds the file to the same full commit. Blob IDs identify the exact
file contents returned during inspection.

| File | Blob | Locations / depth |
| --- | --- | --- |
| [README.md](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/README.md) | 1638bee819fc50a6d092b5b66a53bdd3364f2066 | Full; project status and evaluation claims, lines 32–90; retrieval outline, lines 186–220. |
| [src/retrieve/exclusions.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/retrieve/exclusions.ts) | 13f1ecd0899dae0064d93fb91ef03ced1b8f1d6d | Full; isSibling, lines 4–12. |
| [src/retrieve/retrieval.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/retrieve/retrieval.ts) | ecf03da5df3358b4111e3efecfc89f8aca93fd58 | Full; trigger and query schema, lines 37–65; selection and ranking, lines 212–349; queryFromRecord, lines 351–408. |
| [tests/retrieve.test.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/tests/retrieve.test.ts) | 72396a3fcb18583e0fae39410588136d2a61af15 | Selected test sections; temporal boundary, sibling exclusions, scopes, trigger, and queryFromRecord, including lines 82–329 and 540–703. |
| [src/schemas/memory-event.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/schemas/memory-event.ts) | 2fcc0b9cfb353619744b41018339facfbced380e | Full; event fields and strict top-level schema, lines 55–93. |
| [src/store/memory-events.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/store/memory-events.ts) | 01e1dcff1cd0d0e7ff42039c0bc6e2f5aabf54ac | Full; append, deduplication, reads, ordering, export, and import, lines 1–159. |
| [tests/store.memory-events.test.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/tests/store.memory-events.test.ts) | a6d2dc73e77707ce92dea24310e50af1f9ab0b63 | Full; store and schema exercises, lines 1–131. |
| [tests/schemas.test.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/tests/schemas.test.ts) | d699c9b64d2c7871108334f4fe10847fa7132b4c | Full; TraceError, Execution, and WorkRecord schemas. It does not directly test MemoryEventSchema. |
| [src/distill/verify.ts](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/src/distill/verify.ts) | b13ee4fa826eed053072f029b5fe48f3bbf9fc57 | Full; verifyFixEvidence, recordSignatures, and checkPriorFixRegression, lines 1–112. |
| [memory-bench/membench/report/synthetic_arms.py](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/memory-bench/membench/report/synthetic_arms.py) | bd80577c6413f6001d8359fd52ab354add35062e | Full; evaluator and denominator behavior, lines 1–230. |
| [docs/prereg-beads-three-arm.md](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/prereg-beads-three-arm.md) | 3826913a23f373fac7c8386937f9d7fcdd2486ef | Full text read in sections; endpoint and arm asymmetries, gates, accounting, amendments, residual limits, lines 1–229. |
| [docs/memory-prediction-and-dual-confidence.md](https://github.com/sjarmak/mem/blob/66967ea889eefb0d2cb7bf36902533e5655ee0ab/docs/memory-prediction-and-dual-confidence.md) | 818583c117e11f277fec9b76020eb46aa44e59fc | Full; proposal status and candidate fields, lines 1–110. |

## Retrieval trigger and temporal eligibility

### Source facts

The retrieval module names two trigger modes. The trace mode supplies stored
error records; issue-text mode supplies dispatch-time title and task type.
The source comments explicitly classify replay from the held record's own
errors as an oracle trigger: a new agent would not yet have produced that
failure. queryFromRecord defaults to trace. The test source confirms that
default and separately checks the issue-text path.

The query requires a started timestamp. queryFromRecord uses the record's
started time and falls back to created when started is absent. The retrieval
path asks the store for records closed strictly before that boundary and with
trace errors. same_rig_temporal retains same-rig rows; cross_rig excludes the
query rig. It then excludes the target itself, its supersedes closure, and
sibling rows identified through convoy, PR, external branch reference, session
UUID, or parent/child relation. Tests exercise strict-before cutoff and these
exclusion classes.

Candidate ranking is fixed in source: exact failure signature, then
tool-plus-error-class, then message match; tie ordering uses matched counts,
FTS position, and work ID. Retrieval caps FTS candidates and surfaces a
truncation flag. The returned item contains lessons and citation data; only
same-rig retrieval adds literal file-and-line references. The module states
that it does not inject the prior raw trace.

### Synthesis

The temporal rule is *retrieval eligibility*, not claim valid time. It says
that a work record closed before task start may be considered. It does not
specify when an assertion held in the represented world, whether it remains
applicable at a later source revision, or whether a human accepted its
resolution.

Likewise, closed work plus a stored trace error is not, by itself, an explicit
acceptance or verification predicate. The inspected retrieval path does not
call verifyFixEvidence. EMS should not translate “retrieved as prior work” into
“verified fix,” “current fact,” or “accepted assessment.”

The trigger source changes what can be claimed. A trace-triggered replay can
study retrieval after supplying target-derived error information; it cannot
by itself support an autonomous error-recognition claim. The issue-text
condition is a useful information-source control, but it remains a mechanical
title/task-type query, not evidence of an agent choosing to retrieve.

### Counterexample and falsifier

Keep a target task and lesson set fixed. If a retrieval answer changes only
because the query receives the held target's future trace error rather than
dispatch-time text, the trigger is part of the treatment. Any claim that treats
both triggers as equally available task information is falsified.

A second counterexample is a record that is closed before task start but refers
to source revision A, while the question concerns revision B. Eligibility by
close time alone cannot establish applicability to B. If an EMS manual case
does not make that distinction visible, its temporal question is underspecified.

The observed tests establish source-level expectations for selected synthetic
rows only. They were not run during this study and do not show that every
retrieval path, corpus row, or downstream consumer obeys those expectations.

## Resolution material and verification

### Source facts

verifyFixEvidence is a pure admission check. It rejects null resolution
evidence and admits any non-null ResolutionEvidence passed to it. Its comment
describes the gate as admitting a candidate only when resolution material
exists, such as a landed diff or readable transcript. The function itself
does not execute tests, inspect a verifier receipt, compare a source revision,
or establish that a fix passed.

The neighboring regression functions operate on failure signatures. They
collect distinct signatures from a record and flag later closed records with
the same signature, after excluding the source work item and siblings. The
module describes this as the mechanical level supported by the records, not
literal replay of a historical build. It also says source timestamps are
approximate anchors and identifies prior replay work as a null.

### Synthesis

Material presence, provenance, executed verification, verification result,
acceptance, and later recurrence are separate states. A readable diff can be
inspectable evidence while leaving test success unknown. A clean signature
recurrence window is not proof that the original patch passed, and a later
recurrence does not alone prove that an earlier patch was wrong in its own
scope.

EMS already has a useful candidate distinction in V23: material availability
must not become executed verification. The mem implementation sharpens the
counterexample: a non-null resolution object passes this admission function
without a test run in the function. A manual workbench should preserve both
facts—“material admitted” and “verification not supplied”—rather than
collapsing them.

The inspected function does not establish the caller's full orchestration,
the fields of ResolutionEvidence, or whether another layer records tests. Those
remain unknown because the caller and the evidence type were outside this
bounded file set.

## Memory-event identity, payload, and ordering

### Source facts

The selected MemoryEventSchema represents operations such as read, write,
update, delete, search, consolidate, promote, and forget. It records an ID,
session, optional work ID, operation, backend, optional memory reference,
optional use location, concrete tool, optional payload, source, event time,
and ingest time. It is an operation-capture record, not a claim or assessment
schema.

The schema is strict at the top level and limits operation and backend values.
Its payload, however, is a string-keyed record whose values are unknown to the
schema. The source comment describes payload as structured non-content
metadata, but the type does not semantically inspect nested values for memory
text or outcome labels.

The store appends with INSERT OR IGNORE and treats the ID as its primary
deduplication key. A duplicate ID is skipped; the first row is not updated.
Rows can be read by work ID or session, and export/import preserves the event
table across record rebuilds. Reads sort by occurred_at and then ID, with null
event times last. This is deterministic display order over those fields, not a
stream sequence or parent-linked replay contract.

Tests cover insertion, reads, operation filtering, event-time order, survival
across record rebuild, export/import, duplicate-ID no-op, and rejection of a
new top-level field. The duplicate test repeats the same event; it does not
test a conflicting payload under an already-used ID. The schema test file
covers other schemas, while the store tests invoke MemoryEventSchema through
their event factory and writer.

### Synthesis

An operational event ID is not automatically a digest of all event content.
When two different payloads share one ID, INSERT OR IGNORE gives an
idempotent first-write-wins result, not a conflict diagnosis. The inspected
code does not establish whether that is acceptable for this capture path; it
does establish that the key is not a whole-payload integrity proof.

The strict object boundary is also narrower than the comment's privacy
description. A future focused probe should supply nested payload values that
resemble source text or outcome labels and establish whether a separate
firewall rejects them. This source audit did not run such a probe. The
conclusion is a schema-level limitation, not a finding that captured rows
actually contain such material.

These event records are useful prior art for auditable operation capture.
They do not by themselves supply EMS source authority, source-revision binding,
policy identity, valid-time semantics, claim-level evidence, or deterministic
assessment replay. That is a bounded description of the files inspected; it is
not proof that no other mem component addresses any of those concerns.

## Synthetic harness versus agent utility

The synthetic-arm module defines independent-sequence and shared-project
evaluators. It sets the configured agent ID to scripted-ref. Its module
documentation describes the reference ScriptedAgent as retrieving by exact
ID: exact-ID oracle and filesystem arms can reach oracle-level reward by
construction, while lexical query/top-k can surface seeded distractors and
superseded values. This is a harness mechanics result, not a language-model
retrieval result.

The module computes lift against no-memory reward and gap from oracle reward.
Confusion and staleness rates use only MEMORY_ENABLED trials that attempted a
read, and the contributing count is exposed as rate_n. Token and latency
cost deltas use all no-memory and memory-enabled trials. For shared-project
evaluations, its own comment warns that persisted distractors from earlier
tasks can inflate the denominator without numerator credit, making later-task
confusion a lower bound; the isolated-sequence function is the cleaner rate.
Staleness is reward-bearing in the documented fixture design, while the
distractor confusion metric is diagnostic-only.

The README describes a separate synthetic-world continuity comparison and
reports an increase from 0.062 to 0.188 under its named shared-store
condition. That is a source-reported number; the run, generated worlds, and
result artifact were not inspected or independently reproduced here. The
synthetic-arm module is a report implementation, not itself an executed
result.

The three-arm preregistration is a different protocol. Its beads / none /
builtin comparison uses paired work-ID goal outcomes for a two-session
memory-necessary task, with an unnecessary twin as a validity control. It
specifies a paired median and a 95% bootstrap interval at n=32 work IDs, a
minimum detectable effect of 0.20, and separate establish-leg mechanism
reporting. Do not merge its endpoint or limitations with the synthetic
ScriptedAgent evaluator merely because both discuss three arms.

The preregistration names unresolved or residual design limits. The sham arm
is deferred, so beads versus none cannot separate persistence value from
instruction or tool-salience effects. It reports a 1,338-word beads context
against 35 and 37 words for the controls, a large dosage difference. The
builtin comparator also has native-memory familiarity and an unclamped
establish leg. Its own text states that the experiment cannot prove the pin
held or close all durable channels: recognizer and hook limitations remain,
and /tmp, $HOME, and writable locations outside the wiped working directory
remain open.

The same preregistration records an earlier goal-leg tool-allowlist defect:
identical argv across arms still starved the bd arm because Bash was absent.
Its amendment requires equality with the declared allowlist, not merely
equality among arms. This is a useful falsifier of “matched configuration”
claims based only on arm-to-arm equality. These are statements in the
preregistration, not an independent audit of its implementation.

## Source-reported results and unknown runtime behaviour

The pinned README reports corpus sizes, test totals, prior real-corpus results,
and synthetic-world metrics. The preregistration reports earlier pilots,
including zero bd calls across 480 legs and zero writes in an E1 grid of 160
calls, then says a September 2026 amendment was registered before new paid
runs and that no paid session was run while making or validating that
amendment. These statements are evidence of what the project documents report.
They were not independently verified or rerun.

The preregistration's current comparison is prospective design, not a
completed result. Its latest amendment and validity gates do not establish
that paid runs, agent actions, pin precedence, transcript isolation, hook
behavior, or all leakage controls have been qualified. Comments and tests
describe intended mechanics; this audit executed neither.

Unknowns include the exact runtime behavior of the full orchestrator, which
policies are actually called by all consumers, whether emitted events meet
the prose privacy boundary, whether a full run satisfies its preregistered
gates, and what outcome any not-inspected benchmark artifact records.

## EMS implications for the first manual workbench

For a later, separately authorised manual study, the following candidate
inspection questions could refine the current dossier's synthetic-case plan.
No cases were generated or exercised here, and no agent runtime is needed for
these proposed questions.

| EMS case or question | Bounded manual counterexample | Falsifier for an EMS distinction |
| --- | --- | --- |
| V21: information cutoff | Hold a lesson constant; vary whether its trigger uses dispatch-time text or a held target's later trace error. Record what was available and what was actually shown by cutoff. | If the manual answer cannot distinguish availability from target-derived hindsight, trigger provenance is underspecified. |
| V23: verification boundary | Provide a diff or transcript with no test receipt; separately provide a failing test at the bound revision. | If either artifact alone is reported as tested success, material admission and verification have collapsed. |
| V20 / V09: revision and currentness | A record was useful or verified at revision A; ask about revision B without B-bound evidence. | If age or successful retrieval silently makes A current at B, applicability is underspecified. |
| V22: identity versus integrity | Reuse a deduplication ID while changing one declared payload value. | If identity alone is accepted as full-payload integrity, the event contract is underspecified. |
| V24: authority and abstention | Give an obsolete premise or a correct fact with no declared action authority. | If a correct answer implies permission, or every abstention is scored as failure, the outcome boundary is invalid. |
| New candidate: eligibility versus acceptance | Supply a closed, pre-cutoff record with relevant errors but no explicit resolution acceptance or test result. | If retrieval eligibility is interpreted as accepted or verified knowledge, the inference boundary fails. |

These are proposed manual inspection prompts, not additions to frozen vectors.
V20–V24 and the initial profile remain unfrozen under the dossier. A future
case needs an explicitly selected scope, input revisions, cutoff, policy,
expected observation or rejection, and a falsifier before it becomes a
machine-consumed vector.

The research difference hypothesis remains narrow: EMS is testing whether a
human-governed record can keep source authority, source revision, evidence
relation, policy revision, temporal scope, and replay failure inspectable
together. The inspected mem files establish useful work-linked retrieval,
trigger controls, operational memory-event capture, and candidate confidence
design. They do not show the complete EMS contract in these selected files,
and this bounded review cannot establish that the full repository lacks it.

The hypothesis would be weakened or falsified by a pinned source audit finding
an executable mem consumer that already binds canonical source revisions,
explicit policy revisions, valid-time scope, evidence relations, and
deterministic replay or rejection semantics with equivalent boundaries. It
would also fail the workbench's practical-value test if the fixed-evidence
manual B0 baseline answers the bounded questions with equal correctness and
less review burden.

## Limits and conclusion

This is an exact-ref, twelve-file static audit. It is not a repository-wide
search, a full benchmark review, or a test run. It makes no current-version
compatibility statement, no whole-corpus claim, no claim about all of
Stephanie Jarmak's work, and no independent reproduction of README or
preregistration results.

The strongest immediate EMS lesson is methodological: keep eligibility
separate from valid time, retrieval triggers separate from agent capability,
resolution material separate from executed verification, operational identity
separate from payload integrity, and synthetic harness mechanics separate
from agent utility. Apply these only as counterexamples for the first manual
synthetic workbench. No confidence field, age-decay policy, runtime behavior,
implementation direction, or research gate is adopted by this study.
