# Conventions & Dev Workflow

Part of [[Reference/Reference]] and [[Jobs/Jobs]]. The owner reviews these starting conventions during setup.

## Locations and names

- Vault: `{{Vault Path}}`
- Separate repository, if any: `{{Repo Path}}`
- Project and approving human: {{Project Name}} / {{Owner}}
- Workstreams: one clear outcome/contract per named note under `Workstreams/`; add it to that index, not the root map.
- Daily notes: `Daily Notes/YYYY-MM-DD.md`, one file per day, newest-first one-line session index.
- Plans: stable living note plus immutable `Proposed Plans/Revisions/<Plan Name> — rN.md` snapshots created only for real formal revisions.
- Timestamps include timezone. Stable IDs and filenames should not depend on the current agent. Repair all inbound links on a rename.

## Folder-only workflow

Obsidian is optional. Open the vault folder in a text editor or give a file-capable agent access to it. Read the project map and AGENTS.md first. Resolve a wikilink by its vault-relative path or unique Markdown filename; if ambiguous, report the conflict. When creating a daily note without a template app, substitute the actual date and time/timezone rather than leaving the date token in a saved handoff.

Work is indexed through deliberate maintenance of the Workstreams and Daily Notes indexes and current canonical notes while authorized work is done. There is no watcher, automatic transcript capture or import of work outside this workflow.

## Windows and Mac: same workflow, native file operations

The map, entry contract, workstreams, claims/locks, plans, ambiguity review, verification and handoffs have the same roles on Windows and macOS. Select the actual destination computer, independently of the chat/model host.

| Target | File handling | Local setup-record location when system setup uses one |
| --- | --- | --- |
| Windows | Native file APIs or PowerShell, with literal-path handling and Windows path/name validation. Unix utilities, WSL and Git Bash are not required. | The execution user's local application-data directory, then `workstream-vaults` and `setup.json`. |
| macOS | Native Mac file APIs or appropriately quoted commands in the actual Mac shell. Mac shell examples belong to Mac only. | The execution user's Library, then Application Support, `workstream-vaults` and `setup.json`. |

Preserve all files including `.obsidian`, use UTF-8 without unintended encoding/BOM changes, and update JSON with a serializer. Keep vault-relative catalog/link routes written with `/`; resolve them with the native path library. Absolute machine paths use that target's syntax. Avoid nonportable filenames and notes that differ only by case. A Windows path in a JSON value must survive parse/write/readback with the same meaning, including its spaces/backslashes. Do not use default shell redirection to rewrite JSON when its encoding is uncertain.

Remote/cloud agents need actual access to the selected target; a typed path is not access. Report a missing capability instead of creating files on another machine or claiming Windows verification from a Mac-only check. These rules add no watcher, installer or automatic enforcement.

## Repository workflow, only if a repository exists

Verify the actual checkout, remote identity, instructions, base branch and existing edits. Record project-specific choices below during setup; leave them not applicable when there is no repository. Use an owned branch/worktree for repository changes; never implement directly on the protected base branch. Do not stage others' changes.

Meaningful implementation needs applicable checks, independent review and the project's configured integration gates. A workflow step mentioning push/PR/merge does not grant publication authority. Make the result reviewable, then follow the owner's actual delivery authority. Without configured gates do not pretend the policy is operating.

| Local choice | Set during setup if relevant |
| --- | --- |
| Protected base branch | Not configured |
| Branch naming | Not configured |
| Required checks | Not configured; choose checks for actual behavior and risk |
| Independent review / CI / delivery route | Not configured |

## State and data safety

Read [[Jobs/Parallel Workflow]]. Separate file ownership and code workspaces from shared runtime/data/account/hardware state. Verify isolation or serialize necessary shared resources. Different ports are not enough. Real user data is not a fixture by default. Do not seed, migrate or delete a data target merely to orient or test documentation.

## Verification by assignment

| Assignment | Appropriate evidence |
| --- | --- |
| Read-only question/review | Source-linked findings in chat; no automatic tests or writes |
| Vault prose | Expected-base/preservation, readback, source truth and links |
| Other deliverable | Finite acceptance against the real output |
| Application code/configuration | Relevant repository checks and the actual affected user flow, with isolated safe inputs |

Use [[Jobs/Update the Vault]] after meaningful authorized work. Keep exhaustive detail in its real source. A plan can remain detailed while under review; completed truth is distilled into current notes.
