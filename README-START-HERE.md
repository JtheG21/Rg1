# Roblox + Claude Code Workflow Starter

This pack is an **additive workflow proposal** based on the project history shared in chat. It is not a claim that your local repository has been inspected or modified. Review it against the real repo before adopting it.

## What it optimizes for

- Feature work tracked by task IDs and explicit acceptance criteria.
- Branch-aware implementation, independent audits, evidence-backed playtests, and verified merges.
- Rojo + Luau + Roblox Studio as one development loop.
- A small, memory-aware test strategy for an 8 GB Mac.
- A research-first game design process and the rule that visuals require your approved references.
- Persistent decisions so Claude does not repeatedly ask settled questions or silently resolve open design calls.

## Start safely

1. In your existing repository, run `git status`, inspect its current `CLAUDE.md`, `.claude/`, `docs/`, Rojo config, task system, scripts, and tests.
2. **Do not overwrite existing files.** Diff this pack against them and merge the best parts. Keep your current task / audit conventions if they already work.
3. First add or adapt the root `CLAUDE.md` and documentation templates; do not add hooks, auto-merge scripts, auto-commit, or auto-push behavior yet.
4. Confirm the project commands from the actual repo. The commands recorded in `docs/PROJECT_CONTEXT.md` are observations from the shared history, not guaranteed current commands.
5. Run `/mcp` and `/context` in Claude Code to confirm active connections and loaded instructions. Use Roblox Studio's Manage MCP Servers / Quick Connect flow for Studio MCP if it is not already configured.
6. Run the preflight script with `bash scripts/preflight.sh` from this pack before any task work. It only reports state; it does not modify anything.

## Recommended adoption order

**P0 — safety and truth:** Git/checkout preflight, task ledger reconciliation, evidence integrity, release gate for anti-cheat.

**P1 — workflow quality:** concise root instructions, task-start / implementation / audit skills, a consistent task and playtest template.

**P2 — research system:** game research skill and a research log only after the implementation workflow is stable.

**P3 — automation:** only after manual workflow succeeds repeatedly, consider deterministic hooks for non-destructive checks. Require explicit review before installing hooks that can block tools or modify files.

## Current status caveat

The transcript snippets may be out of order and do not establish the current contents of your machine. Before using task status to make code or merge decisions, reconcile `git status`, branches, task docs, audit records, evidence notes, and the latest test results. `docs/TASK_LEDGER.md` intentionally labels statuses as needing re-verification where appropriate.

## Suggested handoff prompt

> Audit this starter pack against the existing repository. Do not overwrite files, change MCP settings, install packages, create visuals, run destructive Git operations, commit, or push. First report which proposed files already exist, which rules conflict with the current workflow, and a minimal adoption plan. Preserve the established task IDs, architecture, Rojo mappings, tests, audit process, and user changes. Ask me multiple-choice questions for unresolved design or architecture decisions.
