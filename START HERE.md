# Start here

This package contains a blank Obsidian vault and setup instructions for your own project. It teaches where current truth lives, how people and agents find the right sources, how work is owned, and how proposals become approved work.

**For agent-led setup, start with [README.md](README.md).** Give the agent the extracted package folder and ask it to read that file and set up the vault; [AGENTS.md](AGENTS.md) routes it through [SETUP.md](SETUP.md). The agent can handle the checklist and configuration with neutral defaults. A path alone is not a universal automatic-start mechanism across all agent tools.

The `{{Project Name}}` folder is the vault. It works as plain folders, Markdown and JSON. **Obsidian is optional**; no download or installation is needed. A file-capable agent can read the same entry contracts and maintain the notes without it. This guide also supports manual setup and explains every configuration field.

## Use the guide for your computer

- **Windows:** follow [WINDOWS.md](WINDOWS.md). Use Windows file tools or PowerShell; no Mac commands, WSL or Git Bash are needed.
- **Mac:** follow [MACOS.md](MACOS.md). Its shell examples and Library/Application Support location are macOS-only.

Both platforms use the same action menu, name/save-location questions, complete template, metadata, setup-record fields, workstream/onboarding checks and completion report. Only native paths, registry location and file-operation syntax differ. Determine the computer where files will actually be saved before choosing a guide.

## Setup checklist

1. **Choose the final destination, then copy the entire inner template** there, including `.obsidian`; preserve the original blank template. The agent asks for the name and final save location in README's order. Check for existing files first; do not merge over another vault or nest the name twice. Keep an existing canonical repository or vault where it already belongs. A code repository is optional.
2. **Set the project name and owner.** Rename the destination's `{{Project Name}}.md` map to the selected valid project filename. Use the selected OS guide's filename rules, avoid case-only duplicate notes, and keep the resulting map name and its routes consistent. Do not treat a Windows drive colon as part of a filename.
3. **Replace placeholders in text and filenames.** Search all Markdown and JSON files for `{{...}}`. Set `{{Project Name}}`, `{{Owner}}`, `{{Vault Path}}` and, if applicable, `{{Repo Path}}`. `{{Vault Path}}` means the absolute path of the inner folder you just copied. There is no automatic placeholder replacement. Leave `{{date:YYYY-MM-DD}}` only in `Templates/Daily Note.md`; Obsidian's built-in Templates command expands it when used; a folder-only agent replaces it with the actual date when creating a daily note. The JSON files contain empty identity strings as well as placeholders; complete the fields listed below.
4. **Set the JSON identity and local rules.** Choose a stable project ID, such as `project-notes`, and your own initial revision, such as `local-1`. Keep `project-context.json.contextRevision` and `context-profile.json.policyVersion` equal. Review the conventions, guardrails and Jobs with the named owner. These are proposed starting rules for your adoption, not an inherited approval.
5. **Handle the optional repository.** If there is no repository, leave `repository.root` empty and `expectedOrigin` null, and replace every `{{Repo Path}}` placeholder with `Not applicable — no repository`. Keep `gitRepository` false for a non-Git vault. If there is a repository, set its absolute path, verify its actual instructions separately and name its base branch and meaningful checks in Conventions. Do not create an empty repository just for this vault.
6. **Choose how to view the files.** With a text editor or file-capable agent, open the renamed inner folder and begin at its project-name map and AGENTS.md. Resolve wikilinks to the corresponding Markdown files. If you prefer Obsidian, open that same inner folder as a vault. Its `.obsidian` settings enable built-in template/daily-note convenience features only, with community plugins disabled. Obsidian, a workspace, themes and community plugins are not required.
7. **Create your first workstream.** Copy `Templates/Workstream Note.md` to `Workstreams/<clear outcome name>.md`. Replace its title and prompts with your real outcome, owner, boundary, sources/Key files, definition of done and next action. Distinguish observed facts from plans. Add one link row in `Workstreams/Workstreams.md`. Keep the root map pointing at the index rather than adding every workstream there. A workstream note does not automatically claim work.
8. **Run one agent through onboarding.** Paste the briefing from `ONBOARD.md`, fill in the new vault path and first workstream note, and ask for read-only onboarding. The agent should identify sources, boundaries, the matching Job, authority/stop, missing context and proposal status. It should find no existing claim, lock or approval in the blank tables. It must report in chat without editing or claiming. Supply real sources if it cannot access them.
9. **Begin actual work only with a clear assignment.** For authorized edits, use the board/check-in and matching Job. Create a dated handoff only after a meaningful change. Save real plans and decisions when they exist. Do not prefill history to make the vault look active.

