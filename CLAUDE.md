# Roblox Game Development — Project Rules

## Source of truth
- The repository, current Git state, approved design docs, task records, audit reports, and recorded test evidence outrank remembered chat summaries.
- At session start, inspect the root, `git status`, current branch, Rojo config, task ledger, relevant task file, latest audit, and latest evidence before acting.
- Treat `docs/PROJECT_CONTEXT.md` as a provisional transcript summary. Re-verify every status against the actual checkout before relying on it.
- Preserve established architecture, task IDs, conventions, and user changes. Do not create duplicate ledgers or docs if equivalent ones already exist.

## Design control
- Ask concise multiple-choice questions for unresolved, material design choices. Support multi-select, Other, Not sure (recommend and explain), and defer where safe.
- Never silently decide gameplay, economy, feature scope, architecture, or monetization questions that materially affect the approved design.
- Keep approved choices in the existing GDD / decision log. Do not re-ask settled decisions.
- Do not create or generate visuals, mockups, UI styling, maps, models, textures, VFX, icons, or animations without a user-supplied or explicitly approved reference. A game title alone is not visual approval.
- If no approved visual reference exists, stop only the visual part, ask how to proceed, and continue nonvisual engineering where safe.

## Task workflow
1. Identify the task ID, approved requirements, dependencies, and acceptance criteria.
2. Verify the active repo root, branch/worktree, and clean/dirty state before editing.
3. Resolve user decisions before implementing dependent behavior.
4. Make the smallest coherent change on the intended task branch/worktree.
5. Run the fastest relevant checks first, then specs, Rojo build, and Studio tests appropriate to the change.
6. Record exact evidence: command, result, environment, client count, and anything not tested.
7. Request an independent audit where the task workflow requires one. Fix blocking/major findings and re-run affected checks.
8. Merge only from a confirmed intended checkout and only after the required approval/audit gate. Re-check root, branch, and status immediately before any merge.
9. Re-verify on the target branch after merge before marking the task done.

## Git safety
- Before `switch`, `merge`, `rebase`, `cherry-pick`, `reset`, `clean`, commit, push, or branch deletion: show/inspect `pwd`, `git rev-parse --show-toplevel`, `git branch --show-current`, and `git status --short`.
- Never assume the current directory is the intended checkout. Prefer explicitly anchored paths after verifying them.
- If a task or merge directory is missing, stale, or was cleaned up, stop and re-discover the correct checkout. Never fall back to running the operation in whatever directory remains.
- Never discard unrelated edits, reset user work, force-push, delete untracked files, auto-commit, or push without explicit authorization.
- Do not mark a task Done before its required audit, merge, post-merge checks, evidence, and documentation updates are complete.

## Roblox / Luau engineering
- Use the existing Rojo mappings, module conventions, dependency setup, formatter, linter, and tests. Inspect before proposing a framework or reshaping architecture.
- Keep gameplay authority on the server. Validate client requests and all privileged state changes server-side, including movement abilities, damage, rewards, inventory, trading, purchases, and progression.
- Handle failure states, respawns, joins/leaves, cleanup, persistence errors, race conditions, and RemoteEvent abuse appropriately.
- Do not claim Studio, MCP, static analysis, specs, or multiplayer tests ran unless they actually ran. Label what remains unverified.

## Test and release truth
- Report separately: implemented, Rojo build passed, static checks passed, specs passed, solo Studio tested, multiplayer tested, independent audit passed.
- The shared history identifies anti-cheat hardening (including teleporting back to the deck after knock-off) as unfinished. **Do not declare public-play readiness until the current task record proves this is resolved, audited, and tested.** Re-verify status first.
- On the recorded 8 GB Mac, three Studio clients were the practical limit in one test and memory fell very low. Use targeted single-client tests by default; use multi-client testing only when the scenario requires it, configure timeouts, and record limits.
- Telemetry was described as server-output-only and pseudonymous (`P1`, `P2`, faction; no names/IDs; no external sending). Preserve that privacy posture unless the user explicitly approves a change.

## Communication
- Give concise task updates with: changed, checked, results, evidence/doc path, remaining risk, next approval required.
- Distinguish facts from inference. Never fabricate metrics, build hashes, evidence, audit results, or test outcomes.
- Use the existing task/audit system; do not add process overhead unless it solves a demonstrated failure.
