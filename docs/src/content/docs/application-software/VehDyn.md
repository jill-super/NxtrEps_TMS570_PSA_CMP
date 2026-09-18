---
title: "Vehicle Dynamics Interface (`VehDyn`)"
description: "Interfaces vehicle-dynamics signals."
---

# Vehicle Dynamics Interface (`VehDyn`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Interfaces vehicle-dynamics signals. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_VehDyn.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_VehDyn_Cfg.arxml.tt`, `Ap_VehDyn_Cfg.h.tt`, `Ap_VehDyn_Generate.bat`, `Ap_VehDyn_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `SerialCommMethod`
- `Autocenter_f32`
- `TrvlExclsn`
- `Arbn_f32`
- `SmoothHwPos_f32`
- `VehDyn_Init1`
- `VehDyn_Per1`
- `VehDyn_SCom_ForceCenter`
- `VehDyn_SCom_ResetCenter`
- `VehDyn_Trns1`
- `Rte_IRead_VehDyn_Trns1_HandwheelPosition_HwDeg_f32`
- `Rte_IRead_VehDyn_Trns1_HwAuth_Uls_f32`

## Dependencies (internal includes)

- `Ap_VehDyn_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_VehDyn.h`
- `filters.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [VehDyn_Integration_Manual](./doc-VehDyn_Integration_Manual/) | converted | 78,788 bytes | `VehDyn/doc/VehDyn_Integration_Manual.docx` |
| | [VehDyn_MDD](./doc-VehDyn_MDD/) | converted | 188,724 bytes | `VehDyn/doc/VehDyn_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