A successful first run means the agent found the right workstream and sources, understood what it may do, and stopped at the requested boundary. Merely finding the JSON files is not proof that an agent or tool loaded or enforced them.

## What to set in project-context.json

JSON does not permit comments. This table supplies the field explanations. Vault-relative routes use `/` on Windows and Mac and are resolved against the actual root through native file/path tools. Absolute machine paths use the target OS's syntax. Update JSON through a parser/serializer so Windows backslashes are escaped correctly; do not paste them into raw JSON strings. Empty identity fields intentionally prevent the starter from claiming to be a configured project.

| Field | Action / meaning |
| --- | --- |
| `schemaVersion` | Keep `1` for this documented layout. This is not certification against a particular tool schema. |
| `kind` | Keep `declarative-shared-context-guidance`: information and routing, not enforcement. |
| `projectId` | **Set** a unique stable identifier; match the profile and every source entry. |
| `contextRevision` | **Set** your own revision after reviewing the local rules; match profile `policyVersion`. Revise deliberately when the contract changes. |
| `protocolRevision` | Keep `2` as this scaffold's protocol declaration. Verify support with any consumer; the declaration grants no tool capability. |
| `canonicalRoot` | Keep `.` when this file sits at the vault root. |
| `bootstrapPath`, `contractPath` | **Verify** the renamed project map path and `AGENTS.md`. |
| `projectOwner`, `contextOwner` | **Set** the human approving scope and the person maintaining current context; they can be the same person. |
| `gitRepository` | **Verify** whether the vault itself is Git-managed. This does not describe the separate repository. Default false. |
| `repository.root` | **Set** absolute `{{Repo Path}}` if a repository exists; otherwise keep empty. |
| `repository.expectedOrigin` | **Set** the actual verified remote URL when relevant; otherwise null. A URL is not permission to publish. |
| `repository.entryContract` | **Verify** the repository's actual instruction filename; empty only if no repository exists. |
| `repository.verifyAssignedWorktree` | Keep true for repository work; verify actual branch and existing edits at pickup. |
| `repository.notIncludedInVaultOnlyPack` | Keep true; external repository context requires separate reads. |
| `currentSourcePaths` | **Verify/update** every entry after renames; list current entry/rule sources, not history or private data. |
| `routing.scope` | **Set** the exact project boundary; avoid broad cross-project authority. |
| `routing.requiredSourcesNeverTruncated` | Keep true; missing/oversized required context blocks dependent work. |
| `routing.explicitRequiredDependenciesMustBeAdmitted` | Keep true; required dependencies cannot become optional to fit a budget. |
| `routing.denyByDefault` | **Review** restricted categories for your project. These strings document boundaries; filesystem permissions must enforce access separately. |
| `execution.mode` | Default means stop at the assigned boundary. A broader mode needs explicit human direction and a finite target. |
| `execution.status`, `execution.scope`, `execution.stop` | Leave unassigned/empty until real work is assigned; then record current status, authorized scope and stop. Do not copy old authority. |
| `capabilities.declarativeOnly` | Keep true. |
| `capabilities.contextProfile` | Keep `context-profile.json` unless renamed. |
| `capabilities.contextProfileStatus` | Starts `unconfigured`; change only to an accurate, evidenced local status. |
| `capabilities.providerQualification` | Starts `not_assessed`; a manual onboarding read does not qualify automatic provider entry. |
| `capabilities.globalRollout`, `liveRecorder`, `automaticGrantEnforcement`, `durableJournalAcknowledgment` | Keep false; this starter supplies none of these capabilities. |
| `limits` | Keep the plain-language boundary or clarify it without claiming enforcement. |

