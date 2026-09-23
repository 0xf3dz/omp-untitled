# OMP Untitled Metrics

This OMP extension shows Untitled Auto routing metrics for the current OMP session.

## Requirements

- OMP
- Untitled Auto on macOS
- An OMP OpenAI Codex provider that sends requests through the local Untitled relay

## Install

Install the extension from GitHub:

```bash
omp plugin install github:0xf3dz/omp-untitled-metrics
```

For local development, install the repository path:

```bash
omp plugin install ~/Documents/dev/omp-untitled-metrics
```

Restart OMP after installation.

## Use

- The OMP status bar shows the routed model, request count, workload savings, and capacity estimate for the current session.
- Run `/untitled` to show or hide all extension output.
- Run `/untitled details` to show or hide the detail panel.

Exact token savings need a paired Sol comparison. The extension shows `—` when that comparison does not exist.

## Integrate with the OMP status bar

Add the `status` segment and disable the separate hook-status line:

```yaml
statusLine:
  preset: custom
  showHookStatus: false
  leftSegments:
    - pi
    - model
    - mode
    - collab
    - usage
    - status
    - path
    - git
    - pr
  rightSegments:
    - session_name
```

Restart OMP after the change.

## Data source

The extension reads the local Untitled telemetry log. It checks these sources in order:

1. `UNTITLED_SUBSCRIPTION_LOCAL_LOG`
2. `~/Library/Application Support/Untitled Router/config/relay.env`
3. `~/Library/Application Support/Untitled Router Data/subscription.jsonl`

The extension does not send network requests.
