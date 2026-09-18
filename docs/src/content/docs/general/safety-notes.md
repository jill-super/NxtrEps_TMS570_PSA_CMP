---
title: "Functional safety notes"
description: "Where the safety mechanisms live in this firmware."
---

# Functional safety notes

:::caution[Not a safety case]
These notes map where safety-relevant mechanisms live. They are not a safety case and do not replace the hazard analysis, technical safety concept or assessment records.
:::

## Layered monitoring

- **Firewall software components** (Assist, Damping, Return, End-of-Travel Damping firewalls) independently bound or gate the corresponding control outputs.
- **Reasonableness and temporal monitors**: Torque Reasonableness Diagnostics, Hands-Off-Wheel Detection, Over-Voltage Monitor, Controller Temperature Monitoring, Motor Temperature Estimation, Temporal Monitors and the Shutdown Mechanisms safe-state controller.
- **Diagnostics and fault handling**: Diagnostics Manager (core, Diagnostic Event Manager interface, fail-action), Fault Logging, Loss-of-Assist Management, Torque Loss-of-Assist Handling.
- **Supervision below the application**: Watchdog Manager / Watchdog Interface / Watchdog Driver (TTTech), Checkpoint Hooks, Operating System protection, Non-Volatile Memory integrity, Microcontroller Diagnostics (clock, error signalling module, Flash test).

## Design rules visible in the tree

- Each safety-relevant component pairs a Model Design Document with an integration manual in its `doc/` folder.
- Unit-test evidence (Tessy reports) is stored per module under `utp/` but is evidence, not specification, and is therefore indexed rather than converted page-by-page (see the document inventory).
- Static-analysis presets (QA-C / MISRA guidance) are stored with the static analysis configuration.
