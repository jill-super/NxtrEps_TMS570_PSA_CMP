---
title: "Commutated Motor Current Measurement (`CmMtrCurr`)"
description: "Measures commutated motor current for the control loop."
---

# Commutated Motor Current Measurement (`CmMtrCurr`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Measures commutated motor current for the control loop. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_CmMtrCurr.c`
- Public headers: `include/Sa_CmMtrCurr.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_CmMtrCurr_Cfg.arxml.tt`, `Sa_CmMtrCurr_Cfg.h.tt`, `Sa_CmMtrCurr_Generate.bat`, `Sa_CmMtrCurr_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `CmMtrCurrTempOffset_Scom_Get`
- `CmMtrCurrTempOffset_Scom_Set`
- `CmMtrCurr_Init`
- `CmMtrCurr_Per1`
- `CmMtrCurr_Per2`
- `CmMtrCurr_Per3`
- `CmMtrCurr_SCom_CalGain`
- `CmMtrCurr_SCom_CalOffset`
- `CmMtrCurr_SCom_MtrCurrOffReadStatus`
- `CmMtrCurr_SCom_ReadMtrCurrCals`
- `CmMtrCurr_SCom_SetMtrCurrCals`
- `CurrDQPer1`

## Dependencies (internal includes)

- `CalConstants.h`
- `CmMtrCurr_Cfg.h`
- `GlobalMacro.h`
- `Interpolation.h`
- `MemMap.h`
- `Rte_Sa_CmMtrCurr.h`
- `Rte_Type.h`
- `Sa_CmMtrCurr.h`
- `Sa_CmMtrCurr_Cfg.h`
- `filters.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [CmMtrCurr_Integration_Manual](./doc-CmMtrCurr_Integration_Manual/) | converted | 42,421 bytes | `CmMtrCurr/doc/CmMtrCurr_Integration_Manual.docx` |
| | [CmMtrCurr_MDD](./doc-CmMtrCurr_MDD/) | converted | 1,614,300 bytes | `CmMtrCurr/doc/CmMtrCurr_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

