---
title: "Torque Loss-of-Assist Handling (`TrqLOA`)"
description: "Manages torque behaviour under loss-of-assist degradation."
---

# Torque Loss-of-Assist Handling (`TrqLOA`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Manages torque behaviour under loss-of-assist degradation. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_TrqLOA.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_TrqLOA_Cfg.arxml.tt`, `Ap_TrqLOA_Cfg.h.tt`, `Ap_TrqLOA_Generate.bat`, `Ap_TrqLOA_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `TrqLOA_Init1`
- `TrqLOA_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_TrqLOA.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [TrqLOA_IntegrationManual](./doc-TrqLOA_IntegrationManual/) | converted | 80,968 bytes | `TrqLOA/doc/TrqLOA_IntegrationManual.docx` |
| | [TrqLOA_MDD](./doc-TrqLOA_MDD/) | summary | 193,024 bytes | `TrqLOA/doc/TrqLOA_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.
- Safety-relevant monitor/guard: treat changes as safety-relevant and review against the functional-safety notes.

