---
title: "Position Servo Control (`PosServo`)"
description: "Position servo used for test/excitation and controlled positioning."
---

# Position Servo Control (`PosServo`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Position servo used for test/excitation and controlled positioning. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_PosServo.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_PosServo_Cfg.arxml.tt`, `Ap_PosServo_Cfg.h.tt`, `Ap_PosServo_Generate.bat`, `Ap_PosServo_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `FilterDesiredAngle`
- `TransitionControl`
- `PIDControl`
- `OutputTorque`
- `PosServo_Init1`
- `PosServo_Per1`

## Dependencies (internal includes)

- `Ap_PosServo_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_PosServo.h`
- `SystemTime.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [PosServo_IntegrationManual](./doc-PosServo_IntegrationManual/) | summary | 132,608 bytes | `PosServo/doc/PosServo_IntegrationManual.doc` |
| | [PosServo_MDD](./doc-PosServo_MDD/) | converted | 101,573 bytes | `PosServo/doc/PosServo_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

