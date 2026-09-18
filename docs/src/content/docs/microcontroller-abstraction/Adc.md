---
title: "Analog-to-Digital Converter Driver (`Adc`)"
description: "Samples analog inputs (currents, voltages, temperature)."
---

# Analog-to-Digital Converter Driver (`Adc`)

:::note[Origin: Custom (in-house)]
In-house driver written for this Electronic Control Unit (Nexteer copyright). It plays a Microcontroller Abstraction role but is not Vector MICROSAR code.
:::

## Purpose and responsibility

Samples analog inputs (currents, voltages, temperature). It belongs to the **Microcontroller Abstraction Layer** layer.

## Key files

- Implementation: `src/Adc.c`, `src/Adc2.c`, `src/Adc_Common.c`
- Public headers: `include/Adc.h`, `include/Adc2.h`, `include/Adc_Common.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `Adc_Init_FixedCfg`
- `Adc_StartGroupConversion`
- `Adc_GetGroupStatus`
- `Adc_ReadGroup`
- `Adc2_Init1`
- `Adc2_StartGroupConversion`
- `Adc2_EnableGroupNotification`
- `ADCOffsetCalibration`

## Dependencies (internal includes)

- `Adc.h`
- `Adc2.h`
- `Adc2_Cfg.h`
- `Adc_Cfg.h`
- `Adc_Common.h`
- `Ap_DiagMgr.h`
- `CDD_Const.h`
- `CDD_Data.h`
- `CalConstants.h`
- `Calconstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Std_Types.h`
- `SystemTime.h`
- `adc_regs.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Adc2_MDD](./doc-Adc2_MDD/) | converted | 371,647 bytes | `Adc/doc/Adc2_MDD.docx` |
| | [Adc_Common_MDD](./doc-Adc_Common_MDD/) | converted | 136,861 bytes | `Adc/doc/Adc_Common_MDD.docx` |
| | [Adc_MDD](./doc-Adc_MDD/) | converted | 335,159 bytes | `Adc/doc/Adc_MDD.docx` |
| | [Integration_Manual_ADC](./doc-Integration_Manual_ADC/) | converted | 45,947 bytes | `Adc/doc/Integration_Manual_ADC.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

