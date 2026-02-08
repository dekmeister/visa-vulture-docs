---
layout: page
title: Configuration
nav_order: 4
date_created: 2026-02-08_12:00:00
date_modified: 2026-02-08_12:00:00
---

# Configuration

VISA Vulture is configured through a JSON file and CLI options.

## Configuration File

The default configuration is bundled with the application. To override it, pass a custom file:

```bash
visa-vulture --config path/to/config.json
```

### Key Settings

| Setting | Default | Description |
|---------|---------|-------------|
| `simulation_mode` | `true` | Use simulated instruments instead of real hardware |
| `log_level` | `"DEBUG"` | Logging verbosity (`DEBUG`, `INFO`, `WARNING`, `ERROR`) |
| `log_file` | `"equipment_controller.log"` | Log output file path |
| `poll_interval_ms` | `100` | Status polling frequency in milliseconds |
| `plot_refresh_interval_ms` | `1000` | Plot update rate in milliseconds |

### Validation Limits

Test plan values are checked against these limits before execution:

| Limit | Default |
|-------|---------|
| `voltage_max_v` | 100 |
| `current_max_a` | 50 |
| `power_min_dbm` | -100 |
| `power_max_dbm` | 30 |
| `frequency_min_hz` | 1 |
| `frequency_max_hz` | 50,000,000,000 |
| `duration_max_s` | 86,400 |

## CLI Options

| Option | Description |
|--------|-------------|
| `--simulation` | Force simulation mode on |
| `--config PATH` | Load a custom configuration file |
