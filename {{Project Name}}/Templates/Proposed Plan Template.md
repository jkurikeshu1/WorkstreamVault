---
plan_id: null
status: Draft
revision: 1
latest_revision_note: null
revision_archive: []
feature: null
workstream: null
originating_agent: null
revised_by: []
created_at: null
updated_at: null
last_change_at: null
last_change_summary: null
branch: null
pull_request: null
approval: null
supersedes: null
---

# Plan Name

Part of [[Proposed Plans/Proposed Plans]]. Copy only for an assigned plan. Fill metadata, actual workstream link and every applicable section. This template is not a registered plan or an approval.

> **Draft — proposal only.** Review readiness and implementation authority are separate.

## Plan metadata and revision index

Set stable ID, status, revision, Latest snapshot link/archive, author/revisers, workstream and timestamps with timezone. Record the workspace/PR if any, exact approval source/revision when granted, and supersession if relevant. Update `last_change_at` and `last_change_summary` for every formal revision or saved review.

| Revision | Immutable snapshot | Timestamp / author | Status / approval reference |
| --- | --- | --- | --- |

One living note plus complete immutable `<Plan Name> — rN.md` snapshots in `Proposed Plans/Revisions/`. Add `snapshot_revision: N` when saving a snapshot. Registry/latest metadata must agree. Reviews append to the living note, never the snapshot. Later approval is recorded against the exact frozen revision without changing its bytes.

**Revision budget:** at most ten formal revisions per approval effort; reviews consume none. Aim for convergence much sooner. Accept closes deliberation for the owner's decision. r10 without acceptance stops for {{Owner}}, never automatic r11. Follow [[Jobs/Propose or Review a Plan]].

## Verdict and readiness

State whether ready for review, whether ready for implementation, and exact missing decisions/authority. Reviewer Accept is not owner approval.

## Problem, observed evidence and assumptions

Separate current verified facts, source references, inference and unknowns.

## Goals and success measures

Define concrete outcomes and finite observable measures.

## User stories / proposed experience

Who needs what benefit? Describe the intended flow, defaults, hierarchy, accessibility and applicable empty/loading/error/approval states.

## Non-goals and active increment

State what is excluded, why, and activation conditions for any deferred work. A future idea is not current authority.

## Exact rules

Specify applicable semantics, ordering, identities, permissions, retries, time windows and tie-breaks. Mark irrelevant items not applicable with a reason.

## Design, data and ownership

Describe source/state ownership, boundaries, schemas/interfaces, compatibility, access, sensitive-data handling, retention/deletion and external dependencies where applicable. Put binding choices beside the relevant design sections.

## Architecture ambiguity checklist

Complete this for architectural drafts, reviews, amendments and revisions. Follow [[Jobs/Propose or Review a Plan]].

| Decision boundary | How an implementing agent could drift | Explicit direction and section | Owner / verification | Status |
| --- | --- | --- | --- | --- |

Statuses: **Resolved / Deferred outside active increment / Needs decision**. Resolve or explicitly exclude every consequential active-increment choice before implementation readiness; Needs decision means not ready. Deferred work needs an activation condition. The table indexes binding directions in the design; it does not replace them. Keep routine compatible methods flexible.

Consider relevant lenses: outcome versus methods; decision/state ownership; interaction entry/target binding; schemas/identities; context storage/retrieval/correction/forgetting; models/access/spending; failure/recovery/Stop; scope/order; migration/compatibility; finite acceptance/rollback.

## Requirements and acceptance

Separate required-before-delivery, later follow-up and future work. Use finite Given / When / Then criteria tied to evidence; future scope does not enter the active increment automatically.

## Risks, vulnerabilities and mitigations

| Lens | Risk / overlooked case | Impact | Mitigation | Verification |
| --- | --- | --- | --- | --- |

Cover applicable semantics/outcome; model correctness; data/migration/retention; security/privacy/abuse; concurrency/retries/time zones; provider costs/timeouts; performance/accessibility; parallel ownership/integration/rollback. Explain not-applicable lenses briefly.

## Benefits, costs and alternatives

What improves? What complexity, maintenance, time or access cost is added? Could an existing source or smaller sequence achieve the same outcome? Record alternatives and reasons.

## Dependencies, ownership and sequence

Name actual workstream/files, required context, necessary locks, compatibility order and any separately authorized external actions. Do not create resources merely to fill the section.

## Verification, delivery and rollback

Specify proportionate checks, actual user/deliverable acceptance, safe test inputs, observation/evidence, staged delivery and finite rollback/recovery. Distinguish local readiness from integration, installation and final acceptance.

## Open questions

Separate blocking and non-blocking questions, each with an owner. A blocking active-increment choice keeps the plan not ready.

## Recommendation

Precise amendments or readiness recommendation and the next human approval boundary.

## Cross-agent review log

Append only when saving is authorized. Each entry records timestamp/timezone, reviewer/model, workstream, exact immutable revision, Accept/Amend/Reject and readiness, benefits, costs, gaps, stronger opportunities, efficiency, security/privacy, usability, mitigations, revision outcome and blockers. Use the plan Job's full review lenses.

## Revision history

| Revision | Timestamp / author | Material change | Approval reference |
| --- | --- | --- | --- |

## Required user-facing response close

Full analysis → **Simple summary** in everyday language → **Propose next steps to get started**, **Submit/save the proposed plan and do nothing else**, or **Custom prompt / direction**. Do not imply this proposal is approved or implemented.
