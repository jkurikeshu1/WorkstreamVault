# Proposed Plans

Part of [[{{Project Name}}]]. This is the authoritative plan resolver. It starts empty. Proposals are not observed behavior or permission to implement.

## Active plan registry

| Living plan | Status | Latest revision | Revision archive | Originating agent | Workstream | Created / updated | Branch / artifact |
| --- | --- | --- | --- | --- | --- | --- | --- |

## Latest and immutable revisions

Use the row's explicit **Latest revision** link. Verify it agrees with the living note's `revision`/`latest_revision_note` and the frozen snapshot's `snapshot_revision`. Never infer Latest from recency, filenames, chat or memory. A disagreement or missing snapshot blocks dependent work until resolved within authorized scope.

Create one stable living note per actual plan. On the first formal revision, create `Revisions/` and a complete `<Plan Name> — r1.md` snapshot; later snapshots increment by one. Keep every old snapshot unchanged. Saved reviews append to the living note, with change metadata; they do not consume a revision. Update every Latest pointer and revision index/history on a formal revision. See [[Jobs/Propose or Review a Plan]] and [[Templates/Proposed Plan Template]].

## Status meanings

`Draft → Proposed → Under Review → Approved → Implementing → Implemented`

- **Draft:** incomplete working proposal.
- **Proposed:** independently reviewable.
- **Under Review:** reviews/amendments in progress.
- **Approved:** only {{Owner}} explicitly approves an exact revision, with timestamp and source recorded in the living note/registry.
- **Implementing:** approved scope claimed and begun.
- **Implemented:** authorized delivery complete, verified and distilled into current sources, with merge/release evidence if applicable.
- **Rejected / Superseded:** retained history; no present authority.

Accept is a reviewer verdict, not approval. Direct narrow authority covers only its exact task, not a surrounding proposal. Never transfer approval silently to a revised snapshot.

## Review and convergence

Follow all applicable plan Job lenses and the architecture ambiguity table. Agent entry, plan Job and template require it. Every consequential active-increment choice is resolved or explicitly excluded before implementation readiness. No undocumented consequential assumption.

At most ten formal revisions per approval effort; aim to converge much sooner. Independent Accept closes deliberation for the owner decision unless material new evidence/direction reopens it. r10 without acceptance stops for the owner; never automatic r11. No cosmetic revision churn or budget reset to evade the ceiling.

## Revision history index

| Plan | Revision | Immutable snapshot | Timestamp / author | Approval reference / status |
| --- | --- | --- | --- | --- |

Add real revision rows only; retain historical rows. Keep review, implementation and delivery states distinct. Every user-facing plan response ends full analysis → Simple summary → the three choices in the plan Job.
