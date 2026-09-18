---
title: "Hardware Power-Up Sequencing (`HwPwUp`)"
description: "Sequences hardware power-up and initialisation."
---

# Hardware Power-Up Sequencing (`HwPwUp`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Sequences hardware power-up and initialisation. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_HwPwUp.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_HwPwUp_Cfg.arxml.tt`, `Ap_HwPwUp_Cfg.h.tt`, `Ap_HwPwUp_Generate.bat`, `Ap_HwPwUp_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `HwPwUp_Per1`
- `HwPwUp_Trns1`
- `HwPwUp_Trns2`
- `Rte_IWrite_HwPwUp_Trns1_MtrDrvrInitStart_Cnt_lgc`
- `Rte_IWriteRef_HwPwUp_Trns1_MtrDrvrInitStart_Cnt_lgc`
- `Rte_IWrite_HwPwUp_Trns1_PwrDiscATestStart_Cnt_lgc`
- `Rte_IWriteRef_HwPwUp_Trns1_PwrDiscATestStart_Cnt_lgc`
- `Rte_IWrite_HwPwUp_Trns1_PwrDiscBTestStart_Cnt_lgc`
- `Rte_IWriteRef_HwPwUp_Trns1_PwrDiscBTestStart_Cnt_lgc`
- `Rte_IWrite_HwPwUp_Trns1_TMFTestStart_Cnt_lgc`
- `Rte_IWriteRef_HwPwUp_Trns1_TMFTestStart_Cnt_lgc`

## Dependencies (internal includes)

- `Ap_HwPwUp_Cfg.h`
- `CalConstants.h`
- `MemMap.h`
- `Rte_Ap_HwPwUp.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Hardware_Power_Up_MDD](./doc-Hardware_Power_Up_MDD/) | converted | 217,431 bytes | `HwPwUp/doc/Hardware_Power_Up_MDD.docx` |
| | [HwPwUp_Integration_Manual](./doc-HwPwUp_Integration_Manual/) | converted | 39,342 bytes | `HwPwUp/doc/HwPwUp_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

