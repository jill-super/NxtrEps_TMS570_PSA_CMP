---
title: "Absolute Handwheel Position (I2C Vehicle Dynamics Interface) (`AbsHwPos_TcI2cVd`)"
description: "Provides absolute handwheel position over the I2C vehicle-dynamics interface."
---

# Absolute Handwheel Position (I2C Vehicle Dynamics Interface) (`AbsHwPos_TcI2cVd`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Provides absolute handwheel position over the I2C vehicle-dynamics interface. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_AbsHwPos.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_AbsHwPos_Cfg.arxml.tt`, `Ap_AbsHwPos_Cfg.h.tt`, `Ap_AbsHwPos_Generate.bat`, `Ap_AbsHwPos_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `TrimNotPerfDiag`
- `AbsHwPos_Init1`
- `AbsHwPos_Per1`
- `AbsHwPos_Per2`
- `AbsHwPos_Per3`
- `AbsHwPos_Per4`
- `AbsHwPos_SCom_CustClrTrim`
- `AbsHwPos_SCom_CustSetTrim`
- `AbsHwPos_SCom_NxtClearTrim`
- `AbsHwPos_SCom_NxtSetTrim`

## Dependencies (internal includes)

- `Ap_AbsHwPos_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_AbsHwPos.h`
- `filters.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [AbsHwPos_TcI2cVd_Integration_Manual](./doc-AbsHwPos_TcI2cVd_Integration_Manual/) | converted | 35,938 bytes | `AbsHwPos_TcI2cVd/doc/AbsHwPos_TcI2cVd_Integration_Manual.docx` |
| | [Absolute_Handwheel_Position_TcI2cVd_MDD](./doc-Absolute_Handwheel_Position_TcI2cVd_MDD/) | converted | 1,073,977 bytes | `AbsHwPos_TcI2cVd/doc/Absolute_Handwheel_Position_TcI2cVd_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

