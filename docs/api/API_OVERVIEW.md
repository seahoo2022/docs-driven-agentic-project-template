# API_OVERVIEW

## Purpose
Describe the canonical interface surface between major system parts.

## Main interfaces
- Frontend to backend:
- Backend to storage:
- Backend to external services:
- Background workers to backend/runtime state:

## Canonical contracts
Detailed contracts should live in:
- `docs/api/CONTRACTS/`

## Change policy
If an interface changes:
- update the relevant contract doc
- update affected feature/design docs
- append the change to `docs/dev/DEV_LOG.md`

## Notes
-