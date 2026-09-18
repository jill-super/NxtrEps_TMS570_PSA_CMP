---
title: "Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode) (`SVDrvr_CM`)"
description: "Drives the power stage via pulse-width modulation (current-mode complex driver)."
---

# Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode) (`SVDrvr_CM`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Drives the power stage via pulse-width modulation (current-mode complex driver). It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/PwmCdd.c`
- Public headers: `include/PwmCdd.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `PwmPeriodDither_u16`
- `ModIndxPhase_u0p16`
- `PwmCdd_Init`
- `PwmCdd_Per1`
- `CDD_ApplyPWMMtrElecMechPol`
- `CDDPorts_ClearPhsReasSum`

## Dependencies (internal includes)

- `CDD_Data.h`
- `CDD_Func.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `PwmCdd.h`
- `PwmCdd_Cfg.h`
- `Std_Types.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [PWMCdd_Integration_Manual](./doc-PWMCdd_Integration_Manual/) | converted | 38,361 bytes | `SVDrvr_CM/doc/PWMCdd_Integration_Manual.docx` |
| | [PWM_CDD_MDD](./doc-PWM_CDD_MDD/) | converted | 516,830 bytes | `SVDrvr_CM/doc/PWM_CDD_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

