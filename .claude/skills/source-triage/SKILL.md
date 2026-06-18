---
name: source-triage
description: Apply source budgets, evidence labels, severity scoring, and escalation rules for recurring reports.
---

# Source Triage

Use this skill when deciding what to research, how far to research, and how to label confidence.

## Source budget

Default budgets:

- quiet daily run: max 8 fetch/search actions;
- normal daily run: max 15 fetch/search actions;
- escalated daily run: max 25 fetch/search actions;
- normal weekly run: max 40 fetch/search actions;
- escalated weekly run: max 60 fetch/search actions.

Use fewer when possible.

## Evidence labels

Use compact labels:

- `primary` — official release, advisory, vendor page, government source, status page;
- `secondary` — reputable reporting with source links;
- `community` — forum, issue thread, or user report;
- `weak` — unclear source; do not put in top brief;
- `failed` — source failed; do not claim quiet status.

## Severity labels

- `S3` — action or verification needed now;
- `S2` — affects a decision;
- `S1` — watch only;
- `S0` — quiet.

## Escalation triggers

Escalate only when an item may affect:

- user safety or security;
- a running service or workflow;
- an active purchase or build decision;
- a major platform/tool dependency;
- a major macro or market signal;
- a prior unresolved watch item.

## Failure rule

Never write `No notable updates` for a beat if the main source failed. Write a short failure note instead.

## Search rule

Prefer primary fetches. Use broad web search only when a trigger exists or a primary source is unavailable.
