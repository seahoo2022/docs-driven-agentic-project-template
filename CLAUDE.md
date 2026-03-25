# CLAUDE.md

## Purpose

This repository uses a doc-driven engineering workflow.

The repository is designed so that:
- documentation is part of implementation
- each meaningful task maps to one documented subproblem
- each work session focuses on one subproblem only
- code changes must be accompanied by doc updates
- root instructions stay concise and route to more specific docs

This file is a routing and workflow file, not a full knowledge dump.

---

## Progressive disclosure

Do not load the whole repository into context.

Read information in layers:

1. global project intent
2. current working state
3. one subproblem doc
4. only then read additional architecture, API, code, or runtime files if needed

Prefer the smallest useful context.

---

## Documentation map

Use `docs/INDEX.md` as the main map of the documentation system.

Expected top-level doc roles:

- `docs/prd/`
  - product goals and scope
- `docs/architecture/`
  - cross-cutting technical rules and decisions
- `docs/api/`
  - canonical interface contracts
- `docs/dev/`
  - active project state and engineering continuity
- `frontend/designs/`
  - frontend subproblem docs
- `backend/features/`
  - backend subproblem docs
- `runtime/`
  - compact debugging entrypoints and runtime summaries

---

## Source-of-truth order

Use this priority order:

1. `docs/prd/PRD_init.md`
2. relevant docs in `docs/architecture/`
3. relevant docs in `docs/api/`
4. the primary subproblem doc for the current task
5. `docs/dev/HANDOFF.md`
6. `docs/dev/TODO.md`
7. `docs/dev/DEV_LOG.md`

If docs conflict:
- prefer the more authoritative layer above
- record the conflict and resolution in the most relevant doc
- add a short note to `docs/dev/DEV_LOG.md`

---

## One-subproblem rule

Each task must focus on one primary subproblem.

A subproblem should map to one primary doc, for example:
- `frontend/designs/<feature>.md`
- `backend/features/<feature>.md`
- one API contract doc
- one architecture doc for cross-cutting changes

If a request spans multiple areas:
- choose one primary subproblem
- complete that scoped task
- record remaining work in `docs/dev/TODO.md`

Do not mix unrelated subproblems in one implementation pass.

---

## What to read first

### Always read
- `docs/INDEX.md`
- `docs/prd/PRD_init.md`
- `docs/dev/HANDOFF.md`
- the primary subproblem doc for the current task

### Read additionally only if needed
- relevant architecture docs
- relevant API docs
- relevant local `AGENTS.md` in `frontend/` or `backend/`
- relevant runtime summary files
- relevant source files

Do not scan the full repo unless necessary.

---

## Required updates after each task

After each meaningful task, update:

1. the primary subproblem doc
2. `docs/dev/DEV_LOG.md`
3. `docs/dev/HANDOFF.md`

Update additionally if needed:
- `docs/dev/TODO.md`
- relevant API docs
- relevant architecture docs
- testing/logging docs

A task is not complete until both code and docs are updated.

---

## Required structure for subproblem docs

Each subproblem doc should stay concise and structured.

Use these sections where relevant:
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

Every meaningful implementation update should append a short dated change-log entry.

---

## DEV_LOG rules

Append one entry per completed task to `docs/dev/DEV_LOG.md`.

Each entry should include:
- date
- subproblem
- summary
- files changed
- docs changed
- validation
- follow-up items

Keep entries brief and factual.

---

## HANDOFF rules

`docs/dev/HANDOFF.md` must always reflect the current project state.

Update it with:
- current state
- most recent subproblem worked on
- files touched
- unfinished work
- next recommended step
- risks / caveats

This file should allow a new session to continue efficiently without reading long chat history.

---

## Context efficiency

Keep context lean.

- read only relevant docs and files
- avoid rereading large files
- prefer summaries over large raw outputs
- treat logs as query targets, not reading material
- do not pull large generated files into context by default

---

## Debugging and logs

Prefer these runtime entrypoints first:
- `runtime/debug_snapshot.txt`
- `runtime/health_summary.json`
- `runtime/last_error.txt`

For raw logs:
1. inspect size and line count
2. read the last 100 lines first
3. search for relevant markers
4. inspect only small local windows around relevant matches

Never read large logs in full by default.

---

## Testing

Follow `docs/architecture/TESTING.md`.

Default behavior:
- validate the smallest relevant scope first
- record what was validated
- if validation was skipped or deferred, state that explicitly in:
  - the primary subproblem doc
  - `docs/dev/DEV_LOG.md`

---

## Missing docs

If a required doc does not yet exist:
- create the minimal correct file
- keep it concise
- place it in the proper folder
- update `docs/dev/DEV_LOG.md`
- update `docs/dev/HANDOFF.md`

Do not leave important project state only in chat.

---

## Preferred task sequence

For each task:

1. identify the one subproblem
2. identify its primary doc
3. read the minimal relevant docs
4. implement the change
5. validate the change
6. update the primary doc
7. append to `docs/dev/DEV_LOG.md`
8. update `docs/dev/HANDOFF.md`
9. add any remaining work to `docs/dev/TODO.md`

---

## Completion criteria

A task is complete only when:
- the scoped implementation is done
- validation is done or explicitly deferred
- the primary subproblem doc is updated
- `docs/dev/DEV_LOG.md` is updated
- `docs/dev/HANDOFF.md` is updated