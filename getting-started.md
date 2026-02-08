---
layout: page
title: Getting Started
nav_order: 2
date_created: 2026-02-08_12:00:00
date_modified: 2026-02-08_12:00:00
---

# Getting Started

This guide covers installing VISA Vulture and running your first test.

## Requirements

- Python 3.10 or later
- Tkinter (included with most Python installations)
- For real hardware: a VISA driver such as NI-VISA or Keysight IO Libraries

## Installation

Install from PyPI:

```bash
pip install visa-vulture
```

Or install from source:

```bash
git clone https://github.com/dekmeister/visa-vulture.git
cd visa-vulture
pip install .
```

## Running VISA Vulture

Launch the application:

```bash
visa-vulture
```

By default, simulation mode is enabled so you can explore the interface without hardware connected.

To explicitly enable simulation mode:

```bash
visa-vulture --simulation
```

To use a custom configuration file:

```bash
visa-vulture --config path/to/config.json
```

## Next Steps

- Learn how to write test plans in [Test Plans]({{ site.baseurl }}/test-plans.html)
- Customise application settings in [Configuration]({{ site.baseurl }}/configuration.html)
