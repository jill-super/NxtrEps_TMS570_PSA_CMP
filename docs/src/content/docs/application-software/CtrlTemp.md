---
title: "Controller Temperature Monitoring (`CtrlTemp`)"
description: "Monitors controller temperature and requests derating or shutdown."
---

# Controller Temperature Monitoring (`CtrlTemp`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Monitors controller temperature and requests derating or shutdown. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_CtrlTemp.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_CtrlTemp_Cfg.arxml.tt`, `Sa_CtrlTemp_Cfg.h.tt`, `Sa_CtrlTemp_Generate.bat`, `Sa_CtrlTemp_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `CtrlTemp_Init1`
- `CtrlTemp_Per1`
- `CtrlTemp_Per2`

## Dependencies (internal includes)

- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_CtrlTemp.h`
- `Sa_CtrlTemp_Cfg.h`
- `filters.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Controller_Temperature_MDD](./doc-Controller_Temperature_MDD/) | converted | 202,944 bytes | `CtrlTemp/doc/Controller_Temperature_MDD.docx` |
| | [CtrlTemp_Integration_Manual](./doc-CtrlTemp_Integration_Manual/) | converted | 39,759 bytes | `CtrlTemp/doc/CtrlTemp_Integration_Manual.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

