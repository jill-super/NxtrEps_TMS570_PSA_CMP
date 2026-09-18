---
title: "PSA Torque Assist Handling (`PSATA`)"
description: "Implements PSA torque-assist handling."
---

# PSA Torque Assist Handling (`PSATA`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Implements PSA torque-assist handling. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_PSATA.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `TrqArbn_Fn`
- `APASupervision_Fn`
- `Cal_ApaNTC`
- `Cal_PosServoSmoothingFactor`
- `LxaSupervision_Fn`
- `Cal_LxaPosSrvoCmdLimit`
- `Cal_LxaPosSrvoSmotngFactor`
- `Cal_LxaPosSrvoSmotng`
- `LxaNTC`
- `Cal_LxaPosSrvoSftySmotngFactor`
- `Cal_LxaOpTrqOv`
- `Cal_OpTrqOv`
- `NTCDiagc_Fn`
- `PSATA_Init1`
- `PSATA_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_PSATA.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [PSATA_Integration Manual](./doc-PSATA_Integration_Manual/) | converted | 82,865 bytes | `PSATA/doc/PSATA_Integration Manual.docx` |
| | [PSATA_MDD](./doc-PSATA_MDD/) | converted | 145,742 bytes | `PSATA/doc/PSATA_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

