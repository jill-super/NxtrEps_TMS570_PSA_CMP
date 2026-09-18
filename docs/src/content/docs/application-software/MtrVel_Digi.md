---
title: "Motor Velocity Sensing (Digital) (`MtrVel_Digi`)"
description: "Estimates motor velocity from digital position sensors."
---

# Motor Velocity Sensing (Digital) (`MtrVel_Digi`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Estimates motor velocity from digital position sensors. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_MtrVel.c`, `src/Sa_MtrVel2.c`, `src/Sa_MtrVel3.c`
- Public headers: `include/Sa_MtrVel.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_MtrVel2_Cfg.arxml.tt`, `Sa_MtrVel2_Cfg.h.tt`, `Sa_MtrVel2_Generate.bat`, `Sa_MtrVel2_bswmd.arxml`, `Sa_MtrVel_Cfg.arxml.tt`, `Sa_MtrVel_Cfg.h.tt`, `Sa_MtrVel_Generate.bat`, `Sa_MtrVel_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `CalcCoarseVel`
- `MtrVelBlend`
- `RegressionFit`
- `MtrVel_Init`
- `MtrVel_Per1`
- `MtrVel_Per2`
- `MtrVel2_Init`
- `MtrVel2_Per1`
- `MtrVel2_Per2`
- `MtrVel3_Init`
- `MtrVel3_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `Float.h`
- `GlobalMacro.h`
- `MemMap.h`
- `MtrVel_Cfg.h`
- `Rte_Sa_MtrVel.h`
- `Rte_Sa_MtrVel2.h`
- `Rte_Sa_MtrVel3.h`
- `Sa_MtrVel.h`
- `Sa_MtrVel2_Cfg.h`
- `Sa_MtrVel_Cfg.h`
- `Std_Types.h`
- `filters.h`
- `fixmath.h`
- `float.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Motor Velocity_Integration_Manual](./doc-Motor_Velocity_Integration_Manual/) | converted | 34,764 bytes | `MtrVel_Digi/doc/Motor Velocity_Integration_Manual.docx` |
| | [MotorVelocity2_MDD](./doc-MotorVelocity2_MDD/) | summary | 622,592 bytes | `MtrVel_Digi/doc/MotorVelocity2_MDD.doc` |
| | [MotorVelocity3_MDD](./doc-MotorVelocity3_MDD/) | summary | 222,208 bytes | `MtrVel_Digi/doc/MotorVelocity3_MDD.doc` |
| | [MotorVelocity_MDD](./doc-MotorVelocity_MDD/) | summary | 1,378,816 bytes | `MtrVel_Digi/doc/MotorVelocity_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

