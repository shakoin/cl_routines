---
name: routine-state
description: Maintain compact JSON state for recurring Claude routines.
---

# Routine State

Use this skill for scheduled reports that need memory between runs.

## Goal

Each report should include a small JSON state block. The next run reads that block first, then dedupes against it.

## State block

Place this near the end of generated HTML reports:

```html
<script type="application/json" id="routine-state">
{
  "date": "YYYY-MM-DD",
  "generated_utc": "YYYY-MM-DD HH:MM UTC",
  "routine": "routine name",
  "run_mode": "quiet|normal|escalated",
  "actions": [],
  "decisions": [],
  "watch": [],
  "urls": [],
  "items": [],
  "failures": [],
  "next_check": [],
  "feedback_rules": []
}
</script>
```

## Read behavior

At the start of a run:

1. Find the newest prior report.
2. Read only the `routine-state` block if it exists.
3. Do not reread the full report unless state is missing or invalid.
4. Build dedupe sets from actions, decisions, watch items, URLs, and item names.

## Candidate labels

Classify candidate items as:

- new;
- updated;
- still watching;
- resolved;
- repeated/no change;
- skip.

Do not repeat an item unless it changed.

## Public safety

Do not commit real private state output to a public repo. Keep real state in generated reports or private storage.
