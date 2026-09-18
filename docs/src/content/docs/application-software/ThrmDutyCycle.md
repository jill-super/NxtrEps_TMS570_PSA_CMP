---
title: "Thermal Duty Cycle Management (`ThrmDutyCycle`)"
description: "Derates duty cycle with temperature to protect hardware."
---

# Thermal Duty Cycle Management (`ThrmDutyCycle`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Derates duty cycle with temperature to protect hardware. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_ThrmlDutyCycle.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_ThrmlDutyCycle_Cfg.arxml.tt`, `Ap_ThrmlDutyCycle_Cfg.h.tt`, `Ap_ThrmlDutyCycle_Generate.bat`, `Ap_ThrmlDutyCycle_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `StepVarXY_u16_s16Xu16Y_Cnt`
- `ThrmlDutyCycle_Init1`
- `ThrmlDutyCycle_Per1`
- `ThrmlDutyCycle_Trns1`

## Dependencies (internal includes)

- `Ap_ThrmlDutyCycle_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_ThrmlDutyCycle.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`
- `math.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [ThermalDutyCycle_Integration_Manual](./doc-ThermalDutyCycle_Integration_Manual/) | converted | 38,875 bytes | `ThrmDutyCycle/doc/ThermalDutyCycle_Integration_Manual.docx` |
| | [Thermal_Duty_Cycle_MDD](./doc-Thermal_Duty_Cycle_MDD/) | converted | 1,080,711 bytes | `ThrmDutyCycle/doc/Thermal_Duty_Cycle_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

