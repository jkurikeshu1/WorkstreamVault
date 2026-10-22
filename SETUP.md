# Set up this vault

This is the complete agent procedure for an authorized setup of the supplied starter. Read README.md and package AGENTS.md first. Use ordinary file operations; no application, package manager, installer, account or network access is required.

## 1. Verify scope and destination

Confirm that the current user wants setup, rather than a read-only explanation. Verify access to this package and its instructions. Use the extracted package's existing location by default; honor a supplied destination and applicable local location instructions. Do not relocate existing projects. If you cannot read/write required files, explain the smallest access issue rather than pretending setup succeeded.

Inspect immediate child folders for the placeholder vault or an already configured vault containing project-context.json. A configured identity and actual map/contract must agree. If already configured, read it and verify readiness without resetting content or creating duplicate workstreams/handoffs. If a target name already has unrelated files, stop and report the collision. Never merge over an existing vault.

## 2. Use known details or neutral defaults

Use project details and constraints the user already supplied. Missing cosmetic choices do not require another permission question. Otherwise use:

| Choice | Neutral default |
| --- | --- |
| Project name | Work Vault |
| Human project owner | Project owner — the user requesting setup |
| Context maintainer | Same owner role |
| Local project ID | work-vault |
| Initial context/policy revision | local-1 |
| Purpose | Coordinate the project work the user explicitly assigns |
| Repository | None unless the user supplied one |
| Note application | Folder/text-editor workflow; Obsidian optional |

Report defaults at completion so the user can rename them later. Never invent a personal name, organization, project history, approval or real work objective. If a supplied project name is unsuitable for a filename, use a safe name derived from it and explain that choice. Genuine conflicts over authority, access or existing content require resolution; neutral defaults do not resolve those conflicts.

## 3. Configure the starter in place

Work only on the identified starter. Preserve the expected starting content before editing and compare current bytes before overwriting. The placeholder starter has no active claims; perform this initial package-authorized setup as one writer. If another setup agent is present, stop overlapping writes and resolve ownership first.

1. Rename the `{{Project Name}}` folder and its matching map note to the selected project name. Do not create a second live copy. On rerun, retain the existing configured name/location unless a rename is explicitly requested.
2. Replace `{{Project Name}}`, `{{Owner}}`, `{{Vault Path}}` and `{{Repo Path}}` in the inner vault's text/JSON. The vault path is its actual resolved location on this user's machine, not a path inherited from any package. Preserve the daily-note template's `{{date:YYYY-MM-DD}}` token.
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
- Ensure no setup identity/path placeholders remain in operational files. The built-in date token may remain only in the Daily Note template. Package guide examples can retain generic placeholders.
- Confirm entry contract, plan Job and proposal template all require decision boundary, plausible agent drift, explicit direction/section, owner/verification and resolved/deferred/needs-decision status. There must be no consequential unresolved choice inside a claimed implementation-ready architectural increment.
- Confirm no fake claims, locked resources, history, approval, credentials or application configuration were added. Human-review flags stay honest.
- Run a read-only onboarding pass yourself against the actual configured vault: identify its owner/purpose, workstream boundary/Key files, task Job, current authority/stop and missing dependencies. Do not claim that this self-check is independent review or automatic provider qualification.

If Obsidian is installed and the user wants it, explain opening the configured folder as a vault. Do not require or automatically install it. A missing Obsidian installation is not a setup blocker. The same files work with a text editor and a file-capable agent; Obsidian-specific date insertion and clickable wikilinks are conveniences.

## 7. Hand off and stop

Record one actual dated setup handoff using the configured Daily Note template, with real checks, limitations, exact next action and owner. Release the setup claim; leave no invented active lock. On a rerun do not append another setup history entry unless a meaningful authorized change actually occurred.

Report the canonical vault location, selected project/defaults, verification results, any unresolved access/configuration, and how to give the agent its first real task. Explicitly distinguish ready documents from automatic tooling. Stop at the setup boundary; do not start unrelated project implementation.

For later project work, the package agent contract locates the one configured child vault and follows its own entry contract. The agent maintains workstreams, current truth and meaningful handoffs through the existing Jobs as it performs authorized work. This is an instruction-driven working practice, not unattended collection or universal automatic indexing.
