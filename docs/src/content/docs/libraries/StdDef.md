---
title: "Standard Type Definitions (AUTOSAR Platform Types) (`StdDef`)"
description: "AUTOSAR platform and compiler abstractions shared by all modules."
---

# Standard Type Definitions (AUTOSAR Platform Types) (`StdDef`)

:::caution[Origin: Vector-provided]
AUTOSAR platform and compiler abstraction (`Platform_Types`, compiler abstraction) from the Vector MICROSAR scope.
:::

## Purpose and responsibility

AUTOSAR platform and compiler abstractions shared by all modules. It belongs to the **Shared Libraries and Platform Types** layer.

## Key files

- Implementation: _No `src/` files (configuration or documentation-only module)._
- Public headers: `include/Compiler.h`, `include/Platform_Types.h`, `include/Std_Types.h`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).

## Public interface and runnables

No runnable-style entry points were detected by the source scan (library, driver or configuration-only module). See the design documents and headers for the call interface.

## Dependencies (internal includes)

- `Compiler_Cfg.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| _No design documents in `doc/`._ |

## Verification and safety notes

- No `utp/` evidence folder was found for this module.

