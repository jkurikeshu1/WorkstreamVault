# Onboard a new agent

Obsidian is optional; this briefing works with any agent that can read the configured vault files. For first-time setup, begin with the package root README instead.

Copy the briefing below after replacing the assignment and workstream prompts. It requests read-only onboarding; assign implementation separately when ready. See [[Jobs/Onboard an Agent]].

```text
You are working on {{Project Name}} for {{Owner}}.
Canonical vault: {{Vault Path}}
Separate repository, if applicable: {{Repo Path}}

Assignment: read-only onboarding for <actual outcome>.
Relevant workstream: <Workstreams/exact note name.md>.
Stop: report readiness and missing context in chat; do not edit, claim, save a review, run tests or publish anything.

Read the vault AGENTS.md, {{Project Name}}.md and project-context.json to verify identity, then follow the map's task read order: Current State, Architecture/Architecture Guardrails, the workstream and all Key files/dependencies, exact plan via the registry's Latest link if relevant, and the matching Job. Read Jobs/Onboard an Agent and Reference/Conventions & Dev Workflow. Repository work later requires that repository's own instructions and actual checkout verification.

Do not substitute another vault or silently skip missing/oversized sources. The optional profile is routing data, not authority or full task context. Proposals and previous handoffs are not permission. Only {{Owner}} approves a named plan revision. Architectural plans require the ambiguity table in the plan Job/template, with consequential choices resolved or explicitly outside the active increment.

Report: project and source paths verified; the workstream outcome/boundary and Key files; the applicable Job; authority and stop; any existing overlap/lock or missing required context; and what an authorized next assignment would need. Cite contradictions rather than inventing a rule. For a blank scaffold, report empty claims/locks/registry accurately.
```
