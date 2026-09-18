---
title: "States and Modes (System State Manager) (`StaMd`)"
description: "Owns system states and modes and their transitions."
---

# States and Modes (System State Manager) (`StaMd`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Owns system states and modes and their transitions. It belongs to the **Basic Software — Services and ECU Abstraction** layer.

## Key files

- Implementation: `src/Ap_StaMd.c`
- Public headers: `include/Ap_StaMd.h`
- Generator templates and wiring: `generate/` (`Ap_StaMd_Cfg.c.tt`, `Ap_StaMd_Cfg.h.tt`, `Ap_StaMd_Generate.bat`, `Ap_StaMd_Proxy.c.tt`, `Ap_StaMd_bswmd.arxml`, `Ap_StaMd_swc.arxml.tt`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `BldTranVctr`
- `ReadTypeH`
- `WriteTypeH`
- `CheckWarmInitComplete`
- `StaMd_Init0`
- `StaMd_Init1`
- `StaMd_Per1`
- `StaMd_Trns1`
- `MilestoneRqst_WarmInitMilestoneComplete`
- `MilestoneRqst_WarmInitMilestoneNotComplete`
- `StaMd_SCom_EcuReset`
- `StaMd_SCom_FBLTransitionReq`
- `SystemStateCheck`

## Dependencies (internal includes)

- `Ap_StaMd_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Os.h`
- `Rte_Ap_StaMd.h`
- `Rte_Type.h`
- `Std_Types.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [StaMd_Integration_Manual](./doc-StaMd_Integration_Manual/) | converted | 38,377 bytes | `StaMd/doc/StaMd_Integration_Manual.docx` |
| | [States_And_Modes_GeneratedConfiguration_MDD](./doc-States_And_Modes_GeneratedConfiguration_MDD/) | converted | 211,813 bytes | `StaMd/doc/States_And_Modes_GeneratedConfiguration_MDD.docx` |
| | [States_And_Modes_MDD](./doc-States_And_Modes_MDD/) | converted | 928,446 bytes | `StaMd/doc/States_And_Modes_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

