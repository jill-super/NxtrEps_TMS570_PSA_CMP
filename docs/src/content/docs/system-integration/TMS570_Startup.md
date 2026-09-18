---
title: "TMS570 Microcontroller Startup and Boot (`TMS570_Startup`)"
description: "Boot, reset-cause handling, core initialisation and errata workarounds."
---

# TMS570 Microcontroller Startup and Boot (`TMS570_Startup`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Boot, reset-cause handling, core initialisation and errata workarounds. It belongs to the **System Integration Project** layer.

## Key files

- Implementation: `src/AppStartup.c`, `src/BootStartup.c`, `src/ResetCause.c`, `src/errata_SSWF021_45.c`, `src/fiqintvect.asm`, `src/prooftestv02.c`, `src/prooftestv02.het`, `src/sys_core.asm`, `src/sys_memory.asm`, `src/sys_pmu.asm`, `src/sys_startup.c`
- Public headers: `include/ResetCause.h`, `include/errata_SSWF021_45.h`, `include/errata_SSWF021_45_defs.h`, `include/prooftestv02.h`, `include/sys_core.h`, `include/sys_memory.h`, `include/sys_pmu.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

No runnable-style entry points were detected by the source scan (library, driver or configuration-only module). See the design documents and headers for the call interface.

## Dependencies (internal includes)

- `Compiler.h`
- `MemMap.h`
- `Platform_Types.h`
- `ResetCause.h`
- `Std_Types.h`
- `adc_regs.h`
- `appinit_cfg.h`
- `ccm_regs.h`
- `dcan_regs.h`
- `dma_regs.h`
- `efc_regs.h`
- `errata_SSWF021_45.h`
- `errata_SSWF021_45_defs.h`
- `esm_regs.h`
- `flash_regs.h`
- `gio_regs.h`
- `htu_regs.h`
- `mibspi_regs.h`
- `n2het_regs.h`
- `pbist_regs.h`
- `pcr_regs.h`
- `prooftestv02.h`
- `startup_cfg.h`
- `stc_regs.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [TMS570_Startup_BootStartup_MDD](./doc-TMS570_Startup_BootStartup_MDD/) | converted | 120,511 bytes | `TMS570_Startup/doc/TMS570_Startup_BootStartup_MDD.docx` |
| | [TMS570_Startup_FiqIntVect_MDD](./doc-TMS570_Startup_FiqIntVect_MDD/) | converted | 36,371 bytes | `TMS570_Startup/doc/TMS570_Startup_FiqIntVect_MDD.docx` |
| | [TMS570_Startup_Integration_Manual](./doc-TMS570_Startup_Integration_Manual/) | converted | 46,585 bytes | `TMS570_Startup/doc/TMS570_Startup_Integration_Manual.docx` |
| | [TMS570_Startup_SysCore_MDD](./doc-TMS570_Startup_SysCore_MDD/) | converted | 46,802 bytes | `TMS570_Startup/doc/TMS570_Startup_SysCore_MDD.docx` |
| | [TMS570_Startup_SysStartup_MDD](./doc-TMS570_Startup_SysStartup_MDD/) | converted | 2,132,922 bytes | `TMS570_Startup/doc/TMS570_Startup_SysStartup_MDD.docx` |
| | [TMS570_Startup_errata_SSWF021_45_MDD](./doc-TMS570_Startup_errata_SSWF021_45_MDD/) | converted | 68,670 bytes | `TMS570_Startup/doc/TMS570_Startup_errata_SSWF021_45_MDD.docx` |
| | [spna106a](./doc-spna106a/) | converted | 128,350 bytes | `TMS570_Startup/doc/spna106a.pdf` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

