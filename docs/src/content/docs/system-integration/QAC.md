---
title: "Static Analysis Configuration (`QAC`)"
description: "Static-analysis configuration and Modelling rule presets."
---

# Static Analysis Configuration (`QAC`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

## Purpose and responsibility

Static-analysis configuration and Modelling rule presets. It belongs to the **System Integration Project** layer.

## Key files

- Implementation: _No `src/` files (configuration or documentation-only module)._

## Public interface and runnables

No runnable-style entry points were detected by the source scan (library, driver or configuration-only module). See the design documents and headers for the call interface.

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [MISRA Compliance Guidelines](./doc-MISRA_Compliance_Guidelines/) | converted | 548,244 bytes | `QAC/doc/MISRA Compliance Guidelines.docx` | |

## Verification and safety notes

- No `utp/` evidence folder was found for this module.

