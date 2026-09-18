---
title: "Over-Voltage Monitor (`OvrVoltMon`)"
description: "Detects over-voltage and triggers protection."
---

# Over-Voltage Monitor (`OvrVoltMon`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Detects over-voltage and triggers protection. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_OvrVoltMon.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_OvrVoltMon_Cfg.arxml.tt`, `Sa_OvrVoltMon_Cfg.h.tt`, `Sa_OvrVoltMon_Generate.bat`, `Sa_OvrVoltMon_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `OvrVoltMon_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_OvrVoltMon.h`
- `Sa_OvrVoltMon_Cfg.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [OverVoltageMonitor_MDD](./doc-OverVoltageMonitor_MDD/) | converted | 295,841 bytes | `OvrVoltMon/doc/OverVoltageMonitor_MDD.docx` |
| | [OvrVoltMon_Integration_Manual](./doc-OvrVoltMon_Integration_Manual/) | converted | 40,863 bytes | `OvrVoltMon/doc/OvrVoltMon_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.
- Safety-relevant monitor/guard: treat changes as safety-relevant and review against the functional-safety notes.

