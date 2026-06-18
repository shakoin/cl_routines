# Private Routine Configuration Example

Copy this file to `config.local.md` or keep equivalent details in the Claude Routine UI prompt or a private connector document.

Do not commit your real private values to a public repo.

## User context

```yaml
user_context:
  role: "<your role>"
  interests:
    - "<topic>"
    - "<topic>"
```

## Stack watchlist

```yaml
stack_watchlist:
  services:
    - name: "<service name>"
      version: "unknown"
      exposure: "internal|external|unknown"
  infrastructure:
    - "<platform or device>"
```

## Hardware watchlist

```yaml
hardware_watchlist:
  - item: "<hardware item>"
    interesting_under: "<price>"
    strong_buy_under: "<price>"
```

## Model watchlist

```yaml
model_watchlist:
  current_delegate: "<model name>"
  target_tasks:
    - summarize
    - classify
    - triage
```

## Report destination

```yaml
report_destination:
  drive_folder_name: "Tech Digests"
```

## Feedback rules

```yaml
feedback_rules:
  - "Skip routine market moves unless they are material."
  - "Skip rumors unless they affect a watch item."
```
