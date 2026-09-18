---
title: "High-End Timer Configuration and Use (`Nhet1CfgAndUse_35D`)"
description: "Configures the high-end timer for position/signal capture."
---

# High-End Timer Configuration and Use (`Nhet1CfgAndUse_35D`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Configures the high-end timer for position/signal capture. It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/Cd_Nhet1CfgAndUse.c`, `src/Nhet1CfgAndUse_Prog.c`, `src/Nhet1CfgAndUse_Prog.het`, `src/Nhet1CfgAndUse_Prog.lst`
- Public headers: `include/Cd_Nhet1CfgAndUse.h`, `include/Nhet.h`, `include/Nhet1CfgAndUse_Prog.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `HTU1_Init`
- `HwTqProtocolFault`
- `Nhet1CfgAndUse_Per1`
- `Nhet1CfgAndUse_Per2`
- `Nhet1CfgAndUse_Init`
- `Nhet1CfgAndUse_Per3`

## Dependencies (internal includes)

- `CalConstants.h`
- `Cd_Nhet1CfgAndUse.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Nhet1CfgAndUse_Cfg.h`
- `Nhet1CfgAndUse_Prog.h`
- `Rte_Cd_Nhet1CfgAndUse.h`
- `Std_Types.h`
- `htu_regs.h`
- `n2het_regs.h`
- `std_nhet.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [NHetRegisters](./doc-NHetRegisters/) | converted | 1,931,073 bytes | `Nhet1CfgAndUse_35D/doc/NHetRegisters.pdf` |
| | [Nhet1CfgAndUse_Integration_Manual](./doc-Nhet1CfgAndUse_Integration_Manual/) | summary | 206,848 bytes | `Nhet1CfgAndUse_35D/doc/Nhet1CfgAndUse_Integration_Manual.doc` |
| | [Nhet1CfgAndUse_MDD](./doc-Nhet1CfgAndUse_MDD/) | summary | 985,088 bytes | `Nhet1CfgAndUse_35D/doc/Nhet1CfgAndUse_MDD.doc` | |

## Verification and safety notes

- No `utp/` evidence folder was found for this module.

