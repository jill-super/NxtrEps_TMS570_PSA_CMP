---
title: "Battery Voltage Sensing (`BatteryVoltage`)"
description: "Provides filtered battery voltage and quality to consumers such as power limiting."
---

# Battery Voltage Sensing (`BatteryVoltage`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Provides filtered battery voltage and quality to consumers such as power limiting. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_BatteryVoltage.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_BatteryVoltage_Cfg.arxml.tt`, `Ap_BatteryVoltage_Cfg.h.tt`, `Ap_BatteryVoltage_Generate.bat`, `Ap_BatteryVoltage_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `BatteryVoltage_Init1`
- `BatteryVoltage_Per1`
- `BatteryVoltage_Per2`
- `BatteryVoltage_SCom_ClearTransOvData`
- `BatteryVoltage_SCom_ReadTransOvData`
- `Rte_Call_FltInjection_SCom_FltInjection`

## Dependencies (internal includes)

- `Ap_BatteryVoltage_Cfg.h`
- `BatteryVoltage_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Os.h`
- `Rte_Ap_BatteryVoltage.h`
- `adc_regs.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [BatteryVoltage_Integration_Manual](./doc-BatteryVoltage_Integration_Manual/) | converted | 33,972 bytes | `BatteryVoltage/doc/BatteryVoltage_Integration_Manual.docx` |
| | [Battery_Voltage_MDD](./doc-Battery_Voltage_MDD/) | summary | 905,216 bytes | `BatteryVoltage/doc/Battery_Voltage_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

