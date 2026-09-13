# Live GitHub state — 2026-09-12

Read-only GitHub API and CLI state was retrieved on 2026-09-12 between 12:08 and 12:10 UTC. Values below are observations at query time and may drift.

## Repository and coordination records

- The current `main` ref resolved to [`3bf173396a2c1ad91d53280c0dd6eac09b3daab7`](https://github.com/MarcoPorcellato/epistemic-memory-spec/commit/3bf173396a2c1ad91d53280c0dd6eac09b3daab7), commit timestamp `2026-09-05T19:14:08Z`.
- [PR #16](https://github.com/MarcoPorcellato/epistemic-memory-spec/pull/16) is **OPEN**, not draft. Head branch `research/track14-phase1-preregistration-draft` is `42d80ebd75320eb89ab618ac86754fb979c302a7`; base branch is `main`, and the pull request API reported base SHA `973f2ada3d4918d2f4ce1e71149972728356c278`. PR metadata `updated_at` is `2026-09-05T17:50:35Z`. The merge fields report `MERGEABLE` and `CLEAN`; this is not an approval or merge authorization.
- PR #16 has no reported check runs in the Checks API (`total_count: 0`) and no entries in its status-check rollup. The commit-status endpoint returned `state: pending` with `total_count: 0` and an empty statuses array. **No green check result is evidenced; zero checks is not PASS.**
- [Issue #15](https://github.com/MarcoPorcellato/epistemic-memory-spec/issues/15), “Track 14 Phase 1: review bounded CSP preregistration proposal,” is **OPEN**. Its GitHub `updatedAt` is `2026-09-04T06:09:48Z`.

## Release and tag

- GitHub reports one release in the returned release list: [Research Snapshot v0.0.0](https://github.com/MarcoPorcellato/epistemic-memory-spec/releases/tag/v0.0.0-research), tag `v0.0.0-research`, published `2026-09-03T01:07:05Z`, not draft, prerelease, and `isLatest: false`.
- The annotated tag resolves to commit `d1e18e864e4b4ba1ead5f8ccb9b82acc473d0fd2`. Tag name matches `CITATION.cff` version `0.0.0-research` in the inventoried source snapshot.
- GitHub’s `/releases/latest` endpoint returned HTTP 404. Thus there is no latest non-prerelease release reported by that endpoint; this does not negate the prerelease listed above.

## Repository rules

- The repository exposes one active ruleset, [`release-tags`](https://github.com/MarcoPorcellato/epistemic-memory-spec/rules/22156047), targeting tags matching `refs/tags/v*`. Its rules prohibit update, non-fast-forward update, and deletion.
- The classic branch-protection endpoint for `main` returned HTTP 404 with “Branch not protected.” No classic main-branch protection was returned. This query does not establish the absence of every possible organization-level policy.

## Limits and provenance

All observations came from read-only GitHub queries. Initial sandboxed requests could not connect to `api.github.com`; the same requested reads then succeeded with narrowly scoped network permission. The earlier failed reads recorded in the repository inventory are historical and superseded for current issue, PR, release, tag, and ruleset state by this report. No remote or local Git mutation was performed for this report. Current state after the retrieval window remains unverified.
