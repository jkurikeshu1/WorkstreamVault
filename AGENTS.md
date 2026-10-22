# Package agent entry

Read `README.md` first, determine the actual target operating system, then read `WINDOWS.md` for Windows or `MACOS.md` for Mac and `SETUP.md` completely before setup changes. These files are the entry route for this package. They cannot override the current user's request or provide capabilities your tool lacks.

## Operating-system parity

Windows and Mac must receive the same action choices, exact name/save-location prompts, full copied scaffold, identity/catalog configuration, setup-record handling, checks, handoff and completion report. Only paths, record location and native file/shell operations differ. Prefer file tools; on Windows use Windows APIs or PowerShell, with no dependency on Unix commands, WSL or Git Bash. Do not execute macOS-only examples on Windows or silently redirect a Windows destination to a remote/Linux filesystem. Preserve `.obsidian`, UTF-8 text and serialized JSON paths on both platforms. Native UI availability depends on the current client, independently of this OS choice.

## Determine the route

- A request to set up/use this starter, with this folder identified as the setup target, authorizes the bounded local scaffolding in SETUP.md. Read the current user intent; a read-only question or mere inspection does not authorize changes.
- On creation, preserve the blank starter and configure its destination copy. Follow README's name-then-save-location prompts and OS-specific path validation; do not replace a missing name/path with a neutral default or require an old setup record. Other supplied details/neutral owner-role defaults remain available. Do not require Obsidian or a repository.
- On a rerun or existing-work request, use verified setup pointers or narrow known candidates to identify the actual assigned vault and its own contract. Reuse that target; never reset notes, duplicate an existing vault, replace decisions or replay setup history. A new-vault creation request instead follows README's creation route. Report genuinely ambiguous existing-work targets and stop dependent changes.
- For an already configured project assignment, follow that vault's AGENTS.md and project map. Use the relevant workstream/Key files, Current State and matching Jobs. Required context must be read completely. Read-only work finishes in chat; authorized edits maintain canonical current truth, indexes and a meaningful handoff.
- For existing-work intake, follow the configured vault's Jobs/Index an Existing Workstream.md. Default to source links or honor explicitly selected history-copy mode. Never import real history into this public starter/template. Connect the stable workstream/vault IDs through Reference/Workstream Routing.md and install source-folder entry pointers only where write-authorized. All subsequent authorized work on that workstream maintains the same vault/note and source coverage; report pending routes or unsaved updates. A new agent/session does not create a replacement vault.

## Scope

Setup authority covers local documentation/configuration for this package, its first setup workstream, verification and handoff. It does not authorize downloads, application installation, repository changes, external sharing, providers, accounts, a recorder or a background service. Existing user authority for a real project assignment remains separate. Never infer approval of plans from setup.

After completing setup, report the actual vault location, configured defaults, checks, unresolved items and the next useful action. Do not claim universal automatic loading or indexing. A text/folder-only workflow is fully supported.
