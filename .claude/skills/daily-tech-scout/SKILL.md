---
name: daily-tech-scout
description: Produce a compact low-usage daily technology, security, news, and market scout report.
---

# Daily Tech Scout

Use this skill for a daily recurring report.

## Mission

Create a short operational brief, not a newsletter.

Answer:

1. Do I need to act today?
2. Did anything affect the configured stack, tools, workflow, security risk, hardware/model plans, or macro context?
3. Did any source fail?
4. What should carry forward?

## Execution stages

Run in this order:

1. Load prior state block.
2. First-pass source check (quiet scout mode).
3. Escalate only if an S2/S3 trigger appears.
4. Write compact report — omit or collapse empty sections.
5. Save to configured report destination.
6. Save state block.

## Default mode

Start in quiet scout mode.

Deepen research only if an S2/S3 trigger appears.

## Required sections

Use these sections:

1. Bottom Line
2. Top Brief
3. Stack / Security
4. AI / Technology
5. Macro / Markets
6. Hardware / Model Watch
7. State / Failures

## Output limits

- Bottom Line: 1 sentence.
- Top Brief: max 5 items.
- Each section: max 3 bullets.
- Hardware / Model Watch: max 4 rows.
- State / Failures: max 6 lines.

## Empty section rule

If a section has no S1/S2/S3 item and no source failure, omit it entirely or collapse it to one quiet line.

If all sections are quiet, produce a short all-clear report instead of the full structure.

## Quiet default lines

Use short quiet lines when nothing matters:

- `No action needed today.`
- `No stack or security item requiring action today.`
- `No AI or technology update requiring action today.`
- `Market tone: Quiet.`
- `No hardware or model item crossed a configured threshold.`
- `No source failures.`

## Report format

Generate one self-contained dark-mode HTML report.

Include a compact `routine-state` block.

Save to the configured report destination.

## Public template note

This skill is generic. Private stack details, thresholds, and watchlists should come from runtime configuration, not this public repo.
