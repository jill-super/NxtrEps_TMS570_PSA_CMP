---
title: "Fault Injection (Test Support) (`FltInjection`)"
description: "Injects faults for verification of diagnostics and monitors."
---

# Fault Injection (Test Support) (`FltInjection`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Injects faults for verification of diagnostics and monitors. It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_FltInjection.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `FltInjection_Per1`
- `FltInjection_SCom_FltInjection`

## Dependencies (internal includes)

- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_FltInjection.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [Fault_Injection_MDD](./doc-Fault_Injection_MDD/) | converted | 247,709 bytes | `FltInjection/doc/Fault_Injection_MDD.docx` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.

