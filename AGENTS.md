# AGENTS.md

## Repository model

This repository uses doc-driven engineering.

Rules:
- one meaningful task = one primary documented subproblem
- one session should focus on one subproblem
- code and docs must evolve together
- root instructions should stay concise and route to more specific docs

This file is a workflow and routing file, not the full project memory.

---

## Progressive disclosure

Read project context in layers.

Default order:
1. `docs/INDEX.md`
2. `docs/prd/PRD_init.md`
3. `docs/dev/HANDOFF.md`
4. the primary subproblem doc
5. relevant architecture/API/local docs only if needed
6. code/runtime files only if needed

Do not scan the whole repository unless necessary.

---

## Documentation layout

- `docs/prd/` — product requirements
- `docs/architecture/` — technical rules and decisions
- `docs/api/` — canonical contracts
- `docs/dev/` — current execution state and continuity
- `frontend/designs/` — frontend subproblem docs
- `backend/features/` — backend subproblem docs
- `runtime/` — debugging summary files

Expected core docs:
- `docs/INDEX.md`
- `docs/prd/PRD_init.md`
- `docs/architecture/SYSTEM_OVERVIEW.md`
- `docs/architecture/CONVENTIONS.md`
- `docs/architecture/TESTING.md`
- `docs/architecture/LOGGING.md`
- `docs/api/API_OVERVIEW.md`
- `docs/dev/TODO.md`
- `docs/dev/HANDOFF.md`
- `docs/dev/DEV_LOG.md`

---

## Source-of-truth order

Use this order:

1. product docs
2. architecture docs
3. API docs
4. the primary subproblem doc
5. handoff
6. todo
7. dev log

If conflicts exist:
- prefer the higher-authority layer
- document the resolution in the relevant doc
- append a short note in `docs/dev/DEV_LOG.md`

---

## One-subproblem rule

Work on one primary subproblem at a time.

A primary subproblem usually corresponds to one of:
- `frontend/designs/<feature>.md`
- `backend/features/<feature>.md`
- one API doc
- one architecture doc

If a request spans multiple subproblems:
- choose the primary one
- complete that scoped task
- record additional work in `docs/dev/TODO.md`

---

## Read-before-work policy

Always read:
- `docs/INDEX.md`
- `docs/prd/PRD_init.md`
- `docs/dev/HANDOFF.md`
- the primary subproblem doc

Read more only when needed:
- relevant architecture docs
- relevant API docs
- local `AGENTS.md` files
- runtime summaries
- relevant source files

---

## Required documentation updates

After each meaningful task, update:
1. the primary subproblem doc
2. `docs/dev/DEV_LOG.md`
3. `docs/dev/HANDOFF.md`

Also update when needed:
- `docs/dev/TODO.md`
- API docs
- architecture docs
- testing/logging docs

Task completion requires both implementation and documentation updates.

---

## Subproblem doc structure

Use concise sections where relevant:
- Purpose
- Scope
- Constraints
- Relevant files
- Data / control flow
- Design
- Implementation notes
- Validation
- Open questions
- Change log

Append short dated change-log entries after meaningful updates.

---

## DEV_LOG rules

Append one entry per completed task to `docs/dev/DEV_LOG.md`.

Include:
- date
- subproblem
- summary
- files changed
- docs changed
- validation
- follow-up items

Keep entries short and factual.

---

## HANDOFF rules

Keep `docs/dev/HANDOFF.md` current.

It should include:
- current state
- most recent subproblem
- files touched
- unfinished work
- next recommended step
- risks / caveats

This file should let a fresh session continue quickly.

---

## Context efficiency

- keep context lean
- read only relevant docs and files
- avoid rereading large files
- prefer summaries over dumps
- treat logs as query targets, not reading material

---

## Log policy

Prefer:
- `runtime/debug_snapshot.txt`
- `runtime/health_summary.json`
- `runtime/last_error.txt`

For raw logs:
1. inspect size and line count
2. read the last 100 lines
3. search for relevant markers
4. inspect only small local windows

Never read large logs in full by default.

---

## Testing

Follow `docs/architecture/TESTING.md`.

Default:
- validate the smallest relevant scope first
- record what was tested
- if testing is skipped or incomplete, record it explicitly

---

## Missing docs

If a needed doc is missing:
- create the minimal correct doc
- place it in the correct folder
- keep it concise
- update `docs/dev/DEV_LOG.md`
- update `docs/dev/HANDOFF.md`

Do not leave key project state only in chat.

---

## Preferred task sequence

1. identify the one primary subproblem
2. identify the primary doc
3. read minimal relevant docs
4. implement
5. validate
6. update the primary doc
7. update `docs/dev/DEV_LOG.md`
8. update `docs/dev/HANDOFF.md`
9. record remaining work in `docs/dev/TODO.md`