---
title: "Handwheel Torque Correlation for Advanced Driver Assistance Systems (`HwTqCorrln_2TqADAS`)"
description: "Correlates handwheel torque across redundant paths for driver assistance consumers."
---

# Handwheel Torque Correlation for Advanced Driver Assistance Systems (`HwTqCorrln_2TqADAS`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Correlates handwheel torque across redundant paths for driver assistance consumers. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_HwTqCorrln.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `CorrlnSigAvlChk`
- `HwTqCorrln_Init1`
- `HwTqCorrln_Per1`
- `HwTqCorrln_Per2`
- `HwTqCorrln_Per3`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_HwTqCorrln.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`
- `os.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [HwTqCorrln_Integration_Manual](./doc-HwTqCorrln_Integration_Manual/) | summary | 145,408 bytes | `HwTqCorrln_2TqADAS/doc/HwTqCorrln_Integration_Manual.doc` |
| | [HwTqCorrln_MDD](./doc-HwTqCorrln_MDD/) | summary | 147,968 bytes | `HwTqCorrln_2TqADAS/doc/HwTqCorrln_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

