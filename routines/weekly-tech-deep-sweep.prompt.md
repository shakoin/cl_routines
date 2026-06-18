# Weekly Tech Deep Sweep Routine Prompt

Use this repository's instructions and skills:

- `ponytail-caveman`
- `routine-state`
- `source-triage`
- `weekly-tech-deep-sweep`

Run as a bounded weekly deep sweep.

Goal: do the checks the daily scout intentionally skips, then clean up state.

Focus on:

1. stack/security changes;
2. Claude, AI coding, and local AI changes;
3. model candidates worth testing;
4. hardware prices below configured thresholds;
5. infrastructure, kernel, virtualization, or firmware updates;
6. media automation and download ecosystem changes if configured;
7. networking and firmware changes if configured;
8. optional interest areas if configured;
9. cybersecurity, technology, policy, and market context;
10. watchlist cleanup.

Use Ponytail rules:

- do not research what does not affect action, decision, risk, or watchlist;
- do not pad quiet sections;
- prefer primary sources;
- keep the weekly report useful, not exhaustive.

Use Caveman rules:

- short, operational wording;
- no generic newsletter language;
- use compact item format:

```text
[severity evidence] Subject — Change. Impact. Next step. Source.
```

Read prior daily and weekly `routine-state` blocks from the configured report destination.

Create one self-contained dark-mode HTML report.

Save it to the configured report destination.

Recommended filename format:

```text
Tech Deep Sweep YYYY-MM-DD HHMM UTC.html
```

Include an updated compact `routine-state` JSON block at the bottom of the HTML.

After saving, respond only with:

```text
Folder: <configured destination>
Filename written: Tech Deep Sweep YYYY-MM-DD HHMM UTC.html
File id / link: <link or id>

Run notes:
- Prior daily state found: yes/no
- Prior weekly state found: yes/no
- Coverage limitations: none/list
- Watchlist items kept/dropped: n/n
- Drive note: connector is create-only; old reports remain and require manual pruning
```

## Private context

Add private values in the Claude Routine UI prompt or private storage, not in this public repo. Useful private values include:

- report destination folder;
- stack watchlist;
- hardware thresholds;
- model baseline;
- optional hobby/interest areas;
- weekly source list;
- feedback rules.
