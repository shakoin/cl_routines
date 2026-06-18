# Claude Routine Templates

Public-safe templates for Claude Code routines that produce compact recurring reports.

This repository is designed to be generic. Keep personal details, private infrastructure, exact service versions, API keys, account identifiers, and buying thresholds out of this public repo.

## What this repo contains

```text
.claude/skills/ponytail-caveman/SKILL.md
.claude/skills/routine-state/SKILL.md
.claude/skills/source-triage/SKILL.md
.claude/skills/daily-tech-scout/SKILL.md
.claude/skills/weekly-tech-deep-sweep/SKILL.md
routines/daily-tech-scout.prompt.md
routines/weekly-tech-deep-sweep.prompt.md
docs/setup.md
docs/public-safety.md
config.example.md
```

## Intended use

Use this repo as the instruction package for two Claude Code routines:

1. **Daily Tech Scout** — low-usage daily brief. Fast, compact, action-focused.
2. **Weekly Tech Deep Sweep** — broader weekly review and watchlist cleanup.

The routines are intentionally built around three ideas:

- **Ponytail**: skip work that does not need to exist.
- **Caveman**: say the same thing with fewer words.
- **State block**: carry forward compact JSON state instead of rereading full reports.

## Recommended private customization

Do not hardcode personal context in this repo if it is public. Put private details in one of these places instead:

- the Claude Routine UI prompt,
- a private Google Drive config document,
- a private repo fork,
- a local ignored config file based on `config.example.md`.

Private details can include:

- exact hostnames and IPs,
- exact installed versions,
- exposed services,
- hardware inventory,
- model inventory,
- price thresholds,
- personal watchlists,
- private Drive folder IDs,
- client or employer information.

## Safe public contents

Safe to keep public:

- general report structure,
- severity logic,
- evidence labels,
- source-budget strategy,
- state-block schema,
- generic daily/weekly prompts,
- setup notes.

## Quick setup

1. Connect this repo to Claude Code / Claude Routines.
2. Create a daily routine using `routines/daily-tech-scout.prompt.md`.
3. Create a weekly routine using `routines/weekly-tech-deep-sweep.prompt.md`.
4. Add private context in the routine UI prompt or a private config source.
5. Run the daily routine once manually and check the transcript.

See `docs/setup.md` for detailed steps.
