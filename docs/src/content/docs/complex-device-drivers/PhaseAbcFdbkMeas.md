---
title: "Motor Phase Current Feedback Measurement (`PhaseAbcFdbkMeas`)"
description: "Measures three-phase motor currents for feedback control and diagnostics."
---

# Motor Phase Current Feedback Measurement (`PhaseAbcFdbkMeas`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Measures three-phase motor currents for feedback control and diagnostics. It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/Cd_PhaseAbcFdbkMeas.c`, `src/PhaseAbcFdbkMeas.c`, `src/PhaseAbcFdbkMeas.het`, `src/PhaseAbcFdbkMeas.lst`
- Public headers: `include/Cd_PhaseAbcFdbkMeas.h`, `include/PhaseAbcFdbkMeas.h`, `include/std_nhet.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `Cd_PhaseAbcFdbkMeas_Init2`
- `Cd_PhaseAbcFdbkMeas_Per1`
- `Get_PhaseAbcFdbkMeas_PhaseFdbk`
- `Cd_PhaseAbcFdbkMeas_Init1`

## Dependencies (internal includes)

- `Cd_PhaseAbcFdbkMeas.h`
- `MemMap.h`
- `PhaseAbcFdbkMeas.h`
- `Rte_Cd_PhaseAbcFdbkMeas.h`
- `Std_Types.h`
- `n2het_regs.h`
- `std_nhet.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [ES36B_PhaseAbcFdbkMeas _Integration_Manual](./doc-ES36B_PhaseAbcFdbkMeas__Integration_Manual/) | summary | 147,968 bytes | `PhaseAbcFdbkMeas/doc/ES36B_PhaseAbcFdbkMeas _Integration_Manual.doc` |
| | [ES36B_PhaseFdbkMeas _MDD](./doc-ES36B_PhaseFdbkMeas__MDD/) | summary | 348,160 bytes | `PhaseAbcFdbkMeas/doc/ES36B_PhaseFdbkMeas _MDD.doc` | |

## Verification and safety notes

- No `utp/` evidence folder was found for this module.

