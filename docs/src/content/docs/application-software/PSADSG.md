---
title: "PSA Diagnostic Service Gateway (`PSADSG`)"
description: "Implements the PSA diagnostic service gateway."
---

# PSA Diagnostic Service Gateway (`PSADSG`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Implements the PSA diagnostic service gateway. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_PSADSG.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `PSADSG_Per1`
- `Dampg_Per1`
- `DampgFwl_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_PSADSG.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [PSADSG_IntegrationManual](./doc-PSADSG_IntegrationManual/) | summary | 131,072 bytes | `PSADSG/doc/PSADSG_IntegrationManual.doc` |
| | [PSADSG_MDD](./doc-PSADSG_MDD/) | converted | 98,974 bytes | `PSADSG/doc/PSADSG_MDD.docx` | |

## Verification and safety notes

- No `utp/` evidence folder was found for this module.