## What to set in context-profile.json

This is an optional source catalog. Manual onboarding works without a profile consumer. No consumer, scheduler, recorder, request file, credentials or installation is included. Before using a tool, verify its accepted schema and behavior rather than assuming this scaffold is compatible.

| Field | Action / meaning |
| --- | --- |
| `schemaVersion` | Keep `1` for this layout; check compatibility with any later consumer. |
| `operatorReviewed` | Starts false. Set true only after the human owner reviews the configured catalog. This is not approval to implement work. |
| `projectId`, `policyVersion` | **Set** to the project identity and local context revision above. |
| `approvedRevision` | Starts null; leave null unless the owner explicitly records a reviewed local profile revision. Never use it as task authorization. |
| `orientation.goal`, `user`, `architecture`, `rationale` | **Set** the outcome, intended readers, location/ownership model and why these sources are useful. Use project context only. |
| `orientation.constraints` | **Review** the generic boundary statements; add only current project requirements. |
| `sources[*].id` | Stable unique source ID. Keep existing IDs or update all dependencies and instructions when renaming. |
| `sources[*].path` | **Verify** the actual vault-relative file, including the renamed map. Add workstream-specific sources when needed. External repo files stay separate. |
| `sources[*].projectId` | **Set** every entry to the same local project ID. |
| `sources[*].roles` | **Review** intended readers; these are selection hints, not permissions. |
| `sources[*].classification`, `sensitivity`, `kind` | **Review** current/history, handling boundary, and policy/background/evidence role. Do not label history current. |
| `sources[*].status` | Starts `unreviewed`; record an accurate owner-reviewed status only after review. A source label does not approve its proposals. |
| `sources[*].required` | **Review** the baseline required reads; all actual task dependencies are required even if absent here. |
| `sources[*].tags` | Optional relevance hints; a tag never guarantees admission. |
| `sources[*].dependencies` | Source IDs that must accompany this source. `plans` and `setup` depend on `plan-review`. |
| `sources[*].revision` | Starts null. Supply genuine source-version evidence if a later tool requires it; never invent a hash. |
| `limits.maxFileBytes`, `maxReadBytes`, `maxPackBytes`, `optionalBytes` | Advisory ceilings for one file, total reading, assembled orientation and optional material. Review for your tool; no consumer enforces them here. A required-source overflow must block or be resolved, never truncate silently. |

For planning explicitly require source IDs `plans` and its dependency `plan-review`; read the linked exact revision and workstream separately. For implementation/maintenance explicitly require `maintenance`, `parallel` and actual task sources. For setup explicitly require `setup` and `plan-review`. Tags alone are insufficient. Required reads outside an optional pack still have to happen completely.

## What stays empty until real work exists

Current State's claim and lock tables, the proposed-plan registry, the decision log and daily-note index start empty. Create `Proposed Plans/Revisions/` when saving the first plan snapshot. Create `Daily Notes/YYYY-MM-DD.md` at a meaningful authorized handoff. Add shared-state locks only for resources people actually share. Architecture has a small routing/guardrail scaffold; add real subsystem contracts when needed.

The operating cycle is: read → establish authority → claim when editing → check in → do the bounded work → verify → update the canonical note → hand off and release. For architectural plans, agent entry, the plan Job and the template all require the ambiguity table before implementation readiness.

## Included and intentionally empty

The package contains a root README and agent entry, separate Windows/Mac guides, an agent-led setup procedure, this field guide, inner-vault entry and onboarding instructions, an empty coordination board, the required Jobs, workstream and plan templates, reference notes, unconfigured JSON catalogs, and minimal built-in Obsidian settings.

Identity fields, approvals, claims, locks, plan registries, decisions and dated history remain empty until your own work needs them. No community plugins, application code, accounts or runtime services are included.
