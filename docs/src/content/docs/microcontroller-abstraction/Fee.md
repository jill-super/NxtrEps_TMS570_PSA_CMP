---
title: "Flash EEPROM Emulation Driver (`Fee`)"
description: "Emulates EEPROM in Flash (Texas Instruments driver)."
---

# Flash EEPROM Emulation Driver (`Fee`)

:::caution[Origin: Third-party — Texas Instruments]
Source headers carry Texas Instruments proprietary notices (Flash EEPROM Emulation / F021 Flash Application Programming Interface). Vendor material under `doc/` is redistributed under the vendor licence.
:::

## Purpose and responsibility

Emulates EEPROM in Flash (Texas Instruments driver). It belongs to the **Microcontroller Abstraction Layer** layer.

## Key files

- Implementation: `src/Device_TMS570LS07.c`, `src/Device_TMS570LS12.c`, `src/fee.c`, `src/ti_fee_Info.c`, `src/ti_fee_cancel.c`, `src/ti_fee_eraseimmediateblock.c`, `src/ti_fee_format.c`, `src/ti_fee_ini.c`, `src/ti_fee_invalidateblock.c`, `src/ti_fee_main.c`, `src/ti_fee_read.c`, `src/ti_fee_readSync.c`, `src/ti_fee_shutdown.c`, `src/ti_fee_util.c`
- Public headers: `include/Device_Header.h`, `include/Device_TMS570LS07.h`, `include/Device_TMS570LS12.h`, `include/Device_types.h`, `include/Fee_Cbk.h`, `include/fee.h`, `include/fee_interface.h`, `include/fee_memmap.h`, `include/ti_fee.h`, `include/ti_fee_cfg.h`, `include/ti_fee_types.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `Fee_Init`
- `TI_Fee_Init`

## Dependencies (internal includes)

- `Det.h`
- `Device_TMS570LS07.h`
- `Device_TMS570LS12.h`
- `Device_header.h`
- `Device_types.h`
- `F021.h`
- `Fee.h`
- `Fee_Cbk.h`
- `Fee_Cfg.h`
- `MemMap.h`
- `SchM_Fee.h`
- `Std_Types.h`
- `fee_cfg.h`
- `fee_interface.h`
- `nvm.h`
- `ti_fee.h`
- `ti_fee_cfg.h`
- `ti_fee_types.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [AutoSAR FEE Parameter Configuration](./doc-AutoSAR_FEE_Parameter_Configuration/) | summary | 382 bytes | `Fee/doc/AutoSAR FEE Parameter Configuration.pdf` |
| | [AutoSAR FEE User Guide](./doc-AutoSAR_FEE_User_Guide/) | converted | 332,504 bytes | `Fee/doc/AutoSAR FEE User Guide.pdf` |
| | [DataSheet_TMS570LS0714](./doc-DataSheet_TMS570LS0714/) | converted | 84,247 bytes | `Fee/doc/DataSheet_TMS570LS0714.pdf` |
| | [DataSheet_TMS570LS1227](./doc-DataSheet_TMS570LS1227/) | converted | 83,874 bytes | `Fee/doc/DataSheet_TMS570LS1227.pdf` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

