---
title: "Serial Peripheral Interface Driver (`SpiNxt`)"
description: "Serial Peripheral Interface driver for on-board peripherals."
---

# Serial Peripheral Interface Driver (`SpiNxt`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Serial Peripheral Interface driver for on-board peripherals. It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/SpiNxt.c`, `src/SpiNxt_Irq.c`
- Public headers: `include/SpiNxt.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`SpiNxt_Cfg.h.tt`, `SpiNxt_Generate.bat`, `SpiNxt_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `mibspiEnableGroupNotification`
- `mibspiSetData8`
- `mibspiGetData8`
- `SpiNxt_SetupEB`
- `SpiNxt_GetSequenceResult`
- `SpiNxt_AsyncTransmit`
- `SpiNxt_Init`
- `mibspiSetData`
- `mibspiSetCtrlData`
- `mibspiGetData`
- `mibspiTransfer`
- `mibspiNotification`
- `mibspiGroupNotification`

## Dependencies (internal includes)

- `Dio.h`
- `MemMap.h`
- `Metrics.h`
- `Os.h`
- `SchM_SpiNxt.h`
- `Spi.h`
- `SpiNxt.h`
- `SpiNxt_Cfg.h`
- `Std_Types.h`
- `mibspi_regs.h`
- `sys_common.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Spi_Nexteer_Integration_Manual](./doc-Spi_Nexteer_Integration_Manual/) | converted | 41,336 bytes | `SpiNxt/doc/Spi_Nexteer_Integration_Manual.docx` |
| | [Spi_Nexteer_MDD](./doc-Spi_Nexteer_MDD/) | converted | 1,444,708 bytes | `SpiNxt/doc/Spi_Nexteer_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

