---
title: "Average Friction Learning (`AvgFricLrn`)"
description: "Learns slowly-varying friction so compensation stays accurate over life and temperature."
---

# Average Friction Learning (`AvgFricLrn`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Learns slowly-varying friction so compensation stays accurate over life and temperature. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_AvgFricLrn.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_AvgFricLrn_Cfg.arxml.tt`, `Ap_AvgFricLrn_Cfg.h.tt`, `Ap_AvgFricLrn_Generate.bat`, `Ap_AvgFricLrn_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `LoadBuffer`
- `HwAngConstraint`
- `HwVelConstraint`
- `VehSpdConstraint`
- `FricLearning`
- `BaselineMode`
- `ClearMode`
- `AvgFricLrn_Init1`
- `AvgFricLrn_Per1`
- `AvgFricLrn_SCom_GetEOLFric`
- `AvgFricLrn_SCom_GetOffsetOutputDefeat`
- `AvgFricLrn_SCom_GetSelect`
- `AvgFricLrn_SCom_InitLearnedTables`
- `AvgFricLrn_SCom_ResetToZero`
- `AvgFricLrn_SCom_SetEOLFric`
- `AvgFricLrn_SCom_SetOffsetOutputDefeat`
- `AvgFricLrn_SCom_SetSelect`
- `AvgFricLrn_Trns1`
- `Rte_Call_FltInjection_SCom_FltInjection`

## Dependencies (internal includes)

- `Ap_AvgFricLrn_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_AvgFricLrn.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Average_Friction_Learning_MDD](./doc-Average_Friction_Learning_MDD/) | converted | 1,906,622 bytes | `AvgFricLrn/doc/Average_Friction_Learning_MDD.docx` |
| | [AvgFricLrn_Integration_Manual](./doc-AvgFricLrn_Integration_Manual/) | converted | 41,976 bytes | `AvgFricLrn/doc/AvgFricLrn_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

