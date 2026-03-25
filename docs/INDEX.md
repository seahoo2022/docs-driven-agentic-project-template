# INDEX

## Purpose

This file is the documentation map for the repository.

Use it to decide:
- which docs are authoritative
- which doc should be the primary doc for a task
- which files to read first
- which docs must be updated after implementation

---

## Read order

For most tasks, read in this order:

1. `docs/prd/PRD_init.md`
2. `docs/dev/HANDOFF.md`
3. one primary subproblem doc
4. relevant architecture docs if needed
5. relevant API docs if needed
6. code or runtime files if needed

Do not read everything by default.

---

## Documentation areas

### Product
- `docs/prd/PRD_init.md`
  - product goals
  - target scope
  - major user-facing intent

### Architecture
- `docs/architecture/SYSTEM_OVERVIEW.md`
  - high-level system structure
- `docs/architecture/CONVENTIONS.md`
  - repository and engineering conventions
- `docs/architecture/TESTING.md`
  - testing expectations and validation rules
- `docs/architecture/LOGGING.md`
  - observability and log inspection rules

### API
- `docs/api/API_OVERVIEW.md`
  - overview of interfaces and contracts
- `docs/api/CONTRACTS/`
  - detailed canonical contracts

### Active development state
- `docs/dev/TODO.md`
  - pending work
- `docs/dev/HANDOFF.md`
  - current state for the next session
- `docs/dev/DEV_LOG.md`
  - implementation history

### Frontend subproblems
- `frontend/designs/`
  - one doc per frontend subproblem or feature

### Backend subproblems
- `backend/features/`
  - one doc per backend subproblem or feature

### Runtime debugging
- `runtime/debug_snapshot.txt`
  - compact debugging entrypoint
- `runtime/health_summary.json`
  - structured runtime summary
- `runtime/last_error.txt`
  - latest relevant error block

---

## Choosing the primary doc

### If the task is mainly UI / interaction
Use a doc under:
- `frontend/designs/`

### If the task is mainly service / endpoint / behavior
Use a doc under:
- `backend/features/`

### If the task is mainly interface contract
Use a doc under:
- `docs/api/`

### If the task is cross-cutting
Use a doc under:
- `docs/architecture/`

---

## Required updates after a task

After each meaningful task, update:
1. the primary doc
2. `docs/dev/DEV_LOG.md`
3. `docs/dev/HANDOFF.md`

Update additionally if needed:
- `docs/dev/TODO.md`
- API docs
- architecture docs

---

## Primary doc template guidance

A primary subproblem doc should usually contain:
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