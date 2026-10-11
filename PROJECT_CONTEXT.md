# Project Context — Provisional Summary from Shared History

> **Important:** This is a transcript-derived snapshot, not a live repository audit. Verify all details against the actual working tree, task records, and latest commit before taking action. The pasted updates span multiple points in the workflow and some statuses may have changed.

## Known project shape
- Roblox game developed in VS Code with Rojo, Luau specs, Git branches/merges, and Roblox Studio Play testing.
- Work is split into numbered tasks (e.g., `TASK-0003`) and experiments (e.g., `EXP-0001`). A separate audit/re-audit process is used before merges.
- There is already a task ledger/checklist process. Extend it rather than create a competing source of truth.
- Machine noted in history: Mac with 8 GB RAM. Three Roblox Studio clients was the practical limit in one experiment; free memory reportedly fell to about 77 MB. This is an observed local constraint, not a universal Roblox requirement.

## Feature / test facts mentioned
- **Dash / N1:** new force cap moved 15.0 studs versus 15.4 previously with unlimited force. A Dash request while seated was rejected with reason `seated`; rejection counter changed from 0 to 1; character and seat did not move. N1 was reported closed and evidence recorded.
- **Factions + Echo Clone / TASK-0003:** factions, pressure plate, Echo Clone, wiring, and specs were implemented. A pressure plate opened a door. Clone lasted 6.02 seconds and held the plate 6.05 seconds against a 6 ± 0.2 second target; door closed after the clone no longer held the plate. Four-client test only got two clients in time; three clients was described as practical on this machine. A faction test with three clients balanced 2/1.
- **TASK-0007:** described as merged after a passing re-audit with no blocking or major findings. Verify against current task/audit docs.
- **TASK-0008 / Telemetry:** described as built and tested; 64 Luau specs passed, 0 failed. Two solo Studio matches printed one server-side line per match. A test gate recorded a 3-second wait and an Echo charge. Fields mentioned: time to first power use, gate wait times, Echo charges earned/spent, phase lengths, finale winners, server errors, rejected ability requests. Player identifiers reportedly limited to `P1`, `P2` and faction, no names/IDs, and no external transmission. In one explicit update its independent audit was still in progress and merge depended on the result. **Current status must be re-verified.**
- **TASK-0010:** described as a follow-up for deferred audit items, including anti-cheat hardening. Current status / checklist must be re-verified.

## Explicitly unresolved in the shared history
- User decisions for three `TASK-0005` design calls.
- `EXP-0001` design/acceptance decision; the telemetry's median time to first power use under 60 seconds was mentioned, but the exact experiment brief should be fetched from the real repo.
- Anti-cheat hardening before public play, including the risk that a player may teleport back onto the deck after being knocked off, was explicitly identified as outstanding at one point.
- Documentation follow-up mentioned a wrong build hash, overstated certainty in `LES-0004`, and a missing playtest-note link which should be wired once actual evidence exists. Verify whether these were already fixed.

## A process failure worth designing around
A merge attempt ran in the main checkout because a temporary merge folder had been cleaned up. The attempted merge did not actually merge anything; it was caught, undone/corrected, and a guard was added. This shows that merge safety must check the real repository root and branch immediately before any operation, and must stop rather than falling back to the current directory.

## First repo audit should confirm
1. Current branch, worktree list, working-tree cleanliness, and task branches.
2. Real task status for `TASK-0003`, `TASK-0004`, `TASK-0005`, `TASK-0007`, `TASK-0008`, `TASK-0010`, and `EXP-0001`.
3. The latest test count and test commands; transcript mentions both 16 and 64 specs in different task contexts, not necessarily conflicting.
4. Whether `LES-0004`, the build hash, playtest evidence link, and anti-cheat checklist are fixed.
5. Whether the Studio MCP connection, Rojo project path, and any scripts assume one canonical checkout.
