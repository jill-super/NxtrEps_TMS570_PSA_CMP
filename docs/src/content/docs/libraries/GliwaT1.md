---
title: "Timing Trace Library (Gliwa T1) (`GliwaT1`)"
description: "Timing-trace instrumentation support."
---

# Timing Trace Library (Gliwa T1) (`GliwaT1`)

:::caution[Origin: Third-party — Gliwa]
Timing-trace library delivered as a prebuilt archive plus a thin in-house glue layer (`Timing Trace Application Interface`).
:::

## Purpose and responsibility

Timing-trace instrumentation support. It belongs to the **Shared Libraries and Platform Types** layer.

## Key files

- Implementation: `src/T1_AppInterface.c`, `src/T1_config.c`, `src/libt1base.a`, `src/libt1com8.a`, `src/libt1cont.a`, `src/libt1delay.a`, `src/libt1flex.a`, `src/libt1mod.a`, `src/libt1scope.a`, `src/sys_pmu.asm`
- Public headers: `include/Metrics.h`, `include/T1_AppInterface.h`, `include/T1_MemMap.h`, `include/T1_baseConfig.h`, `include/T1_baseInterface.h`, `include/T1_bid.h`, `include/T1_config.h`, `include/T1_contConfig.h`, `include/T1_contInterface.h`, `include/T1_delayConfig.h`, `include/T1_delayInterface.h`, `include/T1_flexConfig.h`, `include/T1_flexInterface.h`, `include/T1_modInterface.h`, `include/T1_runnables.h`, `include/T1_scopeConfig.h`, `include/T1_scopeInterface.h`, `include/T1_targetSpecifics.h`, `include/sys_pmu.h`
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `T1_Init`

## Dependencies (internal includes)

- `Std_Types.h`
- `T1_AppInterface.h`
- `T1_AppInterface_Cfg.h`
- `T1_MemMap.h`
- `T1_baseConfig.h`
- `T1_baseInterface.h`
- `T1_bid.h`
- `T1_contConfig.h`
- `T1_delayConfig.h`
- `T1_flexConfig.h`
- `T1_scopeConfig.h`
- `T1_scopeInterface.h`
- `T1_targetSpecifics.h`
- `osek.h`
- `sys_common.h`
- `sys_pmu.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [GliwaT1_IntegrationManual](./doc-GliwaT1_IntegrationManual/) | summary | 512,000 bytes | `GliwaT1/doc/GliwaT1_IntegrationManual.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

