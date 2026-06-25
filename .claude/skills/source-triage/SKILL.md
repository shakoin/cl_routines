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

## Retry rule

On source fetch failure:

1. Retry once.
2. If still failed, record a partial failure (source name, stage, whether report is still usable, whether tomorrow should retry).
3. Continue the report — do not abort.
4. Do not mark the beat as quiet.

## Partial failure format

```
PARTIAL FAILURE — [source] failed at [stage]. Report usable: yes/no. Retry tomorrow: yes/no.
```

## Failure rule

Never write `No notable updates` for a beat if the main source failed. Write a short failure note instead.

## Search rule

Prefer primary fetches. Use broad web search only when a trigger exists or a primary source is unavailable.

## Primary source registry

Fetch-first rule: for any configured beat, fetch the canonical primary source DIRECTLY (WebFetch) before running a broad WebSearch. Web search is for discovery/confirmation, not as the default source. A direct fetch of an authoritative page beats search-result luck on recall and accuracy.

Use these canonical primaries when the beat applies. Treat each as `primary` evidence.

### Security / CVE
- CISA Known Exploited Vulnerabilities — page `https://www.cisa.gov/known-exploited-vulnerabilities-catalog`; JSON feed `https://www.cisa.gov/sites/default/files/feeds/known_exploited_vulnerabilities.json` (diff against prior state's KEV list).
- NVD `https://nvd.nist.gov/vuln/search`; GitHub Security Advisories `https://github.com/advisories`.
- Vendor security/status pages for any affected product (fetch the vendor's own advisory before secondary reporting).

### Macro / markets
- FRED `https://fred.stlouisfed.org` (series pages for 10Y/2Y, DXY, etc.); US Treasury `https://home.treasury.gov/resource-center/data-chart-center/interest-rates`.
- Federal Reserve `https://www.federalreserve.gov`; BLS `https://www.bls.gov`; CME FedWatch for rate-path expectations.

### AI / developer tools
- Official vendor blog / changelog / release notes pages (fetch the changelog directly, not a news rewrite).

### Homelab stack (public OSS — release/security pages)
Fetch the relevant component's release page directly when it is on the configured stack watchlist:
- Proxmox VE roadmap/release `https://pve.proxmox.com/wiki/Roadmap`
- Plex release notes `https://forums.plex.tv/t/plex-media-server/30447`
- Sonarr / Radarr / Prowlarr / Bazarr — GitHub releases (`https://github.com/<project>/<project>/releases`)
- FileFlows `https://fileflows.com/docs/versions`
- Pi-hole / FTL — GitHub releases (`https://github.com/pi-hole/*/releases`)
- gluetun — GitHub releases (`https://github.com/qdm12/gluetun/releases`)
- Omada / TP-Link firmware — official download/firmware page for the specific model.

Registry rule: if a primary fetch fails, apply the Retry rule and record a partial failure for that beat — do not silently fall back to search and label the beat quiet.
