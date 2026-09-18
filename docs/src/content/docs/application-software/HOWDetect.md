---
title: "Hands-Off-Wheel Detection (`HOWDetect`)"
description: "Detects hands-off-wheel condition."
---

# Hands-Off-Wheel Detection (`HOWDetect`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Detects hands-off-wheel condition. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_HOWDetect.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_HOWDetect_Cfg.arxml.tt`, `Ap_HOWDetect_Cfg.h.tt`, `Ap_HOWDetect_Generate.bat`, `Ap_HOWDetect_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `HOWDetect_Init1`
- `HOWDetect_Per1`

## Dependencies (internal includes)

- `Ap_HOWDetect_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_HOWDetect.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [HOWDetect_Integration_Manual](./doc-HOWDetect_Integration_Manual/) | converted | 39,574 bytes | `HOWDetect/doc/HOWDetect_Integration_Manual.docx` |
| | [HOWDetect_MDD](./doc-HOWDetect_MDD/) | converted | 343,944 bytes | `HOWDetect/doc/HOWDetect_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.
- Safety-relevant monitor/guard: treat changes as safety-relevant and review against the functional-safety notes.

