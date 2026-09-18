---
title: "Standard Software Library (Filters, Interpolation, Math) (`NxtrLib`)"
description: "Shared math: filters, interpolation, trigonometric helpers, checksums, system time."
---

# Standard Software Library (Filters, Interpolation, Math) (`NxtrLib`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Shared math: filters, interpolation, trigonometric helpers, checksums, system time. It belongs to the **Shared Libraries and Platform Types** layer.

## Key files

- Implementation: `src/CheckSums.c`, `src/SystemTime.c`, `src/atan2.asm`, `src/atan2_octants.c`, `src/filters.c`, `src/interpolation.c`
- Public headers: `include/CheckSums.h`, `include/Filter_Types.h`, `include/GlobalMacro.h`, `include/SinCos.h`, `include/SystemTime.h`, `include/atan2.h`, `include/filters.h`, `include/fixmath.h`, `include/fpmtype.h`, `include/interpolation.h`
- Generator templates and wiring: `generate/` (`SystemTime_Cfg.h.tt`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `BMW_CRC`
- `DtrmnElapsedTime_uS_u16`
- `DtrmnElapsedTime_uS_u32`
- `DtrmnElapsedTime_mS_u16`
- `DtrmnElapsedTime_mS_u32`
- `GetSystemTime_uS_u32`
- `GetSystemTime_mS_u32`
- `SystemTime_Init`
- `SystemTime_Per1`
- `NF_Init_f32`

## Dependencies (internal includes)

- `CheckSums.h`
- `Filter_Types.h`
- `GlobalMacro.h`
- `Gpt.h`
- `Gpt_Cfg.h`
- `MemMap.h`
- `Platform_Types.h`
- `Rte_NexteerLibs.h`
- `Rte_Type.h`
- `Std_Types.h`
- `SystemTime.h`
- `SystemTime_Cfg.h`
- `filters.h`
- `fixmath.h`
- `fpmtype.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Filter_Library_Design_Document](./doc-Filter_Library_Design_Document/) | summary | 370,688 bytes | `NxtrLib/doc/Filter_Library_Design_Document.doc` |
| | [Interpolation_Design_MDD](./doc-Interpolation_Design_MDD/) | summary | 153,600 bytes | `NxtrLib/doc/Interpolation_Design_MDD.doc` |
| | [NxtrLib_Systemtime Integration_Manual](./doc-NxtrLib_Systemtime_Integration_Manual/) | converted | 26,185 bytes | `NxtrLib/doc/NxtrLib_Systemtime Integration_Manual.docx` |
| | [Optimized SinCos Algorithm](./doc-Optimized_SinCos_Algorithm/) | converted | 189,562 bytes | `NxtrLib/doc/Optimized SinCos Algorithm.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

