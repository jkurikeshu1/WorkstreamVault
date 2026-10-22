# Parallel Workflow

Part of [[Jobs/Jobs]]. Parallel work is useful when ownership stays clear.

Read-only reviews make no claims. Authorized non-Git vault documentation claims exact notes and follows [[Jobs/Update the Vault]] without touching a separate code worktree. Repository edits use an owned branch/worktree. A proposal or old owner name is not current authority.

## Authorized work loop

1. Resolve exact authority: approved plan revision or direct narrow assignment. State acceptance and stop.
2. Reread [[Current State]]. Claim a non-overlapping workstream/file set. One live owner per overlap.
3. Claim only necessary shared-state locks. One holder per actual shared resource; a lock grants no permission.
4. Isolate repository work in its own branch/worktree based on the verified project base branch. For non-code deliverables, isolate overlapping files or serialize them.
5. Verify runtime/data/account isolation when relevant. Different ports alone do not isolate data, credentials, databases or hardware. If actual shared state cannot be isolated, serialize it under its lock.
6. Post the truthful check-in, do the smallest assigned increment and verify the affected deliverable.
7. Update current truth and one handoff. Submit for review through [[Jobs/Review a Change]]. State exact next owner and checkpoint.
8. Release claims/locks when the owned activity is complete or handed over; never imply unfinished work was delivered. Reconcile remaining repository work after authorized integration.

## Choose locks from reality

Examples of resource categories are shared contracts, migration order, a shared runtime/dataset, account configuration or physical equipment. These are examples, not preclaimed locks or mandatory infrastructure. Add a lock to Current State only with a concrete resource, holder, scope and checkpoint. Never store secret values there.

## Collision handling

Stop overlapping writes. Report the exact files/resource and coordinate ownership with the owner through an authorized channel; otherwise leave a clear local blocker for human resolution. Split on a real interface, sequence the work, or hand ownership to one person. Record compatibility/integration order and resume only when ownership is unambiguous. Continue independent authorized work where possible. Preserve concurrent edits; synchronized Markdown is not an atomic locking system.
