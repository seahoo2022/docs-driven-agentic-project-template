# LOGGING

## Purpose
Define logging and debugging rules.

## Logging goals
- Keep runtime observability useful.
- Avoid giant unreadable logs as the first debugging entrypoint.
- Prefer compact summaries for agent consumption.

## Preferred debugging entrypoints
- `runtime/debug_snapshot.txt`
- `runtime/health_summary.json`
- `runtime/last_error.txt`

## Raw log policy
For raw logs:
1. inspect file size and line count
2. read the last 100 lines first
3. search for relevant markers
4. inspect only small local windows
5. do not read large logs in full by default

## Logging expectations
- Keep logs structured where possible.
- Separate normal operational logs from error summaries when practical.
- Prefer rotating logs over unbounded growth.

## Notes
-