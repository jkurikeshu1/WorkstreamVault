# Windows setup — Windows instructions only

Use this guide when the **vault will be created on Windows**. It provides the same Workstream Vault system as the [macOS guide](MACOS.md): the same choices, prompts, template files, workstreams, setup record, verification and completion report. Only operating-system paths and file operations differ.

This is documentation for a file-capable agent, not an executable installer. No WSL, Git Bash, Unix utilities, Python, Node.js, Git installation or administrator access is required by the vault format. Obsidian is optional.

## Get the package and start the agent

1. Download the repository ZIP from GitHub's **Code → Download ZIP**, or use an existing checkout. A GitHub ZIP normally extracts into a folder named after the repository and branch; use the folder that actually contains README.md.
2. In File Explorer, extract the ZIP completely. Open the extracted folder and copy its real folder path from the address bar. Do not ask the agent to modify files still inside the ZIP.
3. Give that folder to an agent that can access the Windows computer and ask it to read README.md. The agent reads this Windows guide, AGENTS.md and SETUP.md, and presents the action menu.
4. Select first-time setup or creation of a new workstream vault. Both routes ask, one at a time:
   - **What do you want to name your Vault?**
   - **Where would you like your Vault saved?**
   - Save-field hint: **Enter a valid file path.**
5. Supply the **final destination folder**, for example `C:\Work\Planning Vault`. This is a generic example, not a required location. Type the path as plain text in the agent's field, without terminal quote marks. The agent must not append the name again or silently choose another directory.
6. The agent validates access, copies/configures the blank template, checks the result and reports the actual saved location and starting note. A missing old setup record does not block creation.

No terminal step is required for this interaction. If the agent is cloud-hosted or can only produce downloads, it must say that it cannot write to this Windows destination; a pasted path does not create local access. Do not create the vault on a different computer and claim it was saved here.

## Windows path and filename rules for the agent

- Use a fully qualified Windows drive path or an explicitly intended accessible UNC share. A drive-relative path such as `C:Planning` is ambiguous; resolve it with the user instead of treating it as `C:\Planning`.
- Check the actual target and existing ancestors. Preserve a nonempty/conflicting destination; an existing empty directory may be used when it is the intended target. Do not switch to administrator mode, change access controls or enable local/cloud access to bypass a failure.
- Validate generated filename components against Windows rules, including reserved characters/device names and trailing spaces/periods. The drive's colon is part of the path root, not an invalid filename character. Use the chosen name for the map note only when it is a valid filename; explain any necessary safe filename/display-name distinction. Avoid names that differ only by letter case. [Microsoft filename/path rules](https://learn.microsoft.com/en-us/windows/win32/fileio/naming-a-file).
- Use native file APIs or explicit PowerShell cmdlets. Do not assume `bash`, `zsh`, `sed`, `cp`, `mkdir -p`, `chmod` or macOS `open` exists or has equivalent semantics. PowerShell aliases are not a portable translation of Unix command flags.

The internal note/catalog paths, such as `Jobs/Onboard an Agent.md`, remain vault-relative with `/`. Resolve them against the selected Windows vault root using the host's path library. Absolute machine paths are Windows paths; store them using a JSON serializer, which escapes backslashes correctly. Do not insert unescaped Windows paths into raw JSON text.

## Windows-native file handling

Prefer the agent's ordinary read/write/copy tools. Copy **every** template file, including `.obsidian` and its settings. Preserve filenames, empty indexes, instructions, Unicode punctuation and existing/concurrent edits. No symlink or junction is needed for setup.

For Markdown and JSON, read explicitly as UTF-8 and write UTF-8 without a byte-order mark. Windows PowerShell 5.1 has different defaults from newer PowerShell; do not use default `>` redirection or append operations to rewrite these files. Use a UTF-8-aware file tool or an explicit encoder. [Microsoft encoding guidance](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_character_encoding).

**Optional, read-only PowerShell checks — Windows only.** Run from the extracted package folder, or first assign its actual path to the task-specific variable below:

```powershell
$packageFolder = (Get-Location).Path
Get-ChildItem -LiteralPath $packageFolder -Force
Get-Content -LiteralPath (Join-Path $packageFolder 'README.md') -Raw -Encoding UTF8
```

These checks do not scaffold or modify a vault. Use `-LiteralPath` for user-provided paths so characters are not interpreted as wildcards. [Get-Content reference](https://learn.microsoft.com/en-us/powershell/module/microsoft.powershell.management/get-content).

## Returning-user setup record — Windows only

Resolve the current execution user's local application-data directory through the operating system. The conventional record is **LocalApplicationData → workstream-vaults → setup.json**, not the macOS Library folder. An agent can compute this path in PowerShell without creating anything:

```powershell
$setupRecord = Join-Path ([Environment]::GetFolderPath('LocalApplicationData')) 'workstream-vaults\setup.json'
```

Use the same record format/fields described in README.md. Populate only this user's verified template/system/vault pointers during authorized setup. A missing record advances through the normal name/location flow; preserve a conflicting record and report registration as pending rather than blocking an otherwise valid new vault. Do not confuse this record with Obsidian's own settings directory.

## Same scaffolding and completion as macOS

The agent must perform the full SETUP.md procedure on the destination copy: configure the project map and entry contract, JSON identity/catalog, current-state structure, Jobs, Templates, Workstreams index/first actual workstream, plan registry, references, daily-note structure and `.obsidian` settings. Preserve the original blank template for reuse.

Then verify JSON, identity/revision agreement, source/dependency routes, local links, required ambiguity framework, name/path replacement, complete file copying, and a read-only onboarding pass. Record the actual authorized handoff and release setup ownership. Report the Vault name, final Windows path, files created, checks, setup-record status, starting note and next action. Do not replace any of those steps with a reduced Windows-only scaffold.

## Index prior work and keep future work routed — same on both OSs

Choose **Use an existing workstream vault → Index an existing workstream**, or explicitly ask to index into a newly created working vault. Follow that vault's **Jobs/Index an Existing Workstream.md** and **Reference/Workstream Routing.md**. Both platforms inventory the same source scope, default to links or retain selected sanitized history copies, record provenance/gaps, use stable workstream/vault IDs, and update the same canonical context on subsequent authorized work. The archive is not required onboarding context.

On Windows use native file tools or PowerShell literal-path operations for authorized source reads/copies and entry-pointer edits; no Unix utilities, WSL or Git Bash are required. Register verified local routes in this Windows user's LocalApplicationData setup.json with a JSON serializer and UTF-8 output. Use vault-relative `/` note routes and IDs in portable entry pointers. Preserve source originals and existing instructions; report unavailable or out-of-scope pointer installation as pending. Do not copy private history into the public template repository. No background capture is installed.

Verify source coverage, copy provenance when selected, ID/index/record/pointer agreement, saved-file readback and a follow-up route into the same vault. Report actual results. These are the same checks required on Mac, with Windows-native path handling only.

## Optional Obsidian on Windows

After scaffolding, choose the **Windows** download on the [official download page](https://obsidian.md/download) if wanted, then install it using its normal Windows installer. Open Obsidian and choose **Open folder as vault → Open**, select the **created workstream vault folder**, and click **Open**. Open the project-name map note, Current State and Workstreams. If another vault is open, use **Open another vault** to reach the chooser. [Official opening instructions](https://obsidian.md/help/vault).

Use the already created folder, not the package root and not a new empty vault. Downloading/launching/installing an app still follows the user's actual authority. File-only operation remains fully supported.
