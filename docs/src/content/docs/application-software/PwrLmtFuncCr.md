---
title: "Power Limit Function (Current Regulation) (`PwrLmtFuncCr`)"
description: "Enforces electrical/thermal power limits through current regulation."
---

# Power Limit Function (Current Regulation) (`PwrLmtFuncCr`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Enforces electrical/thermal power limits through current regulation. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_PwrLmtFuncCr.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_PwrLmtFuncCr_Cfg.arxml.tt`, `Ap_PwrLmtFuncCr_Cfg.h.tt`, `Ap_PwrLmtFuncCr_Generate.bat`, `Ap_PwrLmtFuncCr_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `PwrLmtFuncCr_Init1`
- `PwrLmtFuncCr_Per1`
- `PwrLmtFuncCr_Per2`

## Dependencies (internal includes)

- `Ap_DiagMgr.h`
- `Ap_PwrLmtFuncCr_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_PwrLmtFuncCr.h`
- `filters.h`
- `fixmath.h`
- `float.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Power_Limit_Function_CM_Integration_Manual](./doc-Power_Limit_Function_CM_Integration_Manual/) | converted | 40,887 bytes | `PwrLmtFuncCr/doc/Power_Limit_Function_CM_Integration_Manual.docx` |
| | [Power_Limit_Function_CM_MDD](./doc-Power_Limit_Function_CM_MDD/) | converted | 589,765 bytes | `PwrLmtFuncCr/doc/Power_Limit_Function_CM_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

