---
layout: page
title: Custom Instruments
nav_order: 5
date_created: 2026-02-08_12:00:00
date_modified: 2026-02-08_12:00:00
---

# Custom Instruments

VISA Vulture supports user-defined instrument classes that extend the built-in power supply and signal generator types.

## Overview

Custom instruments are Python files placed in the `instruments/` directory at the project root. They are auto-discovered at startup and appear in the Resource Manager dropdown alongside the built-in types.

## Creating a Custom Instrument

A custom instrument class must:

- Inherit from `PowerSupply` or `SignalGenerator` (not `BaseInstrument`)
- Define a `display_name` class attribute
- Be placed in the `instruments/` directory

## Example

```python
from visa_vulture.instruments import SignalGenerator

class MyCustomGen(SignalGenerator):
    display_name = "My Custom Signal Gen"
```

The class inherits all standard methods (`set_frequency`, `set_power`, etc.) and can override them to implement device-specific behaviour.
