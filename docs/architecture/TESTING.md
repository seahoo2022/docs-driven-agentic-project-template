# TESTING

## Purpose
Define validation expectations.

## Test levels
- Unit tests
- Integration tests
- End-to-end tests

## Default policy
- Validate the smallest relevant scope first.
- Do not run the largest possible suite by default.
- Record what was tested.
- If validation is skipped, state why.

## Completion expectations
A task is not complete unless:
- the scoped change is implemented
- relevant validation is done or explicitly deferred
- validation status is recorded in:
  - the primary doc
  - `docs/dev/DEV_LOG.md`

## Notes
-