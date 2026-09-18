---
title: "Tuning Selection Authority (`TuningSelAuth`)"
description: "Authorises which calibration tune is active."
---

# Tuning Selection Authority (`TuningSelAuth`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Authorises which calibration tune is active. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_TuningSelAuth.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_TuningSelAuth_Cfg.arxml.tt`, `Ap_TuningSelAuth_Cfg.h.tt`, `Ap_TuningSelAuth_Generate.bat`, `Ap_TuningSelAuth_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `TuningSelAuth_Init1`
- `TuningSelAuth_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_TuningSelAuth.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [TuningSelAuth_Integration Manual](./doc-TuningSelAuth_Integration_Manual/) | summary | 143,360 bytes | `TuningSelAuth/doc/TuningSelAuth_Integration Manual.doc` |
| | [Tuning_Select_Authority_MDD](./doc-Tuning_Select_Authority_MDD/) | converted | 101,129 bytes | `TuningSelAuth/doc/Tuning_Select_Authority_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

