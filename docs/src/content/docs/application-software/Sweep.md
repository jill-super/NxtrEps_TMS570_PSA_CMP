---
title: "Frequency Sweep Excitation (Test Support) (`Sweep`)"
description: "Generates frequency-sweep excitation for identification and test."
---

# Frequency Sweep Excitation (Test Support) (`Sweep`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Generates frequency-sweep excitation for identification and test. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_Sweep.c`, `src/Ap_Sweep2.c`
- Public headers: `include/Ap_Sweep.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_Sweep2_Cfg.arxml.tt`, `Ap_Sweep2_Cfg.h.tt`, `Ap_Sweep2_Generate.bat`, `Ap_Sweep2_bswmd.arxml`, `Ap_Sweep_Cfg.arxml.tt`, `Ap_Sweep_Cfg.h.tt`, `Ap_Sweep_Generate.bat`, `Ap_Sweep_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `Sweep_Init`
- `Sweep_Per1`
- `Sweep2_Per1`

## Dependencies (internal includes)

- `Ap_Sweep.h`
- `Ap_Sweep2_Cfg.h`
- `Ap_Sweep_Cfg.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_Sweep.h`
- `Rte_Ap_Sweep2.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Sweep1_MDD](./doc-Sweep1_MDD/) | converted | 533,878 bytes | `Sweep/doc/Sweep1_MDD.docx` |
| | [Sweep2_MDD](./doc-Sweep2_MDD/) | converted | 108,521 bytes | `Sweep/doc/Sweep2_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

