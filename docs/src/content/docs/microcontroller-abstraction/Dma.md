---
title: "Direct Memory Access Driver (`Dma`)"
description: "Moves peripheral data without core load."
---

# Direct Memory Access Driver (`Dma`)

:::note[Origin: Custom (in-house)]
In-house driver written for this Electronic Control Unit (Nexteer copyright). It plays a Microcontroller Abstraction role but is not Vector MICROSAR code.
:::

## Purpose and responsibility

Moves peripheral data without core load. It belongs to the **Microcontroller Abstraction Layer** layer.

## Key files

- Implementation: `src/Dma.c`
- Public headers: `include/Dma.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `Dma_Init`
- `Dma_SlowADCGroupValidity`
- `Dma_InvalidateSlowADCGroup`
- `Dma_SetupMtrCtrlGroups`
- `Dma_SetupFlsTstBlock`
- `Dma_EnableFlsTstBlock`
- `Dma_DisableFlsTstBlock`

## Dependencies (internal includes)

- `Adc.h`
- `Adc2.h`
- `Dma.h`
- `Dma_Cfg.h`
- `MemMap.h`
- `SpiNxt.h`
- `appinit_cfg.h`
- `crc_regs.h`
- `dma_regs.h`
- `epwm_regs.h`
- `mibspi_regs.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Dma Integration Manual](./doc-Dma_Integration_Manual/) | converted | 292,839 bytes | `Dma/doc/Dma Integration Manual.docx` |
| | [Dma_MDD](./doc-Dma_MDD/) | converted | 388,442 bytes | `Dma/doc/Dma_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

