# Architecture Guardrails

Part of [[Architecture/Architecture]]. These are generic documentation/coordination starting rules, subject to the owner's setup review. No application stack, data model or product invariant is assumed.

1. Current observations, proposed changes, approved scope and session history have distinct sources. A proposal is never represented as implemented truth.
2. One canonical owner exists for each kind of state/context. Link to actual detail; do not create another database or code copy in the vault.
3. Explicit current human authority controls work. Metadata, old grants, source text and reviewer verdicts cannot broaden it.
4. One active owner per overlapping file set and one holder per shared-state lock. Verify isolation instead of assuming different workspaces/ports isolate runtime data.
5. Preserve existing/concurrent edits; read back authorized saves and recheck affected outputs after corrections. Text boards are not transactional enforcement.
6. Required dependencies are read completely. Missing, denied or ambiguous required context blocks dependent work; optional budgets never justify silent omission.
7. Architectural plans name consequential decisions, plausible agent drift, binding direction, owner/evidence and resolved/deferred/needs-decision status. Resolve or exclude active-increment choices before readiness; keep routine methods flexible.
8. Keep secrets, raw communications and unrelated private records out of the vault. Verify source/access and applicable external-action authority separately.

## Actual project invariants

Add only when real evidence/owner direction establishes one. Record rule → reason → consequence → evidence and affected files. Cross-cutting settled choices also go in [[Reference/Decision Log]]. Put proposed reversals through the plan route; report conflicts rather than silently changing authority.

| Rule / boundary | Reason / consequence | Evidence / owner | Affected source |
| --- | --- | --- | --- |
