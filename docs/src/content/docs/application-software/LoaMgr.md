---
title: "Loss-of-Assist Management (`LoaMgr`)"
description: "Manages loss-of-assist degradation and recovery."
---

# Loss-of-Assist Management (`LoaMgr`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Manages loss-of-assist degradation and recovery. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_LoaMgr.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `CalcIvtrState`
- `LatchInputs`
- `RqstRespConds`
- `RqstHwTqResp`
- `ArbResp`
- `ChooseFinalResp`
- `AssignScale`
- `SwBasMtgtn`
- `LoaMgr_Init1`
- `LoaMgr_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_LoaMgr.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [LOAMgr_IntegrationManual](./doc-LOAMgr_IntegrationManual/) | converted | 75,954 bytes | `LoaMgr/doc/LOAMgr_IntegrationManual.docx` |
| | [LoaMgr_MDD](./doc-LoaMgr_MDD/) | summary | 224,256 bytes | `LoaMgr/doc/LoaMgr_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.
- Safety-relevant monitor/guard: treat changes as safety-relevant and review against the functional-safety notes.

