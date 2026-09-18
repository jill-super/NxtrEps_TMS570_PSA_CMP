---
title: "Stability Compensation (`StabilityComp`)"
description: "Shapes loop stability margins across operating points."
---

# Stability Compensation (`StabilityComp`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Shapes loop stability margins across operating points. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_StabilityComp.c`, `src/Ap_StabilityComp2.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_StabilityComp2_Cfg.arxml.tt`, `Ap_StabilityComp2_Cfg.h.tt`, `Ap_StabilityComp2_Generate.bat`, `Ap_StabilityComp2_bswmd.arxml`, `Ap_StabilityComp_Cfg.arxml.tt`, `Ap_StabilityComp_Cfg.h.tt`, `Ap_StabilityComp_Generate.bat`, `Ap_StabilityComp_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `ApplyStabilityComp`
- `StabilityComp_Init1`
- `StabilityComp_Per1`
- `Rte_Call_FaultInjection_SCom_FltInjection`
- `ApplyStabilityComp2`
- `StabilityComp2_Init1`
- `StabilityComp2_Per1`

## Dependencies (internal includes)

- `Ap_StabilityComp2_Cfg.h`
- `Ap_StabilityComp_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_StabilityComp.h`
- `Rte_Ap_StabilityComp2.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [StabilityCompensation2_MDD](./doc-StabilityCompensation2_MDD/) | converted | 370,691 bytes | `StabilityComp/doc/StabilityCompensation2_MDD.docx` |
| | [StabilityCompensation_MDD](./doc-StabilityCompensation_MDD/) | converted | 510,815 bytes | `StabilityComp/doc/StabilityCompensation_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

