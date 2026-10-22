# Set up this vault

This is the complete agent procedure for an authorized setup of the supplied starter. Read README.md and package AGENTS.md first. Use ordinary file operations; no application, package manager, installer, account or network access is required.

## 0. Select the actual target OS

Determine where the files will be saved. Read [WINDOWS.md](WINDOWS.md) for a Windows target or [MACOS.md](MACOS.md) for a Mac target before file operations. Use the same full procedure below on either OS; the native path/file handling changes, not the features or required evidence. A remote agent must verify access to that actual target. Do not require Windows users to install a Unix shell, WSL or Git Bash, or execute a macOS-only command there.

Use native file tools when possible. Preserve all template files including `.obsidian`, UTF-8 text, vault-relative `/` routes and Unicode names. Parse/update/serialize JSON instead of inserting raw machine paths; Windows absolute paths need correct backslash escaping in JSON. Validate path/name rules on the target OS, and avoid case-only duplicate notes on either platform.

## 1. Verify scope and destination

Confirm that the current user wants setup, rather than a read-only explanation. Verify access to this package and its instructions. Follow README's exact **What do you want to name your Vault?** then **Where would you like your Vault saved?** sequence, with **Enter a valid file path.** as the save hint, unless those answers were already explicitly supplied. Use the chosen final destination and applicable local location instructions; do not append the name twice or silently choose another directory. Do not relocate existing projects. Missing filesystem access is a blocker for writes, not permission to create on another computer.

Verify the packaged blank template. On an existing-work request or rerun, use the actual verified assigned vault; do not reset it or duplicate setup handoffs. On a creation request, preserve the blank template and create a separate destination copy. A missing old setup record does not block creation on either OS. An existing empty destination may be used when intended; a nonempty/conflicting target must be resolved before writes. Never merge over an existing vault.

## 2. Use known details or neutral defaults

Use project details and constraints the user already supplied. Missing cosmetic choices do not require another permission question. Otherwise use:

| Choice | Neutral default |
| --- | --- |
| Project name | The user's answer to the required name question |
| Human project owner | Project owner — the user requesting setup |
| Context maintainer | Same owner role |
| Local project ID | Derive a stable ID from the supplied name; avoid collisions |
| Initial context/policy revision | local-1 |
| Purpose | Coordinate the project work the user explicitly assigns |
| Repository | None unless the user supplied one |
| Note application | Folder/text-editor workflow; Obsidian optional |

Report other defaults at completion. Never invent a personal name, organization, project history, approval or real work objective. Validate generated names on the target OS using the selected guide; explain a needed safe filename/display-name distinction instead of silently changing the user's project identity. Genuine conflicts over authority, access or existing content require resolution; neutral defaults do not replace the required name/save answers or resolve those conflicts.

## 3. Configure the destination copy

Use native file operations to copy the **entire** blank starter to the validated destination, including `.obsidian`. Retain the original starter for later vaults. Configure only that destination. Preserve expected starting content and compare current bytes before overwriting. The blank destination has no active claims; perform this initial package-authorized setup as one writer. If another setup agent is present, stop overlapping writes and resolve ownership first.

1. Use the user-selected final folder exactly; name its matching map note from the chosen valid project filename. Do not nest another same-named folder inside the destination. On rerun, retain the existing configured name/location unless a rename is explicitly requested.
2. Replace `{{Project Name}}`, `{{Owner}}`, `{{Vault Path}}` and `{{Repo Path}}` in Markdown and update JSON values through a serializer. The vault path is its actual resolved location on this user's machine, not a path inherited from any package. Preserve the daily-note template's `{{date:YYYY-MM-DD}}` token. Keep Markdown/JSON as UTF-8 without introducing an incompatible encoding or BOM through default shell redirection.
3. Without a repository, replace visible repository placeholders with `Not applicable — no repository`; leave JSON repository.root empty and expectedOrigin null, set entryContract empty, and mark repository workflow choices not applicable. Do not initialize Git.
4. With an explicitly supplied repository, verify that source and its instructions read-only, set its actual root/origin/entry contract and applicable workflow details. Do not change the checkout or run application checks merely for vault setup.
5. Set project-context.json projectId, contextRevision, projectOwner and contextOwner. Set routing.scope to this project's assigned work only. Verify canonicalRoot, bootstrapPath, contractPath and currentSourcePaths. gitRepository describes the vault itself; keep it false unless this vault actually is Git-managed.
6. Set context-profile.json projectId and policyVersion to match. Set every source's projectId. Fill orientation goal, intended project readers, folder/optional-repository architecture and rationale. Verify all source paths, IDs and dependencies against renamed files.
7. Keep execution unassigned until the setup/work assignment is recorded accurately; do not manufacture an ongoing execution grant. Keep automatic/recorder/enforcement/provider capability claims false or unassessed. Keep operatorReviewed false, approvedRevision null, and source status unreviewed unless the actual human independently reviewed them. Agent setup verification is not human approval.

