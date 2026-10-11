# Transcript-Derived Task Ledger (Reconcile Before Use)

This is **not** a replacement for the current repository's authoritative ledger. It is a checklist to make sure the first audit reconciles what was said in the shared history with the real records.

| Item | State reported in shared history | Required reconciliation |
|---|---|---|
| N1 Dash guard | Reported closed; seated Dash rejected; force cap result recorded; evidence committed | Find the real playtest note/commit and verify it is linked correctly. |
| TASK-0003 — Factions + Echo Clone | Reported implemented and merged; pressure plate and 6-second clone behavior measured | Confirm merge commit, specs, Studio evidence, and final task status. |
| TASK-0004 | Described as approved in one update | Find task and verify approved/closed status. |
| TASK-0005 — design calls | Three design decisions reportedly awaiting the user | Locate the exact questions and ask only those still unresolved. |
| TASK-0007 | Described as re-audited and merged; no blocking/major findings | Verify audit report and merge commit; inspect deferred items. |
| TASK-0008 — telemetry | 64 specs passed; solo Studio output observed; an update said independent audit was in progress and merge was conditional on audit | Determine actual audit/merge status from current branch and records. Do not assume either pending or complete. |
| TASK-0010 — follow-up / anti-cheat | Described as the destination for deferred audit items including anti-cheat hardening | Verify if task exists, was approved, started, completed, audited, and merged. Treat anti-cheat as public-release blocker until evidence says resolved. |
| EXP-0001 | Still waiting on user/design decision in shared history; median time to first power use under 60 seconds mentioned | Read the actual experiment brief and present outstanding choices in multiple-choice format. |
| LES-0004 / build hash / playtest note | A documentation update was requested for overstated certainty, a wrong build hash, and a note link that did not yet exist | Verify current docs and evidence; never invent or guess a commit/build hash. |

## Reconciliation rules
- If transcript and repo conflict, the repo's latest verified state wins, but report the mismatch.
- If task status differs across a ledger, branch, commit, and audit, do not guess: inspect the commit graph and report what is missing.
- A green test run does not itself mean the feature was audited, merged, or released.
