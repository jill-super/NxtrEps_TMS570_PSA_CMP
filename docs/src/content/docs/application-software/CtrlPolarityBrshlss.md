---
title: "Controller Polarity Detection (Brushless Motor) (`CtrlPolarityBrshlss`)"
description: "Detects and applies brushless control polarity."
---

# Controller Polarity Detection (Brushless Motor) (`CtrlPolarityBrshlss`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Detects and applies brushless control polarity. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_CtrlPolarityBrshlss.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `GetPolarity`
- `Polarity_Init1`
- `Polarity_SCom_ReadPolarity`
- `Polarity_SCom_SetPolarity`

## Dependencies (internal includes)

- `MemMap.h`
- `Os.h`
- `Rte_Ap_CtrlPolarityBrshlss.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Integration Manual CtrlPolarityBrshlss](./doc-Integration_Manual_CtrlPolarityBrshlss/) | summary | 152,064 bytes | `CtrlPolarityBrshlss/doc/Integration Manual CtrlPolarityBrshlss.doc` |
| | [MDD CtrlPolarityBrshlss](./doc-MDD_CtrlPolarityBrshlss/) | summary | 776,704 bytes | `CtrlPolarityBrshlss/doc/MDD CtrlPolarityBrshlss.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

