---
title: "Non-Volatile Memory Proxy (`NvMProxy`)"
description: "Proxies non-volatile requests between application and manager."
---

# Non-Volatile Memory Proxy (`NvMProxy`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Proxies non-volatile requests between application and manager. It belongs to the **Complex Device Drivers** layer.

## Key files

- Implementation: `src/Cd_NvMProxy.c`
- Public headers: `include/Cd_NvMProxy.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Cd_NvMProxy_Cfg.h.tt`, `Cd_NvMProxy_Generate.bat`, `Cd_NvMProxy_PBcfg.c.tt`, `Cd_NvMProxy_bswmd.arxml`, `Cd_NvMProxy_swc.arxml.tt`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `NvMProxy_Init`
- `NvMProxy_MainFunction`
- `NvMProxy_WriteBlock`
- `NvMProxy_WriteAll`
- `NvMProxy_GetErrorStatus`
- `NvMProxy_SetRamBlockStatus`

## Dependencies (internal includes)

- `Cd_NvMProxy.h`
- `Cd_NvMProxy_Cfg.h`
- `Crc.h`
- `MemMap.h`
- `NvM.h`
- `SchM_NvMProxy.h`
- `Std_Types.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [NvMProxy_Integration_Manual](./doc-NvMProxy_Integration_Manual/) | converted | 46,733 bytes | `NvMProxy/doc/NvMProxy_Integration_Manual.docx` |
| | [NvMProxy_MDD](./doc-NvMProxy_MDD/) | converted | 866,432 bytes | `NvMProxy/doc/NvMProxy_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

