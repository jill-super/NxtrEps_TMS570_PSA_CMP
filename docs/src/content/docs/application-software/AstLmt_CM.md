---
title: "Assist Summation Limiter (Current Mode) (`AstLmt_CM`)"
description: "Limits the summed assist request in current-mode operation."
---

# Assist Summation Limiter (Current Mode) (`AstLmt_CM`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Limits the summed assist request in current-mode operation. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_AstLmt.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_AstLmt_Cfg.arxml.tt`, `Ap_AstLmt_Cfg.h.tt`, `Ap_AstLmt_Generate.bat`, `Ap_AstLmt_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `AstLmt_Init`
- `AstLmt_Per1`
- `AstLmt_Scom_ManualTrqCmd`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_AstLmt.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Assist_Sum_Limit_CurrentMode_MDD](./doc-Assist_Sum_Limit_CurrentMode_MDD/) | converted | 65,406 bytes | `AstLmt_CM/doc/Assist_Sum_Limit_CurrentMode_MDD.docx` |
| | [AstLmt_CM_IntegrationManual](./doc-AstLmt_CM_IntegrationManual/) | converted | 43,861 bytes | `AstLmt_CM/doc/AstLmt_CM_IntegrationManual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

