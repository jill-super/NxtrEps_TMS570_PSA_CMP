---
title: "Hysteresis Compensation (`HystComp`)"
description: "Compensates mechanical hysteresis for a linear steering feel."
---

# Hysteresis Compensation (`HystComp`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Compensates mechanical hysteresis for a linear steering feel. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_HystComp.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_HystComp_Cfg.arxml.tt`, `Ap_HystComp_Cfg.h.tt`, `Ap_HystComp_Generate.bat`, `Ap_HystComp_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `MoreCompensation`
- `LessCompensation`
- `CalcAvailComp`
- `HystComp_Init1`
- `HystComp_Per1`
- `Rte_Call_FltInjection_SCom_FltInjection`

## Dependencies (internal includes)

- `Ap_HystComp_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_HystComp.h`
- `filters.h`
- `fixmath.h`
- `float.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [HystComp_Integration_Manual](./doc-HystComp_Integration_Manual/) | converted | 27,811 bytes | `HystComp/doc/HystComp_Integration_Manual.docx` |
| | [Hysteresis_Compensation_MDD](./doc-Hysteresis_Compensation_MDD/) | summary | 2,092,544 bytes | `HystComp/doc/Hysteresis_Compensation_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

