# OMP Untitled Metrics

This OMP extension shows Untitled Auto routing metrics for the current OMP session.

## Requirements

- OMP
- Untitled Auto on macOS
- An OMP OpenAI Codex provider that sends requests through the local Untitled relay

## Install

Run the remote installer:

```bash
curl -fsSL https://raw.githubusercontent.com/0xf3dz/omp-untitled/main/install.sh | bash
```

The installer:

- Installs the plugin from `github:0xf3dz/omp-untitled`.
- Adds the extension status to the main OMP status bar.
- Disables the separate hook-status line.

Restart OMP after installation.

## Use

- The OMP status bar shows the routed model, request count, workload savings, and capacity estimate for the current session.
- Run `/untitled` to show or hide all extension output.
- Run `/untitled details` to show or hide the detail panel.

Exact token savings need a paired Sol comparison. The extension shows `—` when that comparison does not exist.

## Data source

The extension reads the local Untitled telemetry log. It checks these sources in order:

1. `UNTITLED_SUBSCRIPTION_LOCAL_LOG`
2. `~/Library/Application Support/Untitled Router/config/relay.env`
3. `~/Library/Application Support/Untitled Router Data/subscription.jsonl`

The extension does not send network requests.
