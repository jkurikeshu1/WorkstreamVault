# macOS setup — Mac instructions only

Use this guide when the **vault will be created on macOS**. Windows users and agents must follow [WINDOWS.md](WINDOWS.md) instead. Both guides produce the same Workstream Vault system; operating-system paths and file operations differ.

## Get the package and start the agent

1. Download the repository ZIP or use an existing checkout. Expand the ZIP in Finder and locate the extracted folder containing README.md.
2. Give that folder's actual location to an agent with access to this Mac. Ask it to read README.md. It reads this guide, AGENTS.md and SETUP.md and presents the same action menu.
3. After first-time setup or new-workstream-vault selection, it asks **What do you want to name your Vault?**, then **Where would you like your Vault saved?**, with **Enter a valid file path.** as the save hint.
4. Supply the final destination folder. The agent validates it, preserves the packaged blank template, scaffolds the chosen destination and reports the result. It does not append the name twice, overwrite an existing project or require a pre-existing setup record.

A text editor and a file-capable agent are sufficient. Obsidian, a repository and terminal commands are optional. A remote agent must establish access to the intended Mac filesystem rather than treating a path as access or creating the vault on its cloud computer.

## macOS file handling

Use the agent's native file tools or actual macOS shell operations. Quote paths containing spaces and treat user-supplied path text as data. Resolve home-directory notation against the execution user; don't use another person's home or a Windows drive path. Preserve complete contents, including `.obsidian`, Unicode filenames and concurrent edits. No compatibility symlink is required.

**Optional, read-only shell checks — macOS only.** Run from the extracted package folder:

```sh
pwd
ls -la
cat ./README.md
```

These checks do not scaffold a vault. They are macOS examples, not instructions for Windows PowerShell. Do not require Windows users to install a Unix shell to reproduce the setup.

Keep Markdown/JSON as UTF-8, preferably without a byte-order mark, and use a JSON serializer for machine paths. Preserve the vault-relative `/` routes in notes/catalogs. Choose portable note names so the result can also be copied to Windows; see the filename guidance in WINDOWS.md rather than introducing case-only duplicates or Windows-invalid names.

## Returning-user setup record — macOS only

Resolve the current execution user's **Library → Application Support → workstream-vaults → setup.json**. Use the same record format/fields as Windows, but record this Mac's verified locations. Do not use the Windows local-application-data directory or assume another machine's paths exist.

The record is setup metadata, not an installed service. A missing record does not block a new vault; a conflicting or inaccessible one stays preserved and is reported accurately. Only an existing-vault/recovery request may need an old setup location.

## Same scaffolding and completion as Windows

Perform the entire SETUP.md procedure on the destination copy. Both platforms create the same map/entry/onboarding files, current-state structure, identity/profile JSON, Jobs, Templates, Workstreams index and actual first workstream, plan registry, references, daily-note structure and `.obsidian` settings.

Perform the same JSON/identity, routes, links, placeholder, architecture-ambiguity, complete-copy and read-only onboarding checks. Save the meaningful setup handoff, release ownership and report the actual created files, final location, checks, registration status and starting note. A successful command alone does not prove setup is complete.

## Optional Obsidian on macOS

After scaffolding, select the **Mac** download from the [official download page](https://obsidian.md/download) if wanted and follow its macOS installation flow. Open Obsidian, choose **Open folder as vault → Open**, select the created workstream vault folder, then click **Open**. Open its project-name map, Current State and Workstreams. Use **Open another vault** if another vault is already open. [Official opening instructions](https://obsidian.md/help/vault).

Open the existing created folder; do not create a second empty vault or use the package root as the workstream vault. Application installation/launching is separately governed by the current user's authority. The folder-only workflow remains available.
