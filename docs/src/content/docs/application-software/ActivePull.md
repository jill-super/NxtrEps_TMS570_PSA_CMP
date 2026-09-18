---
title: "Active Pull Compensation (`ActivePull`)"
description: "Compensates steady pull/drift so the vehicle tracks straight with minimal driver effort."
---

# Active Pull Compensation (`ActivePull`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Compensates steady pull/drift so the vehicle tracks straight with minimal driver effort. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_ActivePull.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_ActivePull_Cfg.arxml.tt`, `Ap_ActivePull_Cfg.h.tt`, `Ap_ActivePull_Generate.bat`, `Ap_ActivePull_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `ActvCmpEna_lgc`
- `CalcIntGain_f32`
- `ActivePull_Init1`
- `ActivePull_Per1`
- `ActivePull_Per2`
- `ActivePull_Per3`
- `ActivePull_SCom_ReadParam`
- `ActivePull_SCom_Reset`
- `ActivePull_SCom_SetLTComp`
- `ActivePull_SCom_SetSTComp`
- `ActivePull_Trns1`
- `ActivePull_Trns2`
- `Rte_Call_FaultInjection_SCom_FltInjection`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_ActivePull.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [ActivePullCmp_Integration Manual](./doc-ActivePullCmp_Integration_Manual/) | summary | 156,160 bytes | `ActivePull/doc/ActivePullCmp_Integration Manual.doc` |
| | [Active_Pull_Comp_MDD](./doc-Active_Pull_Comp_MDD/) | converted | 2,162,924 bytes | `ActivePull/doc/Active_Pull_Comp_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

