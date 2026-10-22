# Review a Change

Part of [[Jobs/Jobs]]. Review the concrete result and its evidence against the exact assignment. Read-only review reports in chat; saving or running checks requires the assignment to include them.

## Review packet

The implementer provides authority/exact revision, file/workstream and workspace identity, claims/locks, before/after behavior, acceptance evidence, checks/results, compatibility/recovery notes, affected documentation, known limits and proposed next owner. Include actual preview/deliverable references. Do not claim tests, integration or installation that did not happen.

## Reviewer checks

Verify scope and actual sources, correctness, privacy, untrusted-input handling, concurrency/failure behavior and usability as applicable. Use proportionate checks: source truth, links and saved readback for documentation; meaningful deliverable checks for other work; relevant repository tests and the affected flow for code when authorized. Use isolated data and avoid unnecessary access to private records. Check that current state, workstream contracts, decisions and handoff reflect what actually happened.

For substantial repository implementation, obtain independent review and configured CI/PR gates before integration. A configured remote is not proof of working CI or publication authority. For other work use the owner's applicable review/acceptance process. Passing checks alone do not approve a plan or authorize merge, release, sharing or external delivery.

## After authorized acceptance/delivery

Record the actual stage: locally prepared, reviewed, merged, released or accepted, with evidence where applicable. Mark a plan Implemented only after its authorized delivery is complete, verified and distilled into current sources. Preserve the exact approval and artifact references. Update current truth, append one handoff and release/transfer claims and locks. Identify unresolved work, next owner and remaining authority. Reconcile remaining branches after integration only when a repository is involved.
