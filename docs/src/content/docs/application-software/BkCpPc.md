---
title: "Bulk Capacitor Pre-Charge Control (`BkCpPc`)"
description: "Pre-charges the bulk capacitor before enabling the power stage."
---

# Bulk Capacitor Pre-Charge Control (`BkCpPc`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Pre-charges the bulk capacitor before enabling the power stage. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_BkCpPc.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_BkCpPc_Cfg.arxml.tt`, `Sa_BkCpPc_Cfg.h.tt`, `Sa_BkCpPc_Generate.bat`, `Sa_BkCpPc_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `BkCpPc_Per1`
- `BkCpPc_Trns1`
- `BkCpPc_Trns2`
- `CapPcDcStub_OP_SET`
- `Rte_IWrite_BkCpPc_Trns1_PwrDiscATestComplete_Cnt_lgc`
- `Rte_IWriteRef_BkCpPc_Trns1_PwrDiscATestComplete_Cnt_lgc`
- `Rte_IWrite_BkCpPc_Trns1_PwrDiscBTestComplete_Cnt_lgc`
- `Rte_IWriteRef_BkCpPc_Trns1_PwrDiscBTestComplete_Cnt_lgc`
- `Rte_IWrite_BkCpPc_Trns2_PwrDiscATestComplete_Cnt_lgc`
- `Rte_IWriteRef_BkCpPc_Trns2_PwrDiscATestComplete_Cnt_lgc`
- `Rte_IWrite_BkCpPc_Trns2_PwrDiscBTestComplete_Cnt_lgc`
- `Rte_IWriteRef_BkCpPc_Trns2_PwrDiscBTestComplete_Cnt_lgc`
- `Rte_IWrite_BkCpPc_Trns2_PwrDiscClosed_Cnt_lgc`
- `Rte_IWriteRef_BkCpPc_Trns2_PwrDiscClosed_Cnt_lgc`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_BkCpPc.h`
- `Sa_BkCpPc_Cfg.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Bulk_Cap_Precharge_MDD](./doc-Bulk_Cap_Precharge_MDD/) | converted | 1,109,386 bytes | `BkCpPc/doc/Bulk_Cap_Precharge_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

