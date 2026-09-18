---
title: "Steering Power Assist Control (`Assist`)"
description: "Computes the primary power-assist torque from handwheel torque, vehicle speed and system state."
---

# Steering Power Assist Control (`Assist`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Computes the primary power-assist torque from handwheel torque, vehicle speed and system state. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_Assist.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_Assist_Cfg.arxml.tt`, `Ap_Assist_Cfg.h.tt`, `Ap_Assist_Generate.bat`, `Ap_Assist_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `Assist_Per1`
- `Rte_Call_FltInjection_SCom_FltInjection`

## Dependencies (internal includes)

- `Ap_Assist_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_Assist.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Assist_Integration_Manual](./doc-Assist_Integration_Manual/) | converted | 27,182 bytes | `Assist/doc/Assist_Integration_Manual.docx` |
| | [Assist_MDD](./doc-Assist_MDD/) | converted | 234,628 bytes | `Assist/doc/Assist_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

