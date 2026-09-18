---
title: "TMS570 Microcontroller Diagnostics (`TMS570_uDiag`)"
description: "Microcontroller self-diagnostics (clocks, error signalling, Flash test)."
---

# TMS570 Microcontroller Diagnostics (`TMS570_uDiag`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Microcontroller self-diagnostics (clocks, error signalling, Flash test). It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/AbortHandler.c`, `src/Cd_uDiagCCRM.c`, `src/Cd_uDiagClockMonitor.c`, `src/Cd_uDiagECC.c`, `src/Cd_uDiagESM.c`, `src/Cd_uDiagFPU.c`, `src/Cd_uDiagIOMM.c`, `src/Cd_uDiagLossOfExec.c`, `src/Cd_uDiagParity.c`, `src/Cd_uDiagPeriphMPU.c`, `src/Cd_uDiagResetHandler.c`, `src/Cd_uDiagStaticRegs.c`, `src/Cd_uDiagUtility.asm`, `src/Cd_uDiagVIM.c`
- Public headers: `include/Cd_uDiagUtility.h`, `include/FlsTst.h`, `include/RednRpdShtdn.h`, `include/uDiag.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Cd_uDiag_Cfg.arxml.tt`, `FlsTst_Cfg.c.tt`, `FlsTst_Cfg.h.tt`, `FlsTst_Generate.bat`, `FlsTst_bswmd.arxml`, `uDiag_Cfg.c.tt`, `uDiag_Cfg.h.tt`, `uDiag_Generate.bat`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `AbortHandler`
- `uDiagCCRM_Init`
- `CCRMErr`
- `uDiagClockMonitor_Init`
- `ClockMonitorErr`
- `DCCErr`
- `uDiagECC_Per`
- `uDiagECC_Init`
- `FlashECCCorrErr`
- `RAMECCCorrErr`
- `FlashECCUncorrErr`
- `RAMECCUncorrErr`
- `FlashECCLiveLockErr`
- `uDiagECC_RednRpdShtdn`
- `uDiagESM_Init`
- `uDiagFPU_Init1`
- `uDiagFPU_Init2`
- `uDiagIOMM_Init`
- `IOMMErr`
- `uDiagLossOfExec_Per2`
- `uDiagLossOfExec_Per3`
- `MicroDiag_Per1`
- `NHETParityInit`
- `HTUParityInit`

## Dependencies (internal includes)

- `Ap_DiagMgr.h`
- `CalConstants.h`
- `Cd_uDiagUtility.h`
- `Dma.h`
- `FlsTst.h`
- `FlsTst_Cfg.h`
- `GlobalMacro.h`
- `Interrupts.h`
- `MemMap.h`
- `Nhet.h`
- `Os.h`
- `RednRpdShtdn.h`
- `ResetCause.h`
- `Rte_Cd_uDiag.h`
- `Std_Types.h`
- `WdgM.h`
- `adc_regs.h`
- `appinit_cfg.h`
- `crc_regs.h`
- `dcan_regs.h`
- `dcc_regs.h`
- `esm_regs.h`
- `flash_regs.h`
- `htu_regs.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Cd_uDiagFPU_MDD](./doc-Cd_uDiagFPU_MDD/) | converted | 213,663 bytes | `TMS570_uDiag/doc/Cd_uDiagFPU_MDD.docx` |
| | [Cd_uDiagUtility_MDD](./doc-Cd_uDiagUtility_MDD/) | converted | 32,732 bytes | `TMS570_uDiag/doc/Cd_uDiagUtility_MDD.docx` |
| | [Cd_uDiag_Integration_Manual](./doc-Cd_uDiag_Integration_Manual/) | converted | 49,404 bytes | `TMS570_uDiag/doc/Cd_uDiag_Integration_Manual.docx` |
| | [FlsTst_Integration_Manual](./doc-FlsTst_Integration_Manual/) | converted | 40,519 bytes | `TMS570_uDiag/doc/FlsTst_Integration_Manual.docx` |
| | [FlsTst_MDD](./doc-FlsTst_MDD/) | converted | 29,489 bytes | `TMS570_uDiag/doc/FlsTst_MDD.docx` |
| | [OsErrCallouts_MDD](./doc-OsErrCallouts_MDD/) | converted | 139,895 bytes | `TMS570_uDiag/doc/OsErrCallouts_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

