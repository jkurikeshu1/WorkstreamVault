# Workstream Vaults — start here

This package is a reusable starter for **workstream vaults**: folders of Markdown notes and JSON files that help a person and their agents coordinate project work. **Obsidian is optional.** A file-capable agent and a text editor are enough.

## First contact: show an action menu

If the user gives only this package's folder path, read the entry/setup instructions and present the action menu below. That menu establishes intent; a path alone does not authorize scaffolding. Do not end with a generic “set it up, review it, or make changes?” paragraph when the platform can show a structured question.

Use the **current platform's own supported question/choice interface**, with one single-selection question. Prefer four choices when the available interface supports four; follow its actual option limits. Show this in the current conversation, not in an external form, a new chat or a newly generated application. No executable, custom UI code, plugin installation or tool configuration is needed for this documented flow.

**Question: What would you like to do with Workstream Vaults?**

| Choice | What the user is choosing |
| --- | --- |
| **Set up for the first time** | Establish the reusable Workstream Vault system and create the first workstream vault. |
| **Create a new workstream vault** | Scaffold a separate project vault from the blank template, reusing a verified system setup when available. |
| **Use an existing workstream vault** | Select a verified existing vault, then continue the user's actual project assignment. |
| **Explore how it works** | Explain the package and workflow without making changes. |

If a tool allows only three preset options, use the first three choices and explain that the user can type **Explore how it works** in its free-text/other-answer field or ordinary chat. Do not invent a fourth option outside the tool's schema. A preselected choice is not a submitted answer. Honor custom text, cancellation and the current user's explicit direction.

When the user's request already specifies the route, skip the redundant menu. Likewise, a verified returning user explicitly asking for a new workstream vault goes directly to the naming question. A returning user who provided only a path still needs to choose an action; past setup alone does not establish today's intent.

### Match the interface to the agent platform

Determine the actual host and exposed tools from the current session, not just the model name. Present the same choices and follow-up intent using the host's own UI:

| Host | Required presentation when supported | When that interface is unavailable |
| --- | --- | --- |
| **ChatGPT** | Use the current ChatGPT surface's exposed native question/form controls for the menu and separate text inputs for the name and save location, when provided. Only use file tools that actually reach the selected destination. | Ask the same questions in ordinary ChatGPT conversation. If local filesystem access is unavailable, explain that limitation; a typed local path does not give ChatGPT access to the computer. Do not claim files were created there. |
| **Codex** | Use the available native structured user-input/question tool, such as `request_user_input` or `request_user_input_async`, only when actually exposed and allowed in the active mode. Use its choice controls for the menu and separate free-text inputs or other-answer fields for the name and save location. | Show the same menu as numbered chat choices and collect each answer in chat. Do not switch modes or change settings just to force a menu. |
| **Claude / Claude Code** | In Claude Code, use its exposed `AskUserQuestion` interface for the choices and supported free-text/other-answer input for each of the name and save location questions. In another Claude surface, use that surface's actual native question/form capability when provided. | Ask the same numbered choices, naming question and save-location question in the current Claude conversation. Do not assume every Claude app exposes Claude Code tools. |
| **Grok / Grok Build** | Use the current Grok host's exposed native question/choice tool, then separate supported free-text inputs for the name and save location. Use the actual available interface; do not guess a tool name or call a Codex/Claude tool that is absent. | Present the same numbered choices in Grok chat and collect the name, then the save location, as normal replies. If that surface cannot access the supplied files, explain the missing access before claiming setup can run. |
| **Grok Bots** | Use the Bot conversation's exposed native question/form tool to present the choices, followed by separate supported text inputs for the name and save location. Keep each question in the current Bot conversation so the answer returns to the same Bot. | Present the choices and both text questions as normal messages in that Bot conversation. Do not create another Bot, send cross-Bot messages or build a separate UI just for onboarding. |

Native support depends on the client, active mode, tool availability and permissions. A README can instruct an agent to use existing controls; it cannot add controls to a platform or guarantee an agent invokes them. If the native tool is absent, restricted or fails, briefly say the same choice will be collected in chat and use the fallback once. Do not claim that Markdown checkboxes are native buttons or that a text reply came from a form.

