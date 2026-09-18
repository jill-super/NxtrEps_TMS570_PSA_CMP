---
title: "PSA Steering Angle Arbitration (`PsaAgArbn`)"
description: "Arbitrates steering-angle sources for PSA vehicle functions."
---

# PSA Steering Angle Arbitration (`PsaAgArbn`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Arbitrates steering-angle sources for PSA vehicle functions. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_PsaAgArbn.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `ESCOffsMngr`
- `OffsConsistencyFltMngt`
- `SnsrMon`
- `SnsrSupv`
- `RecommendedState`
- `GenRawAbsltHwPosnSignals`
- `VehCondChk`
- `SwitchOffs`
- `PsaAgArbn_Init1`
- `PsaAgArbn_Per1`
- `PsaAgArbn_SCom_PsaAaCmd`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_PsaAgArbn.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [PsaAgArbn_IntegrationManual](./doc-PsaAgArbn_IntegrationManual/) | summary | 145,920 bytes | `PsaAgArbn/doc/PsaAgArbn_IntegrationManual.doc` |
| | [PsaAgArbn_MDD](./doc-PsaAgArbn_MDD/) | converted | 125,682 bytes | `PsaAgArbn/doc/PsaAgArbn_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

