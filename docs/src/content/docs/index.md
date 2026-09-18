---
title: "Electric Power Steering — Technical Documentation"
description: "AUTOSAR-layered reference for the Electric Power Steering controller firmware."
---

# Electric Power Steering — Technical Documentation

This site documents the Electric Power Steering controller firmware: an AUTOSAR-based embedded system written mostly in C for a Texas Instruments TMS570 microcontroller. Use it to find a module, understand which AUTOSAR layer it belongs to, tell in-house code apart from third-party code, and read the converted design documentation.

:::note[How to read this site]
Module titles use **expanded long names** for readability, with the repository directory name in code spans (for example: Steering Power Assist Control (`Assist`)). The [glossary](./general/glossary/) lists every expansion.
:::

## AUTOSAR layers in this project

| Layer | What lives here | Start |
|---|---|---|
| Application Software | Steering control, estimation, monitoring and vehicle-interface software components | [Application Software](./application-software/) |
| Complex Device Drivers | Hardware-near drivers: motor sensing, power stage, memory proxy, microcontroller diagnostics | [Complex Device Drivers](./complex-device-drivers/) |
| Basic Software (Services and ECU Abstraction) | Diagnostics, memory, mode management, communication and hardware abstraction services | [Basic Software](./basic-software/) |
| Microcontroller Abstraction Layer | Peripheral and memory drivers (Analog-to-Digital Converter, Direct Memory Access, Flash memory, timers) | [Microcontroller Abstraction](./microcontroller-abstraction/) |
| Runtime Environment and Generated Configuration | Vector MICROSAR Runtime Environment and DaVinci Configurator output | [Runtime Environment](./runtime-environment/) |
| Shared Libraries and Platform Types | Filters, math, diagnostics helpers, timing-trace support, platform types | [Libraries](./libraries/) |
| System Integration Project | Top-level Electronic Control Unit build, startup and integration artefacts | [System Integration](./system-integration/) |

## Vector-provided versus in-house code

- **Custom (in-house)** — control logic written for this controller. File templates may carry a Vector MICROSAR Runtime Environment Generator banner, but the behaviour is in-house. Most Application Software and Complex Device Driver modules are in this group.
- **Vector-provided** — Vector MICROSAR Basic Software, Runtime Environment and DaVinci-generated configuration (Controller Area Network stack, Diagnostic Event Manager, Non-Volatile Memory Manager, Operating System and similar).
- **Third-party (non-Vector)** — Texas Instruments Flash drivers, TTTech watchdog stack and the Gliwa timing-trace library.

Details and the full per-module verdict: [Vector vs in-house code](./general/origin-policy/).

## Design documents

Every `doc/` folder in the repository was inventoried. Modern Word (`.docx`), Portable Document Format (`.pdf`) and text files were converted to Markdown next to their module page; legacy binary Word (`.doc`) files — which need a full office converter — are represented by a structured summary page that names the source file, its size and what it covers. Start at the [design document inventory](./general/document-inventory/).

## Build and safety

- How the firmware is built (Windows batch wiring, DaVinci generation, calibration): [Build guide](./general/build-guide/).
- Functional-safety context (firewalls, monitors, watchdogs, diagnostics): [Functional safety notes](./general/safety-notes/).
