# Public Safety Checklist

This repository is intended to be safe as a public template.

Keep it generic.

## Safe to commit

- generic routine prompts;
- generic Claude skills;
- report structure;
- severity labels;
- evidence labels;
- source-budget rules;
- example config with placeholders;
- setup docs.

## Do not commit

- API keys;
- OAuth tokens;
- GitHub tokens;
- Google tokens;
- SSH keys;
- passwords;
- real hostnames;
- real IP addresses;
- private network maps;
- exact installed versions;
- exposed services;
- personal hardware inventory;
- exact model inventory;
- personal buying thresholds;
- account identifiers;
- client or employer information;
- real Google Drive IDs;
- real generated reports;
- real routine-state blocks from private reports.

## Public/private split

Use this public repo for reusable logic.

Use private runtime configuration for user-specific details.

Good public pattern:

```text
Watch configured stack for important security issues.
```

Avoid public pattern:

```text
Watch these exact services, versions, hostnames, and exposed endpoints.
```

## Before making changes public

Search for:

- names;
- emails;
- usernames;
- hostnames;
- IP addresses;
- product serials;
- exact versions;
- API keys;
- tokens;
- private URLs;
- generated reports.

If unsure, keep the file private.
