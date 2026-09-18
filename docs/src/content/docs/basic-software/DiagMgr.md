---
title: "Diagnostics Manager (`DiagMgr`)"
description: "Central diagnostics: fault confirmation, Diagnostic Event Manager interface and fail-actions."
---

# Diagnostics Manager (`DiagMgr`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Central diagnostics: fault confirmation, Diagnostic Event Manager interface and fail-actions. It belongs to the **Basic Software — Services and ECU Abstraction** layer.

## Key files

- Implementation: `src/Ap_DiagMgr_Core.c`, `src/Ap_DiagMgr_DemIf.c`, `src/Ap_DiagMgr_FailAction.c`
- Public headers: `include/Ap_DiagMgr.h`, `include/Ap_DiagMgr_Types.h`
- Generator templates and wiring: `generate/` (`DiagMgr_Cfg.c.tt`, `DiagMgr_Cfg.h.tt`, `DiagMgr_Generate.bat`, `DiagMgr_Proxy.c.tt`, `DiagMgr_bswmd.arxml`, `DiagMgr_swc.arxml.tt`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `FailedCheckAndProcessing`
- `ProcessRampResponse`
- `ProcessDiagSts`
- `SetBits_u8`
- `ClrBits_u8`
- `ReadBit_u8`
- `ReadBit_u32`
- `SetBits_u16`
- `DiagMgr_Init_Core`
- `DiagMgr_Per_Core`
- `DiagMgr_Trns_Core`
- `NxtrDiagMgr_GetNTCFailed_Core`
- `NxtrDiagMgr_GetNTCActive_Core`
- `NxtrDiagMgr_GetNTCStatus_Core`
- `NxtrDiagMgr_SetNTCStatus_Core`
- `NxtrDiagMgr_ReportNTCStatus_Core`
- `CreateStorageArray`
- `DiagMgr_Init1`
- `DiagMgr_Trns1`
- `DiagMgr_StaCtrl_Shutdown`
- `DiagMgr_Per2`
- `DiagMgr_SCom_GetNTCInfo`
- `DiagMgr_SCom_ResetNTCStatus`
- `DiagMgr_SCom_ReadStrgArray`

## Dependencies (internal includes)

- `Ap_DiagMgr.h`
- `Ap_DiagMgr_Types.h`
- `CalConstants.h`
- `Det.h`
- `DiagMgr_Cfg.h`
- `GlobalMacro.h`
- `MemMap.h`
- `NvM.h`
- `Os.h`
- `Rte_Type.h`
- `Std_Types.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Diagnostics_Manager_Core_MDD](./doc-Diagnostics_Manager_Core_MDD/) | converted | 1,056,129 bytes | `DiagMgr/doc/Diagnostics_Manager_Core_MDD.docx` |
| | [Diagnostics_Manager_DemIf_MDD](./doc-Diagnostics_Manager_DemIf_MDD/) | converted | 677,333 bytes | `DiagMgr/doc/Diagnostics_Manager_DemIf_MDD.docx` |
| | [Diagnostics_Manager_FailAction_MDD](./doc-Diagnostics_Manager_FailAction_MDD/) | converted | 245,265 bytes | `DiagMgr/doc/Diagnostics_Manager_FailAction_MDD.docx` |
| | [Diagnostics_Manager_GeneratedCfg_MDD](./doc-Diagnostics_Manager_GeneratedCfg_MDD/) | converted | 321,343 bytes | `DiagMgr/doc/Diagnostics_Manager_GeneratedCfg_MDD.docx` |
| | [Integration Manual _DiagMgr](./doc-Integration_Manual__DiagMgr/) | summary | 142,336 bytes | `DiagMgr/doc/Integration Manual _DiagMgr.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

