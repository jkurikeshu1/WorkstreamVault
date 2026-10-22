# Shared Context

Part of [[Reference/Reference]]. The aim is accurate continuity with less repeated explanation and reading. This is documentation, not a memory service, recorder or permissions engine.

## Identity and required context

[project-context.json](../project-context.json) declares this vault's identity and current routes. [context-profile.json](../context-profile.json) is an optional source catalog rooted here. It does not include an external repository's instructions/code, prove automatic agent loading or replace actual task dependencies. No consumer is included. Required sources must be read completely; missing, denied, ambiguous or oversized context blocks dependent work.

Tags prioritize optional context only. Planning explicitly requires `plans` and `plan-review`; relevant implementation/maintenance requires `maintenance` and `parallel`; setup requires `setup` and `plan-review`. The actual workstream, exact plan and Key files remain separate required reads. A link or metadata entry is not access permission.

Baseline routing uses `routing`; existing-work intake explicitly requires `index-workstream` and its `routing`/`maintenance` dependencies. [[Reference/Workstream Routing]] resolves stable IDs and canonical notes before dependent work. It also directs future authorized work to update that same context at completion.

## One place for each kind of context

| Information | Canonical place |
| --- | --- |
| Current objective, authority, stop, owner and next action | [[Current State]] |
| Workstream facts, boundaries and source routes | Relevant workstream note and actual source detail |
| Prior-context coverage, provenance and gaps | Workstream source-coverage table or its linked ledger |
| Workstream discovery | Stable IDs plus local record/source-folder pointers through [[Reference/Workstream Routing]]; never task authority |
| Proposal revision/approval | [[Proposed Plans/Proposed Plans]] and exact living approval record/frozen revision |
| Settled cross-cutting choice | [[Reference/Decision Log]] and affected rule note |
| Meaningful result, checks, unfinished work and next owner | Dated [[Daily Notes/Daily Notes]] heading plus artifacts |

Save only the useful delta at ordinary work/handoff boundaries. Read-only tasks finish in chat. Exclude raw transcripts by default, private operational stores and unrelated project context. The narrow exception is explicitly selected, permitted, sanitized project history under [[Jobs/Index an Existing Workstream]]'s optional history-copy mode. Those copies remain historical evidence outside baseline reads, with provenance; they are not policy, approvals or automatic future-chat collection. Project preferences do not become global policy by inference.

## Corrections and handoffs

- **Received:** understood, not yet saved/applied.
- **Saved with manual readback:** an authorized canonical edit was written and read back; compare the expected base and reconcile concurrent edits. An uncertain save remains unsaved/unknown.
- **Applied with evidence:** the dependent output used the corrected source and passed a relevant check, with source/version and output reference. An old passing check or acknowledgment is insufficient.

Changed context invalidates affected results; reread/revalidate them. Keep ambiguous feedback unresolved and inferred lessons labeled candidates. A normal handoff records stable task/dated heading, scope/acceptance/stop, result/checks, current source/version, unresolved work, next owner and remaining authority. Old, quoted or consumed authority never starts a successor automatically.

If asked to stop using a fact, update authorized current routes and explain the effect. Backups/provider copies may remain; logical forgetting is not secure erasure. Do not prune history destructively without an assignment. Preserve unknown measurements as unknown, not zero or an estimate derived from file size. No per-turn benchmark form or background collector is required.
