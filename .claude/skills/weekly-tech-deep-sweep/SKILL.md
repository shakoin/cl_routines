---
name: weekly-tech-deep-sweep
description: Produce a bounded weekly deep sweep and cleanup recurring routine state.
---

# Weekly Tech Deep Sweep

Use this skill for a weekly recurring report.

## Mission

Do the deeper checks the daily scout skips.

Focus on:

- stack and security changes;
- AI and developer-tool changes;
- model candidates worth testing;
- hardware prices crossing configured thresholds;
- infrastructure, firmware, and release changes;
- broader technology, cybersecurity, policy, and market context;
- watchlist cleanup.

## Required sections

1. Bottom Line
2. Weekly Top Brief
3. Decisions Updated
4. Stack / Security Deep Sweep
5. AI / Technology Deep Sweep
6. Hardware / Model Candidate Watch
7. Optional Interest Areas
8. Macro / Markets Weekly View
9. Watchlist Cleanup
10. Skipped / Failures
11. Routine State

## Output limits

- Weekly Top Brief: max 8 items.
- Each major section: max 5 bullets.
- Hardware/model table: max 8 rows.
- Watchlist cleanup: max 10 rows.

## Watchlist cleanup

For each watch item, decide:

- keep;
- drop;
- resolved;
- still watching.

Do not carry stale items forever.

## Report format

Generate one self-contained dark-mode HTML report.

Include an updated compact `routine-state` block.

Save to the configured report destination.

## Public template note

This skill is generic. Private context and exact watchlists should come from runtime configuration or private storage.
