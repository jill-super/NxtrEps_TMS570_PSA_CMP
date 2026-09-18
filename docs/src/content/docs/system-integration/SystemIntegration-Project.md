---
title: "System Integration Project (PSA CMP EPS TMS570)"
description: "Top-level Electronic Control Unit build, startup and integration."
---

# System Integration Project (`SwProject`)

:::note[Origin: mixed — in-house wiring on Vector/Third-party stacks]
The integration project is owned in-house. It wires in-house components (Application Software, Complex Device Drivers) to Vector-provided Basic Software and Runtime Environment plus Texas Instruments, TTTech and Gliwa third-party parts.
:::

## Layout

- `SwProject/Source/` — integrated sources: `Application Startup`, `Basic Software`, `Complex Device Drivers`, `Generated Configuration Data*`, `Input-Output Hardware Abstraction`.
- `SwProject/CDDInterface`, `Customer Battery Diagnostics`, `Diagnostic Event Manager Interface`, `Default Configuration Data`, `Diagnostic Services`, `Fault Logging`, `Input-Output Hardware Abstraction (User)`, `Serial Communication Driver/Input/Output`, `Vehicle Power Mode Management` — project-level modules documented under their own pages.
- `High-Level Design Documents/` — vendor technical references (Controller Area Network stack, Interaction Layer, Transport Protocol, Network Management, Station Manager, standard library) plus integration checklists; indexed in the [design document inventory](../general/document-inventory/).
- `Tools/` — DaVinci project, timing, metrics, Quality Assurance and patch tooling.
- `Linker.cmd`, `postbuild.bat`, `targetConfigs/` — link and target wiring.

## Build flow

See the [build guide](../general/build-guide/): generate (DaVinci / component templates) → integrate (per-module `Integrate.bat`) → compile with the Texas Instruments toolchain → link with `Linker.cmd` → calibrate via the Universal Measurement and Calibration Protocol path.
