# Repository Instructions

This repository provides public-safe Claude Routine templates and reusable Claude skills.

## Core behavior

When using this repo for a routine:

- prefer compact, action-focused reports;
- avoid generic newsletters;
- use source-first research;
- label uncertainty;
- preserve a compact JSON state block at the end of each report;
- never include private secrets in generated commits;
- keep public files generic.

## Safety rule

Do not commit user-specific operational details to this public repository. Treat private context as runtime configuration supplied by the routine prompt, a private connector document, or a private fork.

Avoid committing:

- API keys or tokens;
- hostnames, IP addresses, or network maps;
- exact installed service versions;
- exposed services;
- personal hardware inventory;
- private price thresholds;
- personal account identifiers;
- client or employer data;
- real Google Drive file or folder IDs;
- real routine-state output from private reports.

## Reporting style

Use Ponytail for scope:

- skip what does not need to exist;
- search only when a trigger exists;
- one normal item gets one source;
- important items may get more sources;
- quiet days should stay short.

Use Caveman for wording:

- short lines;
- no filler;
- no duplicate explanation;
- use compact operational items.

Preferred item format:

```text
[severity evidence] Subject — Change. Impact. Next step. Source.
```

## Routine model guidance

Default:

- Daily routine: fast/low-cost model.
- Weekly routine: balanced model.

Escalate only when the routine finds a high-severity or decision-impacting item.
