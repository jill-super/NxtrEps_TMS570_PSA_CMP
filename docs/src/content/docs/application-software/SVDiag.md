---
title: "Motor Driver Diagnostics (Servo Drive Diagnostics) (`SVDiag`)"
description: "Diagnoses the servo power stage (digital phase reasonableness, motor-driver diagnostics)."
---

# Motor Driver Diagnostics (Servo Drive Diagnostics) (`SVDiag`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Diagnoses the servo power stage (digital phase reasonableness, motor-driver diagnostics). It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_DigPhsReasDiag.c`, `src/Sa_MtrDrvDiag.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_DigPhsReasDiag_Cfg.arxml.tt`, `Ap_DigPhsReasDiag_Cfg.h.tt`, `Ap_DigPhsReasDiag_Generate.bat`, `Ap_DigPhsReasDiag_bswmd.arxml`, `Sa_MtrDrvDiag_Cfg.arxml.tt`, `Sa_MtrDrvDiag_Cfg.h.tt`, `Sa_MtrDrvDiag_Generate.bat`, `Sa_MtrDrvDiag_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `PhaseGroundTabLookupoffset`
- `Read_CountToRev`
- `DigPhsReasDiag_Init`
- `DigPhsReasDiag_Per1`
- `DigPhsReasDiag_Trans1`
- `MotorDriverInit`
- `ProcGateDriveFlt`
- `ProcBridgeFlt`
- `ReadMtrDrvFltData`
- `ResetGateDrive`
- `GateDrvWaitTime`
- `MtrDrvDiag_Per1`
- `MtrDrvDiag_Per2`
- `MtrDrvDiag_Trns1`
- `Rte_IWrite_MtrDrvDiag_Trns1_MtrDrvrInitComplete_Cnt_lgc`
- `Rte_IWriteRef_MtrDrvDiag_Trns1_MtrDrvrInitComplete_Cnt_lgc`

## Dependencies (internal includes)

- `Ap_DigPhsReasDiag_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Os.h`
- `Rte_Ap_DigPhsReasDiag.h`
- `Rte_Sa_MtrDrvDiag.h`
- `Sa_MtrDrvDiag_Cfg.h`
- `filters.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [DigPhsReasDiag_MDD](./doc-DigPhsReasDiag_MDD/) | converted | 1,324,560 bytes | `SVDiag/doc/DigPhsReasDiag_MDD.docx` |
| | [Motor_Driver_Diagnostics_MDD](./doc-Motor_Driver_Diagnostics_MDD/) | converted | 1,010,799 bytes | `SVDiag/doc/Motor_Driver_Diagnostics_MDD.docx` |
| | [SVDiag_Integration_Manual](./doc-SVDiag_Integration_Manual/) | converted | 80,819 bytes | `SVDiag/doc/SVDiag_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

