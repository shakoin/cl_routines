# Setup Guide

This guide explains how to use this public template repo with Claude Code Routines.

## 1. Connect the repo

In Claude Code / Claude Routines, select this repository as the routine repo.

The repo provides:

- `CLAUDE.md` repository instructions;
- reusable skills in `.claude/skills/`;
- daily and weekly launcher prompts in `routines/`.

## 2. Add private context outside the public repo

Do not commit private operational details here.

Put private context in one of these places:

- the Claude Routine UI prompt;
- a private Google Drive config document;
- a private fork;
- a local ignored file such as `config.local.md`.

Use `briefing/user-context.example.md` and `briefing/config.example.json` as templates.

## 3. Create the daily routine

Suggested name:

```text
Daily Tech Scout
```

Suggested model:

```json
{
  "model": "haiku",
  "effortLevel": "low",
  "fallbackModel": ["sonnet"]
}
```

Suggested schedule:

```text
Daily, morning local time
```

Prompt:

Use `routines/daily-tech-scout.prompt.md` as the base. Add private context below it in the Claude Routine UI.

## 4. Create the weekly routine

Suggested name:

```text
Weekly Tech Deep Sweep
```

Suggested model:

```json
{
  "model": "sonnet",
  "effortLevel": "low",
  "fallbackModel": ["haiku"]
}
```

Suggested schedule:

```text
Weekly, weekend morning
```

Prompt:

Use `routines/weekly-tech-deep-sweep.prompt.md` as the base. Add private context below it in the Claude Routine UI.

## 5. Connect report storage

If using Google Drive:

- enable the Google Drive connector for the routine;
- choose a destination folder name in the routine prompt;
- remember that many connectors are create-only for HTML outputs, so old reports may need manual cleanup.

## 6. Test manually

Before relying on schedules:

1. Run the daily routine manually.
2. Check the run transcript.
3. Confirm the report was saved.
4. Confirm the report includes a `routine-state` block.
5. Confirm quiet days stay short.
6. Confirm no private config was committed to the repo.

## 7. Tune feedback rules

When reports include noise, add feedback rules in private runtime context, for example:

```yaml
feedback_rules:
  - "Skip routine market moves unless material."
  - "Skip rumors unless they affect an active watch item."
  - "Only include hardware if it crosses my configured threshold."
```
