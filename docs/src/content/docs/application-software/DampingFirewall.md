---
title: "Damping Firewall (Safety Monitor) (`DampingFirewall`)"
description: "Independently bounds damping torque (safety monitor)."
---

# Damping Firewall (Safety Monitor) (`DampingFirewall`)

:::note[Origin: Custom (in-house)]
In-house software component (Nexteer copyright). File templates may have been expanded by the Vector MICROSAR Runtime Environment Generator / DaVinci tooling (look for the `Generator: MICROSAR RTE Generator` banner), but all control logic, calibration and safety monitoring are in-house.
:::

:::note[Vector template, in-house behaviour]
The implementation file header shows `Generator: MICROSAR RTE Generator`: the file skeleton is Vector-generated, but the control logic below it is in-house. Do not mistake the generator banner for Vector ownership of the behaviour.
:::

## Purpose and responsibility

Independently bounds damping torque (safety monitor). It belongs to the **Application Software** layer.

## Key files

- Implementation: `src/Ap_DampingFirewall.c`
- AUTOSAR description: `autosar/` (DaVinci `*.dcf`, `*.arxml` component and data-type descriptions).
- Generator templates and wiring: `generate/` (`Ap_DampingFirewall_Cfg.arxml.tt`, `Ap_DampingFirewall_Cfg.h.tt`, `Ap_DampingFirewall_Generate.bat`, `Ap_DampingFirewall_bswmd.arxml`).
- Integration and Runtime Environment generation wiring: `tools/` (`Integrate.bat`, `RteGen.bat` where present).

## Public interface and runnables

Entry points found in `src/*.c` (reconstructed by scanning for `FUNC(...)` and periodic/init runnable names):

- `DriverVelCalc`
- `ADDCoefCalc`
- `FilterCoefCalc`
- `GenFddIcCmd`
- `DampingFirewall_Init1`
- `DampingFirewall_Per1`

## Dependencies (internal includes)

- `Ap_DampingFirewall_Cfg.h`
- `CalConstants.h`
- `GlobalMacro.h`
- `MemMap.h`
- `Rte_Ap_DampingFirewall.h`
- `filters.h`
- `fixmath.h`
- `interpolation.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [DampingFirewall_IntegrationManual](./doc-DampingFirewall_IntegrationManual/) | converted | 80,683 bytes | `DampingFirewall/doc/DampingFirewall_IntegrationManual.docx` |
| | [Damping_Firewall_MDD](./doc-Damping_Firewall_MDD/) | summary | 5,539,328 bytes | `DampingFirewall/doc/Damping_Firewall_MDD.doc` | |

## Verification and safety notes

- Unit-test evidence (Tessy reports, plans) is stored under `utp/` and indexed in the [design document inventory](../general/document-inventory/); it is evidence, not specification.
- Safety-relevant monitor/guard: treat changes as safety-relevant and review against the functional-safety notes.

