---
title: "Universal Measurement and Calibration Protocol Interface (`Xcp`)"
description: "Application-side Universal Measurement and Calibration Protocol handling."
---

# Universal Measurement and Calibration Protocol Interface (`Xcp`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Application-side Universal Measurement and Calibration Protocol handling. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_ApXcp.c`
- Public headers: `include/Ap_ApXcp.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_ApXcp_Cfg.c.tt`, `Ap_ApXcp_Cfg.h.tt`, `Ap_ApXcp_Generate.bat`, `Ap_ApXcp_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `XcpSetError`
- `CreateXcpCalSession`
- `GetPersIndexes`
- `GetSetIndexes`
- `EERead`
- `EEWrite`
- `CheckXcpAccess`
- `GetFcnIdx`
- `GetAppIdx`
- `ApXcp_Per1`
- `ApXcp_Init`
- `ApXcpWriteCommon`
- `ApplXcpGetPointer`
- `ApplXcpGetTimestamp`
- `ApplXcpReset`
- `ApplXcpFlashClear`
- `ApplXcpFlashProgram`
- `ApplXcpProgramStart`
- `ApplXcpCheckReadAccess`
- `ApplXcpCheckReadEEPROM`
- `ApplXcpCheckWriteAccess`
- `ApplXcpCheckDAQAccess`
- `ApplXcpCheckWriteEEPROM`
- `ApplXcpCalibrationRead`

## Dependencies (internal includes)

- `Ap_ApXcp.h`
- `Ap_ApXcp_Cfg.h`
- `EPS_DiagSrvcs_SrvcLUTbl.h`
- `EPS_DiagSrvcs_XCP.Interface.h`
- `EPS_DiagSrvcs_XCP.h`
- `Eep_30_At25128.h`
- `Mcu.h`
- `MemMap.h`
- `Rte_Ap_ApXcp.h`
- `Std_Types.h`
- `SystemTime.h`
- `XcpProf.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [ApXcp_Integration_Manual](./doc-ApXcp_Integration_Manual/) | converted | 82,129 bytes | `Xcp/doc/ApXcp_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

