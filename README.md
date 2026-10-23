# release-readiness-report
Consolidated release readiness checklists and report for the service platform go/no-go review

## Contents

- `checklists/` — the five service owners' readiness checklists for the 2026-10-17 cut (unedited originals)
- `reports/release_readiness.csv` — the consolidated go/no-go summary

## Summary

| service | owner | result | detail |
| --- | --- | --- | --- |
| auth-service | Priya Raman | GO | clear |
| billing-service | Tomas Novak | NO-GO | open blockers |
| edge-proxy | Aisha Bello | GO | clear |
| payments-service | Dana Whitfield | NO-GO | test run not green |
| search-service | Sofia Rossi | GO | clear |

**Tally: 3 GO / 2 NO-GO.**

Rule applied: a service is GO when its latest test run is green AND it has zero open blockers; everything else is NO-GO.

### NO-GO detail

- **billing-service (Tomas Novak)** — latest test run #1907 is GREEN, but 2 open blockers remain: BL-1041 (invoice PDF shows duplicate line on refunds) and BL-1044 (EU tax rounding drift). Both are still under review with no fix merged.
- **payments-service (Dana Whitfield)** — run #5560 is RED (3 unit / 2 integration failures) with 0 open blockers. Card-network sandbox flakiness was suspected, but the same failures reproduced twice.