For Grok Bots or any remote agent, distinguish its execution computer from the user's local computer. Verify that the supplied package and setup record are accessible on the authorized target; never assume a local path exists on a cloud computer or silently enable broader machine access.

Capability references: [Codex structured user input](https://learn.chatgpt.com/docs/app-server), [Claude questions and free-text answers](https://code.claude.com/docs/en/agent-sdk/user-input), and [Grok Bot conversation questions/forms](https://docs.x.ai/grok-bot/chat-and-collaboration). These establish supported mechanisms, not a cross-platform guarantee. For ordinary Grok/Grok Build, inspect the current session's actual tools; no universal custom-choice API is assumed here.

### Required creation sequence: name, save location, scaffold, report

After either **Set up for the first time** or **Create a new workstream vault**, the next creation questions are exactly the following, **in this order, one at a time**. They refer to the new workstream vault. Do not ask for the location of an old system setup before these questions. Do not insert an optional Obsidian question between them or delay scaffolding for an app choice.

**1. Ask for the name**

> **What do you want to name your Vault?**

Use the platform's native text input when available. Field label: **Vault name**. Optional placeholder: **Enter a Vault name**. Wait for a non-empty name; then ask the second question.

**2. Ask for the save location**

> **Where would you like your Vault saved?**

Use a separate native text input when available. Field label: **Save location**. Input hint/placeholder: **Enter a valid file path.** Helper text: **Enter the full path of the folder to create for this Vault.** Treat the answer as the final vault folder, not merely a parent to which the name will silently be appended.

In a choice-only tool, collect each answer through its supported other-answer/free-text path. If no native text field is available, ask the same questions in chat, in the same order. A literal placeholder inside a chat message is explanatory text, not a real form control. If the host cannot customize a field's placeholder, show the hint beside the question. Do not build a custom form, add an executable or install a skill/plugin to force a particular UI.

An empty, skipped or dismissed answer is not permission to choose a default or create anything. If the user already explicitly supplied a usable name or final destination, reuse that value and state it rather than asking redundantly; collect the next missing field. Use **workstream vault** in setup explanations and action labels, with the exact short **Vault** wording above for these two questions.

**3. Validate the destination, then scaffold**

Validate the path on the actual authorized execution computer. It must resolve to an intended folder location, with a usable existing ancestor and sufficient access to create the target. Resolve home-directory notation safely; treat path text as data, not a shell command. Reject a URL, an existing regular file, invalid path characters for that operating system, or an ambiguous relative location. If a relative path's base is clear, resolve it and show the final location; otherwise ask for an unambiguous path. Do not silently redirect a local path to a remote computer.

Use the final destination exactly once: do not append the chosen Vault name again when it is already part of that path. A nonexistent target can be created. An existing empty directory can be used after verifying it is the intended target; a nonempty or conflicting directory requires resolution before writes. Do not overwrite, merge into or reset someone else's files, follow an unexpected redirected target without checking, or change permissions just to make a path writable.

Once both answers are present and the destination is valid, begin the bounded scaffolding using the packaged blank template. **No existing setup record is required to create a new workstream vault.** A missing registry must not trigger an old-setup-location question or another installation-choice loop. Reuse verified setup information where useful; otherwise initialize the necessary setup pointers during the authorized creation. Preserve malformed/conflicting old records and report unresolved registration separately from the created vault.

Do not ask for another generic confirmation after the two required answers. Only ask again for a real collision, missing required access or unresolved scope. If the platform has no tools that can write to the selected filesystem, report that specific limitation; do not claim scaffolding succeeded. Existing-vault selection and read-only exploration do not create new vaults.

**4. Return the creation result**

After verification, report the chosen name, actual saved location, useful created files/folders, completed checks, anything pending, and the map note to open first. Follow the completion format later in this README. Offer optional Obsidian guidance after this result, without making it a prerequisite or asking permission to scaffold a second time.

## Quick start

1. Unzip the package into an empty location you control.
2. Give a file-capable agent the extracted package folder. After reading this README, it should show the action menu above. An explicit request to **read README.md and show the Workstream Vaults action menu** is the dependable starting point if the host does not automatically inspect a supplied path.
3. Select first-time setup, create a new workstream vault, use an existing one, or explore. For either creation choice, answer **What do you want to name your Vault?** followed by **Where would you like your Vault saved?** The save field is prompted with **Enter a valid file path.**
4. After validating the supplied final folder path, the agent scaffolds the workstream vault and reports what it created. No additional generic confirmation or existing setup record is required. Obsidian remains optional and can be offered afterward.

This is an instruction-driven setup, not an executable installer. Reading this file does not run code, install applications or grant filesystem access. A read-only question remains read-only. The distributed package contains no populated setup record or user-specific paths.

## Agent entry and procedure order

Read this README, [AGENTS.md](AGENTS.md) and [SETUP.md](SETUP.md) completely. Use this README's route selection, explicit vault naming, returning-user lookup and reusable-template rules before applying SETUP.md's identity/configuration, verification and handoff steps to the chosen target.

This README makes the following setup distinctions explicit:

- **System setup** establishes a reusable template home and a small local setup record. It installs no software or service.
- **New workstream vault** creates a separate, named project vault from the retained blank template. It does not rename or reset an existing project vault.
- **Existing project work or a rerun** reuses the exact assigned vault and its own contract. It does not create another vault or replay setup history.

The earlier single-vault/in-place instructions in SETUP.md and package AGENTS.md describe configuring or reusing one target. For a creation route, preserve the original blank template and apply those configuration steps to its new destination copy. This README's required name-then-save-location sequence replaces any neutral project-name or automatic destination defaults for interactive creation. A missing old setup record is not a prerequisite failure. These route clarifications do not broaden access, approval or external-action authority.

## Recognize a returning user without chat history

For a setup or new-vault request, a narrow read-only check of the **Workstream Vaults local setup record** can identify returning users. This lookup is optional discovery, not an extra required question or a prerequisite to scaffolding from the packaged blank template. It must not interrupt the name-then-save-location sequence. Verify any pointers that will actually be reused. The record's conventional location is the operating system's per-user configuration/application-data area, inside a `workstream-vaults` folder, named `setup.json`:

- On macOS, use the current user's **Library → Application Support** directory.
- On Windows, use the current user's **local application-data** directory.
- On Linux, use the user's configured configuration directory, falling back to **.config** in their home directory.

The agent resolves those locations on the current user's machine. The package contains no prefilled personal path. Read only the specific record and explicitly routed sources needed for this assignment; do not recursively search the computer for vaults. If required access is unavailable, explain the narrow access issue rather than claiming no setup exists.

The first authorized system setup creates this small **data record**, not a script. Record the setup format/version, actual system home, retained blank-template location, chosen vaults home, optional viewer preference, and each known workstream vault's name, stable project ID and canonical location. Record accurate setup/verification state; do not call a partially completed setup ready. Keep only local setup pointers, with no note bodies, credentials, account data or transcripts.

Before treating the user as returning:

1. Read and validate the record; malformed or conflicting records stay unresolved.
2. Verify access to any retained template that will be reused, and verify an existing vault only when relevant to an existing-work assignment against its actual project-context.json and entry contract. For creation, the user supplies the destination through the required save-location question.
3. Treat stale/missing locations as unresolved discovery, not permission to overwrite the record, reset the system or create duplicates. For a new-vault request, use the packaged blank template and chosen destination without requiring old pointers to be repaired first. A record is discovery guidance, not task approval.
4. If no record is found, inspect the supplied package's immediate known candidates for an already configured vault. A verified existing setup can be registered during authorized setup without reinstalling it.
5. Ask for an old setup/vault's location only when the user selects **Use an existing workstream vault** or explicitly asks to recover/reuse that specific old setup and its location is necessary. Do not ask this during ordinary creation from the supplied template. Verify any supplied existing location before registering it. Filesystem access remains necessary even with a valid record.

A new agent can therefore discover the setup from disk without earlier conversations. A fresh package cannot magically identify an unregistered vault somewhere else. This README documents the future agent procedure; no registry or background discovery tool has been installed by receiving this package.

## First response when no setup can yet be verified

Use the first-contact action menu above rather than a generic clarification paragraph. After either creation choice, ask the required **Vault name**, then **Save location**, validate the final folder path, and scaffold from the packaged blank template. A missing setup record does not trigger a question about where the old system is, a repeated menu, or another installation step. A reply such as **First-time setup** answers the route question: advance to the Vault-name question instead of asking for an existing setup path.

If the selected route is **Explore how it works**, answer in chat without claims or file changes. For **Use an existing workstream vault**, resolve the actual target and requested assignment; selecting it is not permission to start new project implementation.

Do not ask a question again when the verified sources and current user request already answer it. Missing discovery information is not proof of first-time use.

## First-time setup and optional Obsidian

After the creation result, or earlier only if the user explicitly asks about it, offer the following optional visual component. It must be clear that the user can keep working from files alone. This choice must not interrupt the required name, save-location and scaffolding sequence:

> **Would you like to use Obsidian to view and navigate your workstream vault? It's optional.**
>
> [Obsidian](https://obsidian.md/) is a note-taking app that lets you browse your vault's folders, follow links between notes and edit them in one place. It makes the structure easier to explore visually. Your agent can also work directly with the same files without it.
>
> You can choose **help me get started with Obsidian**, **I already have Obsidian**, or **continue with files only**. This choice does not require a paid service or an account for this local-folder workflow. [Obsidian's local-use details](https://obsidian.md/pricing).
>
> If you'd like Obsidian:
>
> 1. [Download Obsidian for your computer](https://obsidian.md/download), then install and open it. If it's already installed, skip the download.
> 2. After I scaffold your workstream vault, I'll identify the exact folder to open.
> 3. In Obsidian's vault chooser, select **Open folder as vault → Open**, select that configured workstream vault folder, then click **Open**. If another vault is already open, use **Open another vault** to reach the chooser. [Official opening instructions](https://obsidian.md/help/vault).
> 4. Open the note named after your project, followed by **Current State** and **Workstreams**, to explore the system.
>
> Opening that folder uses the same files the agent maintains. No import or second copy is needed.

Present the download link and opening instructions as clickable, readable text. Offer guidance rather than silently installing or launching applications. Obsidian download or installation is not a dependency for scaffolding. Do not repeatedly ask returning users to choose a viewer; honor a recorded preference and provide the instructions when requested. An unanswered optional viewer choice does not authorize installation or block a clearly authorized file-only setup.

## Returning-user response and new-vault name

When existing setup is verified and the user wants a new project vault, acknowledge that verified fact briefly, then ask through the native text input or supported chat fallback:

> **What do you want to name your Vault?**

After the name is supplied, ask:

> **Where would you like your Vault saved?**
>
> Enter a valid file path.

The first-time route uses the same sequence. Do not infer a save destination solely from a previous vaults home; the current user's answer controls. Use already supplied answers without repeating questions.

## Scaffold after the name and save location are supplied

The selected creation route, name and valid final destination define the bounded scaffolding request. Begin without another generic permission question. Resolve genuine name/destination collisions, inaccessible sources or scope conflicts before dependent writes.

1. Use the user-selected final folder path, honoring applicable local location instructions and explicit user direction. The recorded vaults home may be offered as an optional suggestion, not silently selected instead. Create only the folders needed for this actual setup. The reusable system/template stays in its existing location.
2. Retain the packaged `{{Project Name}}/` as the blank template. Create the selected workstream vault at the exact validated destination folder, without appending the name a second time. Use the chosen Vault name for its map and project identity, and its actual destination for canonical paths. Never overwrite, rename, merge into or reset an existing project merely to satisfy the new name. Do not copy an existing project's content as the generic template.
3. Apply SETUP.md's placeholder replacement and identity/profile configuration to the new destination copy. Set the map filename and project identity from the chosen name. Use an explicitly supplied human owner, otherwise the documented current-user owner role. Do not invent a person's identity. A separate repository is optional; no Git initialization or repository mutation is implied.
4. Read the actual destination's map, entry contract, current state, guardrails and matching Jobs. Complete their required dependencies. For a real workstream use the user's known assignment; otherwise create only the actual setup workstream described by SETUP.md.
5. Verify JSON, project/revision agreement, catalog routes, local links, remaining placeholders and the connected architecture-ambiguity framework. Run a read-only onboarding check, keeping human-review/approval flags honest. Claim/release setup work and record one genuine setup handoff under the destination's contract.
6. During authorized system setup, save or update the local setup data record only with verified system/template locations and the actual new workstream vault's chosen name, identity and location. Preserve earlier entries and concurrent changes; compare the expected base and read back the save. Failed, inaccessible or conflicting registration must be reported as pending rather than fabricated or used to reset existing data. When the vault itself was created and verified, report that result separately from incomplete optional discovery registration. Do not write note contents into the record.
7. Return the concrete creation summary below. Stop after setup and handoff; wait for the next real work assignment. Optional Obsidian guidance can follow without delaying or repeating the completed scaffolding.

## Completion response: show what was created

After successful creation and readback, provide a concise result in the current conversation. Use the actual values, verified files and checks, with clickable local references when the host supports them:

- **Vault created:** the chosen Vault name.
- **Saved to:** the actual resolved final destination folder.
- **Created:** the project map, AGENTS.md, ONBOARD.md, Current State, identity/profile JSON, Jobs, Templates, Workstreams index, plan registry, references/decision log, daily-note structure and optional Obsidian settings. Summarize or show a compact tree; list only what actually exists.
- **First workstream:** the actual assigned workstream or setup workstream, with a link to its note.
- **Verified:** actual JSON, identity, routing, links and onboarding checks performed. Separate failures, unknowns and skipped checks; never claim application installation or automatic agent loading.
- **Setup record:** saved/reused with readback, or a specific pending/unavailable registration status. Its absence is not proof that the vault was not created.
- **Open first:** the actual project-map note, then Current State and Workstreams.
- **Next:** invite the user's first real work assignment. Offer optional Obsidian viewing/download/opening instructions here if useful.

If creation fails, describe what was actually created, what remains unchanged and the precise blocker/recovery step. Do not display **Vault created** as success for a failed/partial scaffold. Do not dump setup scripts, raw command output or private source content into the result.

An existing-vault work request takes its own route: resolve the exact assigned vault from verified pointers and follow its own AGENTS.md. A returning user does not automatically want a new vault. If more than one vault could match an existing-work request, ask which one; never choose silently.

## After setup

Each workstream vault has one canonical folder and its own operating contract. The system's setup record routes to those separate projects; it is not a copy of their work or a second project database. Preserve the blank template so later new-vault requests can scaffold another clean project.

For authorized project work, follow the selected vault's current state, guardrails, relevant workstream/Key files, exact plan if applicable, and matching Job. Maintain current truth, Workstreams/Daily Notes indexes and meaningful handoffs as that work is performed. Read-only questions finish in chat. Unrelated activity is not imported, and no watcher, automatic transcript recorder or background service is included.

## Files in this package

- [AGENTS.md](AGENTS.md) — package entry and scope boundaries.
- [SETUP.md](SETUP.md) — field configuration, operating-context reads, verification and handoff steps, applied to the target selected here.
- [START HERE.md](<START HERE.md>) — manual setup and complete JSON field reference. For the reusable multi-vault workflow, preserve the original template as directed here.
- `{{Project Name}}/` — the blank template used to create new workstream vaults.

This README is the only changed package file for the guided first-time/returning-user flow. It contains instructions for future authorized setup; it does not itself execute, create a setup record, install software or force an agent to load it. No executable or additional packaged file is required.
