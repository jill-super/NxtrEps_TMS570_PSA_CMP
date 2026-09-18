---
title: "Enhanced Pulse-Width Modulation Driver (`ePWM_Up`)"
description: "Configures and drives enhanced pulse-width modulation outputs."
---

# Enhanced Pulse-Width Modulation Driver (`ePWM_Up`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Configures and drives enhanced pulse-width modulation outputs. It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/Ap_ePWM2.c`, `src/ePWM.c`
- Public headers: `include/ePWM.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `ePWM2_Per1`
- `ePWM2_Trns1`
- `ePWM2_Trns2`
- `ePWM_Init1`
- `ePWM_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_ePWM2.h`
- `ePWM_Cfg.h`
- `ePwm.h`
- `epwm_regs.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Ap_ePWM2 MDD](./doc-Ap_ePWM2_MDD/) | summary | 354,816 bytes | `ePWM_Up/doc/Ap_ePWM2 MDD.doc` |
| | [ePWM MDD](./doc-ePWM_MDD/) | summary | 1,074,176 bytes | `ePWM_Up/doc/ePWM MDD.doc` |
| | [ePWM_Integration_Manual](./doc-ePWM_Integration_Manual/) | summary | 152,064 bytes | `ePWM_Up/doc/ePWM_Integration_Manual.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

