# Project Template: Doc-Driven Full-Stack App

This repository is a reusable template for building apps with:
- frontend and backend
- agent-friendly documentation
- doc-driven task workflow
- handoff continuity across sessions

## Core idea

Each meaningful task should map to one documented subproblem.

Every task should:
1. read the minimal relevant docs
2. implement one scoped change
3. update the corresponding docs
4. append to the dev log
5. refresh the handoff

## Start a new project

1. Fill in `docs/prd/PRD_init.md`
2. Read:
   - `CLAUDE.md`
   - `AGENTS.md`
   - `docs/INDEX.md`
3. Scaffold the missing docs and the first task breakdown
4. Record the initial plan in:
   - `docs/dev/TODO.md`
   - `docs/dev/HANDOFF.md`

## Suggested first instruction to an agent

Read `CLAUDE.md`, `AGENTS.md`, and `docs/INDEX.md`. Based on `docs/prd/PRD_init.md`, scaffold the minimal architecture, API, and development docs for this repository, then propose the first subproblem breakdown in `docs/dev/TODO.md`.

## Core documentation

- `docs/INDEX.md` — doc map
- `docs/prd/PRD_init.md` — product goals
- `docs/architecture/` — cross-cutting rules
- `docs/api/` — canonical contracts
- `docs/dev/TODO.md` — pending work
- `docs/dev/HANDOFF.md` — current state for the next session
- `docs/dev/DEV_LOG.md` — implementation history

## Runtime debugging entrypoints

- `runtime/debug_snapshot.txt`
- `runtime/health_summary.json`
- `runtime/last_error.txt`