---
title: "Motor Control (Current Mode) (`MtrCtrl_CM`)"
description: "Current-mode motor control: command scaling, proportional-integral current control, quadrant detection, torque cancellation and peak-current estimation."
---

# Motor Control (Current Mode) (`MtrCtrl_CM`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Current-mode motor control: command scaling, proportional-integral current control, quadrant detection, torque cancellation and peak-current estimation. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_CurrCmd.c`, `src/Ap_CurrParamComp.c`, `src/Ap_PICurrCntrl.c`, `src/Ap_PeakCurrEst.c`, `src/Ap_QuadDet.c`, `src/Ap_TrqCanc.c`, `src/Ap_TrqCmdScl.c`
- Public headers: `include/Ap_MtrCtrl.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_CurrCmd_Cfg.arxml.tt`, `Ap_CurrCmd_Cfg.h.tt`, `Ap_CurrCmd_Generate.bat`, `Ap_CurrCmd_bswmd.arxml`, `Ap_CurrParamComp_Cfg.arxml.tt`, `Ap_CurrParamComp_Cfg.h.tt`, `Ap_CurrParamComp_Generate.bat`, `Ap_CurrParamComp_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `ParabolicInterpolation`
- `CalculateIq`
- `CalculateImVSIdq`
- `CurrtoVoltTest`
- `CalcTorque`
- `LocateTrqExtremes`
- `LocateMinimumIm`
- `CalLowPassFiltBilinearTerm`
- `CalLowPassFiltBilinearOut`
- `AngleWrap`
- `CalculateIdBoost`
- `CurrCmd_Init`
- `CurrCmd_Per1`
- `CurrParamComp_Init`
- `CurrParamComp_Per1`
- `CurrParamComp_Per2`
- `SCom_EOLNomMtrParam_Get`
- `SCom_EOLNomMtrParam_Set`
- `IntegralStateVarNonOperState`
- `CalLowPassFiltVecuOut`
- `LoaMtgtnSclFac`
- `PICurrCntrl_Init`
- `PICurrCntrl_Per1`
- `PeakCurrEst_Per1`

## Dependencies (internal includes)

- `Ap_CurrCmd_Cfg.h`
- `Ap_CurrParamComp_Cfg.h`
- `Ap_MtrCtrl.h`
- `Ap_PeakCurrEst_Cfg.h`
- `Ap_QuadDet_Cfg.h`
- `Ap_TrqCanc_Cfg.h`
- `Ap_TrqCmdScl_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `Interpolation.h`
- `MemMap.h`
- `MtrCtrl_Cfg.h`
- `Rte_Ap_CurrCmd.h`
- `Rte_Ap_CurrParamComp.h`
- `Rte_Ap_PICurrCntrl.h`
- `Rte_Ap_PeakCurrEst.h`
- `Rte_Ap_QuadDet.h`
- `Rte_Ap_TrqCanc.h`
- `Rte_Ap_TrqCmdScl.h`
- `Std_Types.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [CurrCmd_MDD](./doc-CurrCmd_MDD/) | summary | 4,557,824 bytes | `MtrCtrl_CM/doc/CurrCmd_MDD.doc` |
| | [CurrParamComp_MDD](./doc-CurrParamComp_MDD/) | converted | 374,077 bytes | `MtrCtrl_CM/doc/CurrParamComp_MDD.docx` |
| | [MtrCntrl_Integration_Manual](./doc-MtrCntrl_Integration_Manual/) | converted | 82,985 bytes | `MtrCtrl_CM/doc/MtrCntrl_Integration_Manual.docx` |
| | [PICurrentContrl_MDD](./doc-PICurrentContrl_MDD/) | summary | 752,640 bytes | `MtrCtrl_CM/doc/PICurrentContrl_MDD.doc` |
| | [PeakCurrEst_MDD](./doc-PeakCurrEst_MDD/) | converted | 244,532 bytes | `MtrCtrl_CM/doc/PeakCurrEst_MDD.docx` |
| | [Quadrant_Detection_MDD](./doc-Quadrant_Detection_MDD/) | converted | 236,311 bytes | `MtrCtrl_CM/doc/Quadrant_Detection_MDD.docx` |
| | [TorqueCmdScaling_MDD](./doc-TorqueCmdScaling_MDD/) | summary | 246,784 bytes | `MtrCtrl_CM/doc/TorqueCmdScaling_MDD.doc` |
| | [TrqCanc_MDD](./doc-TrqCanc_MDD/) | converted | 1,199,331 bytes | `MtrCtrl_CM/doc/TrqCanc_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

