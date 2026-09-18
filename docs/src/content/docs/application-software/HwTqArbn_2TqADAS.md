---
title: "Handwheel Torque Arbitration for Advanced Driver Assistance Systems (`HwTqArbn_2TqADAS`)"
description: "Arbitrates handwheel torque for advanced driver assistance consumers."
---

# Handwheel Torque Arbitration for Advanced Driver Assistance Systems (`HwTqArbn_2TqADAS`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Arbitrates handwheel torque for advanced driver assistance consumers. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_HwTqArbn.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `ArbnSigAvlChk`
- `HwTqArbn_Init1`
- `HwTqArbn_Per1`
- `HwTqArbn_Per2`
- `HwTqArbn_Per3`
- `HwTrqArbn_SCom_ClrHwTrqArbOffsetTrim`
- `HwTrqArbn_SCom_ReadHwTrqArbOffsetTrim`
- `HwTrqArbn_SCom_SetHwTrqArbOffsetTrim`
- `HwTrqArbn_SCom_WriteHwTrqArbOffsetTrim`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_HwTqArbn.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [HwTqArbn_Integration_Manual](./doc-HwTqArbn_Integration_Manual/) | summary | 147,968 bytes | `HwTqArbn_2TqADAS/doc/HwTqArbn_Integration_Manual.doc` |
| | [HwTqArbn_MDD](./doc-HwTqArbn_MDD/) | summary | 169,472 bytes | `HwTqArbn_2TqADAS/doc/HwTqArbn_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

