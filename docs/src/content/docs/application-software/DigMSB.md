---
title: "Digital Motor Sensor Board Interface (`DigMSB`)"
description: "Interfaces the digital motor sensor board (position/current acquisition)."
---

# Digital Motor Sensor Board Interface (`DigMSB`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Interfaces the digital motor sensor board (position/current acquisition). It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Sa_DigMSB.c`
- Public headers: `include/Sa_DigMSB.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Sa_DigMSB_Cfg.arxml.tt`, `Sa_DigMSB_Cfg.h.tt`, `Sa_DigMSB_Generate.bat`, `Sa_DigMSB_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `MtrPosProcessing`
- `ErrorRegisterProcessing`
- `RevCntrProcessing`
- `DigMSB_Init`
- `DigMSB_Per2`
- `DigMSB_Per3`
- `DigMSB_Per1`

## Dependencies (internal includes)

- `CalConstants.h`
- `DigMSB_Cfg.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Sa_DigMSB.h`
- `Sa_DigMSB.h`
- `Sa_DigMSB_Cfg.h`
- `SystemTime.h`
- `fixmath.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [DigMSB_Integration_Manual](./doc-DigMSB_Integration_Manual/) | converted | 82,721 bytes | `DigMSB/doc/DigMSB_Integration_Manual.docx` |
| | [DigtalMSB_MDD](./doc-DigtalMSB_MDD/) | converted | 2,032,904 bytes | `DigMSB/doc/DigtalMSB_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

