# Daily Tech Scout Routine Prompt

Use this repository's instructions and skills:

- `ponytail-caveman`
- `routine-state`
- `source-triage`
- `daily-tech-scout`

Run as a low-usage daily scout.

Goal: produce a compact daily decision brief, not a newsletter.

Answer only:

1. Do I need to act today?
2. Did anything affect the configured stack, AI tools, local AI, hardware plans, cybersecurity risk, work, macro awareness, or market context?
3. Did any source fail?
4. What should carry forward?

Use Ponytail rules:

- skip what does not need to exist;
- do not deep scan unless an S2/S3 trigger appears;
- prefer primary sources;
- use one source for normal items;
- use up to three sources only for S2/S3 items;
- stop early on quiet days.

Use Caveman rules:

- short lines;
- no filler;
- no duplicate explanations;
- use this item format:

```text
[severity evidence] Subject — Change. Impact. Next step. Source.
```

Read prior state from the configured report destination if available.

Create one self-contained dark-mode HTML report.

Save it to the configured report destination.

Recommended filename format:

```text
Tech Scout YYYY-MM-DD HHMM UTC.html
```

Include a compact `routine-state` JSON block at the bottom of the HTML.

If nothing matters, say:

```text
No action needed today.
```

After saving, respond only with:

```text
Folder: <configured destination>
Filename written: Tech Scout YYYY-MM-DD HHMM UTC.html
File id / link: <link or id>

Run notes:
- Prior report found: yes/no
- Run mode: quiet/normal/escalated
- Coverage limitations: none/list
- Drive note: connector is create-only; old reports remain and require manual pruning
```

## Private context

Add private values in the Claude Routine UI prompt or private storage, not in this public repo. Useful private values include:

- report destination folder;
- stack watchlist;
- hardware thresholds;
- model baseline;
- news/market preferences;
- feedback rules.
