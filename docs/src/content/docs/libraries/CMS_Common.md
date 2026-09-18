---
title: "Diagnostics Communication Common Services (`CMS_Common`)"
description: "Shared diagnostics/communication helpers (ISO and calibration-protocol paths)."
---

# Diagnostics Communication Common Services (`CMS_Common`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Shared diagnostics/communication helpers (ISO and calibration-protocol paths). It belongs to the **Shared Libraries and Platform Types** layer.

## Key files

- Implementation: `src/EPS_DiagSrvcs_ISO.c`, `src/EPS_DiagSrvcs_XCP.Vector.c`, `src/EPS_DiagSrvcs_XCP.c`
- Public headers: `include/EPS_DiagSrvcs_CommonData.h`, `include/EPS_DiagSrvcs_ISO.h`, `include/EPS_DiagSrvcs_SrvcLUTbl.h`, `include/EPS_DiagSrvcs_XCP.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `EPS_DiagSessionChangeIndicator`
- `EPSDiagSrvcs_Task`
- `EPS_DiagSrvcs_Init`
- `NxtrMEC_Init`
- `DiagSrvcs_MainHandler`
- `DiagSrvcs_PIDIdxSearch`
- `DiagSrvcs_ConfiguredNrcCheck`
- `DiagSrvcs_NRCTranslate`
- `DiagSrvNullFunc`
- `HandsOnDetection`
- `F00FCheckConditions`
- `ProcessF0FF`
- `EPSInternal_RESET_1160`
- `EPSInternal_RID_F000`
- `EPSInternal_RID_F001`
- `EPSInternal_RID_F002`
- `EPSInternal_RID_F003`
- `EPSInternal_RID_F004`
- `EPSInternal_RID_F005`
- `EPSInternal_RID_F006`
- `EPSInternal_RID_F007`
- `EPSInternal_RID_F008`
- `EPSInternal_RID_F009`
- `EPSInternal_RID_F00A`

## Dependencies (internal includes)

- `Ap_DfltConfigData.h`
- `CDD_Data.h`
- `CalConstants.h`
- `Compiler.h`
- `DataLogistic.h`
- `EPS_DiagSrvcs_CommonData.h`
- `EPS_DiagSrvcs_ISO.Customer.h`
- `EPS_DiagSrvcs_ISO.Interface.h`
- `EPS_DiagSrvcs_ISO.h`
- `EPS_DiagSrvcs_SrvcLUTbl.h`
- `EPS_DiagSrvcs_XCP.Interface.h`
- `EPS_DiagSrvcs_XCP.h`
- `GlobalMacro.h`
- `MemMap.h`
- `NvM.h`
- `Rte_type.h`
- `Std_Types.h`
- `SystemTime.h`
- `fixmath.h`
- `fpmtype.h`
- `osek.h`
- `tiotp_regs.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| _No design documents in `doc/`._ |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

