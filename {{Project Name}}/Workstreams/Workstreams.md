# Workstreams

Part of [[{{Project Name}}]]. A workstream owns a distinct outcome/contract and source set inside this vault. Several can run here; each has a note, while [[Current State]] holds live ownership and locks.

## Add one workstream

1. Choose a clear outcome name, not an agent/session name. Check whether an existing note already owns that boundary.
2. Copy [[Templates/Workstream Note]] to `Workstreams/<clear outcome name>.md` and change its title.
3. Fill its owner, purpose, observed state, boundaries, invariants, inputs/outputs, failure/permission behavior, acceptance/stop, next action and exact Key files. Say not applicable where appropriate. Do not invent a history or approval.
4. Add one row below pointing to that note. Keep the root project map pointing at this index; do not expand it for every workstream.
5. Before actual edits, follow [[Jobs/Onboard an Agent]] and claim files/locks on Current State. Creating a note does not itself claim the workstream. Resolve overlaps and dependency order before parallel work.

## Workstream index

| Workstream note | Outcome / boundary | Accountable owner |
| --- | --- | --- |

Use [[Proposed Plans/Proposed Plans]] for exact plan revisions and [[Daily Notes/Daily Notes]] for handoffs. Link these sources rather than creating competing boards or Latest pointers in each workstream.
