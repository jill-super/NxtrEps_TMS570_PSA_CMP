---
title: "Temporal Monitor (Program Flow Monitoring) (`TmprlMon`)"
description: "Monitors program-flow timing (temporal/sequence supervision)."
---

# Temporal Monitor (Program Flow Monitoring) (`TmprlMon`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Monitors program-flow timing (temporal/sequence supervision). It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_TmprlMon.c`, `src/Sa_TmprlMon2.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_TmprlMon2_Cfg.arxml.tt`, `Sa_TmprlMon2_Cfg.h.tt`, `Sa_TmprlMon2_Generate.bat`, `Sa_TmprlMon2_bswmd.arxml`, `Sa_TmprlMon_Cfg.arxml.tt`, `Sa_TmprlMon_Cfg.h.tt`, `Sa_TmprlMon_Generate.bat`, `Sa_TmprlMon_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `TmprlMon_Per1`
- `TmprlMon_Per2`
- `TmprlMon_Per3`
- `TmprlMon_Trns1`
- `TmprlMon_Trns2`
- `TmprlMon2_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_TmprlMon.h`
- `Rte_Sa_TmprlMon2.h`
- `Sa_TmprlMon2_Cfg.h`
- `Sa_TmprlMon_Cfg.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Temporal Monitor_Integration_Manual](./doc-Temporal_Monitor_Integration_Manual/) | converted | 40,752 bytes | `TmprlMon/doc/Temporal Monitor_Integration_Manual.docx` |
| | [Temporal_Monitor_2_MDD](./doc-Temporal_Monitor_2_MDD/) | converted | 57,599 bytes | `TmprlMon/doc/Temporal_Monitor_2_MDD.docx` |
| | [Temporal_Monitor_MDD](./doc-Temporal_Monitor_MDD/) | converted | 464,890 bytes | `TmprlMon/doc/Temporal_Monitor_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.
- Safety-relevant monitor/guard: treat changes as safety-relevant and review against the functional-safety notes.

