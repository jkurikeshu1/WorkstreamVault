# Workstream Routing

Part of [[Reference/Reference]]. One workstream has one stable identity and one canonical context note. Use this route for continuing work, including with a new agent. Intake follows [[Jobs/Index an Existing Workstream]]; ongoing saves follow [[Jobs/Update the Vault]].

## Identity and the local record

The workstream note's front matter contains `workstream_id` and `canonical_vault_id`; the latter must equal [project-context.json](../project-context.json)'s `projectId`. Its index row uses the same workstream ID. Assign IDs only during real setup/intake, keep them stable across renames/moves, and reject duplicate IDs pointing at different active notes. Blank template IDs are intentionally null.

Use the package README's conventional per-user `workstream-vaults/setup.json` on the **actual target computer**: macOS Application Support, Windows LocalApplicationData, or the configured Linux configuration directory. Resolve it through native tools; this template ships no populated record. Extend an existing valid record without dropping unrelated fields/vaults. Preserve malformed/conflicting records and report registration pending rather than overwriting them. For a new record, use `schemaVersion: 1` and retain the setup/template fields from the README.

Use these documented discovery fields on both Mac and Windows. They are ordinary JSON data, not a runtime service schema:

| Field | Meaning |
| --- | --- |
| `vaults[]` | Known vaults; each has `vaultId` (the configured `projectId`), `name`, and `canonicalPath` (verified absolute local folder). |
| `workstreams[]` | Workstream discovery entries, with the fields below. |
| `workstreams[].workstreamId` | Stable ID matching the note and workstream index. |
| `workstreams[].vaultId` | ID of the canonical vault in `vaults[]`. |
| `workstreams[].notePath` | Vault-relative Markdown path using `/` on both operating systems; never an absolute or escaping path. |
| `workstreams[].aliases` | Explicitly assigned names for discovery; names are not globally unique identity. |
| `workstreams[].sourceRoots` | Verified absolute local source folders, within the supplied scope. Overlapping/shared roots require an explicit workstream choice. |
| `workstreams[].entryPoints[]` | Each entry has absolute local `path`, `status` (`verified` or `pending`), and `lastVerifiedAt` (actual UTC timestamp, or null when unverified). A verified entry contains the installed pointer and has passed readback/ID resolution. |

Save paths with a JSON serializer (UTF-8); Windows backslashes must be escaped correctly. Keep absolute machine paths **only in the user's local record or their private working configuration**, never in the distributed template or a publicly tracked entry pointer. Keep note bodies, transcripts, credentials and account data out of this registry. Verify/read back updates before reporting registration saved. A local record is a discovery hint, not authority or evidence that a client automatically loads it.

## Entry from a work folder or repository

During authorized indexing, merge [[Templates/Workstream Entry Pointer]] into the actual work folder's **existing** agent-entry instructions, using the IDs and vault-relative note path. Use the client's existing supported entry file when known (for example its actual repository AGENTS.md or CLAUDE.md). Preserve existing instructions; do not replace an entry contract, invent universal autoload behavior or install a new plugin to force it.

Only change an entry file within the current write scope. If a separate repository requires a branch/review, follow that contract. Otherwise provide the prepared pointer and report installation pending. A pointer must be placed where future agents actually begin reading, not only hidden in the vault. A shared repository pointer uses stable IDs; each coworker resolves those IDs through their own local record and authorized vault access.

The first agent that installs it verifies the saved pointer and target IDs. A new agent must still read it. A client that does not load entry instructions needs an explicit request to read them. A path alone, a local record alone or this README alone cannot intercept all agent activity.

## Resolve before dependent work

1. Read the current assignment and the entry pointer, when present. An explicit vault/workstream ID or verified note path is the strongest route; confirm any change of canonical destination with the owner instead of creating a competing copy.
2. Resolve the pointer through the current user's local record. If entering from the package without a pointer, use an explicit assignment or a verified source-root match. Do not infer identity from a similar title, recent date, chat memory or an ambiguous alias. Match complete path components, not raw string prefixes. Canonicalize through the target OS, check redirects/symlinks, and require a unique mapping; one repository can contain several workstreams.
3. Verify access to the actual vault; confirm `projectId`, workstream front matter, note path within the vault, index row and source boundary. Repository identity/checkout and its actual instructions require their own verification. A matching ID does not grant filesystem or task authority.
4. If missing, inaccessible, conflicting or ambiguous, ask only for the missing canonical vault path or workstream choice. Do not scan the whole computer, silently substitute another vault, create a duplicate or replay first-time setup. Resolve the gap before work that depends on this context. Do not describe stale pointers as a completed route.
5. Read the vault's entry contract and map, [[Current State]], guardrails, the routed workstream and complete Key files, exact plan/approval if relevant, and matching Job. Check current authority, owner, stop and overlaps before editing. Historical data does not start work.

## Keep subsequent work indexed

For authorized work on this workstream, maintaining its useful context is part of completion: update the same canonical workstream note with changed facts/Key files and source versions, update actual coordination/decisions where they belong, and add one meaningful dated handoff with outcome, checks, gaps and next owner. Use [[Jobs/Update the Vault]]. Include newly used sources in the coverage ledger. Keep the selected history mode: link by default; copy only specifically selected, permitted history. Do not copy every future chat automatically.

Claims, branches, new sessions, renamed source folders and different agent brands do not create new workstream identities. Do not keep a competing agent-specific current-state notebook. Reuse existing source IDs and update only changes. For read-only questions/reviews, route through the same context but report in chat; no automatic history append or claim. If the user narrows write scope, or vault access is unavailable, report the unsaved context update explicitly and provide a handoff rather than pretending it was indexed.

After an authorized vault move or entry-path change, update the local discovery pointers, preserve stable IDs and verify every affected installed entry point. Until repaired, report the route pending. Do not relocate a working vault merely to repair discovery.

These rules direct cooperating agents that can read the entry instructions and vault. They supply no background monitoring, universal provider memory or enforcement. Work performed elsewhere without reading this route is not automatically indexed.
