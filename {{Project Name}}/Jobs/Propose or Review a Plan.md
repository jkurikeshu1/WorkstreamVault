# Propose or Review a Plan

Part of [[Jobs/Jobs]] and [[Proposed Plans/Proposed Plans]]. Use for drafting, locating, reviewing, comparing, amending or formally revising a plan.

## Resolve the exact plan

Each plan has a stable living note in `Proposed Plans/` and a complete immutable snapshot for each formal revision in `Proposed Plans/Revisions/`, named `<Plan Name> — rN.md`. The registry's explicit Latest link, living `revision`/`latest_revision_note`, and snapshot `snapshot_revision` must agree. State the exact revision. If they disagree or a snapshot is missing, report the paths and block dependent work; repair only within write scope. Never infer Latest from dates, filenames, chat or memory.

## Draft and revise

Read Current State, guardrails, the workstream/Key files and registry. Separate verified facts from assumptions. Check for an existing living plan with the same scope. Copy [[Templates/Proposed Plan Template]] when authorized to save a plan. Cover outcome/measures, non-goals, experience/failure states, exact rules, data/security/ownership, acceptance, dependencies, order, tests, rollout/rollback, costs and alternatives.

When ready for review, create complete r1, its registry row, living revision index/history and a normal handoff. Only {{Owner}} approves the named revision. Draft/Proposed/Under Review never authorize implementation; Accept is a reviewer verdict. A direct narrow assignment does not approve the broader plan.

Review-only means analysis in chat; save a review only when authorized. Saved reviews append to the living note and update `last_change_at` and `last_change_summary`. Do not change its normative design or revision number merely to review. Analyze-and-revise means review first, then create a complete rN+1 only when a material change is warranted. Preserve every old snapshot/review and update all frontmatter, visible metadata, registry/latest pointers, revision index/history, Current State readiness and the handoff. Use timestamps with timezone. An approval does not transfer silently to a new revision.

For a snapshot, copy the full normative proposal and relevant provenance at that revision, add `snapshot_revision: N`, and clearly label it immutable. Later approval/review/status changes go in the living note/registry, referencing that exact snapshot; never rewrite a snapshot to reflect them. Living-note review logs can grow without mutating the frozen revision.

## Required architecture ambiguity review

Apply whenever an architectural plan is drafted, reviewed, amended or revised:

| Decision boundary | How an agent could drift | Explicit direction and section | Owner / verification | Status |
| --- | --- | --- | --- | --- |

Use **Resolved**, **Deferred outside active increment**, or **Needs decision**. Put binding direction beside the relevant design section; the table points to it. Review relevant lenses: outcome versus methods; decision/state ownership; interaction entry and target binding; schemas/identities; context storage/retrieval/correction/forgetting; models/access/spending; failure/recovery/Stop; scope/order; migration/compatibility; finite acceptance/rollback.

Every consequential active-increment choice must be resolved or explicitly excluded before implementation readiness. Needs decision means not ready, with the precise missing choice and owner. A deferral includes its activation condition and is not current permission. Preserve useful reasoning and flexible methods; examples are acceptance scenarios, not permanent capability limits. Routine compatible details remain builder discretion. Contradictions need a bounded amendment while independent authorized work can continue.

## Review every applicable lens

1. Exact revision, Accept/Amend/Reject verdict and readiness for review versus implementation.
2. Benefits for the outcome, user and workflow.
3. Costs: complexity, maintenance, time, access/provider cost and opportunity cost.
4. Overlooked issues, edge/failure states, dependencies and conflicts.
5. Stronger opportunities for quality, adoption or impact.
6. Efficiency: whether a smaller/reused sequence works better.
7. Security/privacy/abuse: scopes, secrets, untrusted input, retention and rollback.
8. Usability: hierarchy, defaults, accessibility and empty/loading/error states where relevant.
9. Precise amendments, mitigations, blocking questions, or why no revision is needed.

Check semantic ambiguity; model/AI correctness if used; data/migration/retention; authorization; concurrency/retries/time zones; provider budgets/timeouts; performance/accessibility; and multi-owner/integration/rollback. Mark irrelevant lenses not applicable with a reason rather than inventing requirements.

An authorized saved review records timestamp/timezone, reviewer/model, workstream, immutable revision link, disposition/readiness, each lens, mitigation, revision outcome and blockers. Implementation requires actual approval, claims and check-in; completion is distilled to current docs with delivery evidence.

## Convergence

One approval effort has at most ten formal snapshots; aim to converge by r2 or r3. Reviews consume no revision. Only material correctness, outcome, security, evidence or readiness issues warrant a new snapshot. Independent Accept closes deliberation for a human decision unless material new evidence, implementation failure or owner-changed goals reopen it. r10 without acceptance stops for {{Owner}}; no automatic r11. Only the owner can start a genuinely new bounded effort for changed goals/evidence, with the reason recorded. Never reset the count to evade the limit. Exhaustion is not acceptance.

## Required response ending

Keep the complete analysis, then add **Simple summary** in everyday language, normally three to six short sentences and at most about 120 words. Explain what is proposed/changed, why it matters and what remains unapproved or unimplemented. Then offer these choices:

1. **Propose next steps to get started** — authority, owners, sequence, locks, checks and delivery gates; proposing them does not begin work.
2. **Submit/save the proposed plan and do nothing else** — save only within current write authority.
3. **Custom prompt / direction** — invite a different constraint, reviewer or priority.
