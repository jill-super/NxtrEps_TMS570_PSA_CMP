---
title: "Non-Volatile Memory Manager (Flash EEPROM Interface) (`NvMMgr`)"
description: "Manages non-volatile storage through the Flash EEPROM interface."
---

# Non-Volatile Memory Manager (Flash EEPROM Interface) (`NvMMgr`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Manages non-volatile storage through the Flash EEPROM interface. It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/Cd_FeeIf.c`, `src/Fapi_UserDefinedFunctions.c`
- Public headers: `include/Cd_FeeIf.h`
- Generator templates and wiring: `generate/` (`Cd_NvMMgr_Cfg.h.tt`, `Cd_NvMMgr_Generate.bat`, `Cd_NvMMgr_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `FeeIf_Init`
- `Fee_Init`
- `TWrapC_FeeIf_Init`
- `TRUSTED_TWrapS_FeeIf_Init`

## Dependencies (internal includes)

- `Cd_FeeIf.h`
- `Cd_NvMMgr_Cfg.h`
- `F021.h`
- `MemIf_Types.h`
- `Os.h`
- `Std_Types.h`
- `fee.h`
- `trustfct.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Fee_Interface_MDD](./doc-Fee_Interface_MDD/) | converted | 624,155 bytes | `NvMMgr/doc/Fee_Interface_MDD.docx` |
| | [NvMMgr_Integration_Manual](./doc-NvMMgr_Integration_Manual/) | converted | 65,731 bytes | `NvMMgr/doc/NvMMgr_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

