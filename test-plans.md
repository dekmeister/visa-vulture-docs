---
layout: page
title: Test Plans
nav_order: 3
date_created: 2026-02-08_12:00:00
date_modified: 2026-02-08_12:00:00
---

# Test Plans

Test plans are CSV files that define a sequence of instrument settings to apply over time. Each row represents a test step with a duration and setpoints.

## Overview

Every test plan CSV begins with a metadata comment specifying the instrument type:

```
# instrument_type: power_supply
```

or

```
# instrument_type: signal_generator
```

The remaining rows define the test steps as comma-separated values.

## Power Supply Test Plans

Columns: `duration`, `voltage`, `current`, `description` (optional)

```csv
# instrument_type: power_supply
duration,voltage,current,description
5.0,5.0,1.0,Warmup
10.0,12.0,2.0,Operating voltage
5.0,0.0,0.0,Power down
```

- `duration` — seconds to hold the setpoint
- `voltage` — volts
- `current` — amps
- `description` — optional label for the step

## Signal Generator Test Plans

Columns: `duration`, `frequency`, `power`, `modulation_enabled` (optional), `description` (optional)

```csv
# instrument_type: signal_generator
duration,frequency,power,description
5.0,1000000,0,Start at 1 MHz
10.0,10000000,-10,Peak at 10 MHz
```

- `duration` — seconds
- `frequency` — Hz
- `power` — dBm
- `modulation_enabled` — `true` or `false` (optional, defaults to false)

## Modulation Parameters

Signal generator test plans support AM and FM modulation. Specify modulation settings as metadata comments:

```csv
# instrument_type: signal_generator
# modulation_type: am
# modulation_frequency: 1000
# am_depth: 50
duration,frequency,power,modulation_enabled,description
5.0,1000000,0,true,1 MHz with 50% AM
5.0,10000000,-10,false,No modulation
```

## Validation Limits

Test plan values are validated against configurable limits before execution. See [Configuration]({{ site.baseurl }}/configuration.html) for default limits and how to change them.