The complete field reference is in START HERE.md. The profile is optional routing data, not a required runtime or proof of schema compatibility with a tool.

## 4. Read and adopt the operating route for this assignment

Read the renamed map, inner AGENTS.md, Current State, Architecture/Architecture Guardrails, Jobs/Onboard an Agent, Jobs/Create or Adapt a Project Vault, Jobs/Update the Vault, Reference/Conventions & Dev Workflow and Reference/Shared Context. Follow their required dependencies completely. Read the plan Job and template to verify the architecture-ambiguity framework is connected; do not create a proposed plan just to set up the vault.

Now establish the scoped setup claim/necessary check-in under the configured contract before further operational note edits. A shared-state lock is unnecessary unless an actual shared resource needs one. Do not change a separate code repository or launch its runtime. Treat new project-specific policy choices as requiring the owner's actual direction; setup does not mark them approved.

## 5. Create the first appropriate workstream

If the user supplied real work, create its clearly named note from Templates/Workstream Note.md and fill only known facts. Record unknowns honestly. If no work was supplied, create **Vault Setup** for this actual setup activity: configure entry/routing, verify the scaffold, and hand back a ready project workspace. This is actual setup work, not a fictional business project.

Include purpose, accountable owner role, observed state, boundaries, relevant invariants, actual inputs/outputs, failure/permission behavior, finite acceptance/stop, next action and exact Key files. Add its row to Workstreams/Workstreams.md; keep the root map linking only the Workstreams index. Do not invent plans, approvals, decisions, prior sessions or results.

For the setup workstream, acceptance is successful identity/link/JSON and entry-route checks. Its stop is returning the verified vault and waiting for the user's first real project assignment. Update Current State only with actual setup status; keep claims/locks separate from workstream descriptions.

## 6. Verify the configured files

- Parse both JSON documents; project IDs and local revision/policy values agree.
- Resolve every currentSourcePaths and catalog path; source IDs and dependencies exist. Paths outside the optional vault-rooted catalog remain separate required reads.
- Check all local note links after renaming, including the map, Jobs, workstreams, references and templates. Standard wikilinks refer to Markdown notes; resolve them as file routes even without Obsidian.
- Confirm the same complete scaffold on Windows and Mac, including `.obsidian` settings; validate target-native paths, generated filename safety, UTF-8 text and round-tripping of machine paths through the JSON serializer.
- Ensure no setup identity/path placeholders remain in operational files. The built-in date token may remain only in the Daily Note template. Package guide examples can retain generic placeholders.
- Confirm entry contract, plan Job and proposal template all require decision boundary, plausible agent drift, explicit direction/section, owner/verification and resolved/deferred/needs-decision status. There must be no consequential unresolved choice inside a claimed implementation-ready architectural increment.
- Confirm no fake claims, locked resources, history, approval, credentials or application configuration were added. Human-review flags stay honest.
- Run a read-only onboarding pass yourself against the actual configured vault: identify its owner/purpose, workstream boundary/Key files, task Job, current authority/stop and missing dependencies. Do not claim that this self-check is independent review or automatic provider qualification.

If Obsidian is installed and the user wants it, explain opening the configured folder as a vault. Do not require or automatically install it. A missing Obsidian installation is not a setup blocker. The same files work with a text editor and a file-capable agent; Obsidian-specific date insertion and clickable wikilinks are conveniences.

## 7. Hand off and stop

Record one actual dated setup handoff using the configured Daily Note template, with real checks, limitations, exact next action and owner. Release the setup claim; leave no invented active lock. On a rerun do not append another setup history entry unless a meaningful authorized change actually occurred.

Report the canonical vault location, selected project/defaults, verification results, any unresolved access/configuration, and how to give the agent its first real task. Explicitly distinguish ready documents from automatic tooling. Stop at the setup boundary; do not start unrelated project implementation.

For later project work, the package agent contract resolves the actual assigned vault from verified pointers and follows its own entry contract. The same Windows/Mac operating-system distinction continues for file operations. The agent maintains workstreams, current truth and meaningful handoffs through the existing Jobs as it performs authorized work. This is an instruction-driven working practice, not unattended collection or universal automatic indexing.
