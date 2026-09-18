---
title: "Basic Software — Services and ECU Abstraction"
description: "AUTOSAR Basic Software services (diagnostics, memory, mode management), ECU abstraction and communication services. Vector MICROSAR modules appear here next to in-house service components."
---

# Basic Software — Services and ECU Abstraction

AUTOSAR Basic Software services (diagnostics, memory, mode management), ECU abstraction and communication services. Vector MICROSAR modules appear here next to in-house service components.

## Modules in this layer

| Module (long name) | Directory | Origin |
|---|---|---|
| [Diagnostics Manager](./basic-software/DiagMgr/) | `DiagMgr` | Custom (in-house) |
| [States and Modes (System State Manager)](./basic-software/StaMd/) | `StaMd` | Custom (in-house) |

### Vector MICROSAR Basic Software stack (inside the system integration project)

These sources live under the integration project (`Source/Basic Software`) and are documented individually:

- [Controller Area Network Driver and Interface](./basic-software/BasicSoftware-Can/) — `Source/Basic Software/Can`
- [Cyclic Redundancy Check Library](./basic-software/BasicSoftware-Crc/) — `Source/Basic Software/Crc`
- [Diagnostic Event Manager](./basic-software/BasicSoftware-Dem/) — `Source/Basic Software/Dem`
- [Default Error Tracer](./basic-software/BasicSoftware-Det/) — `Source/Basic Software/Det`
- [Electronic Control Unit State Manager](./basic-software/BasicSoftware-EcuM/) — `Source/Basic Software/EcuM`
- [Interaction Layer (Signal Gateway)](./basic-software/BasicSoftware-Il/) — `Source/Basic Software/Il`
- [Input-Output Hardware Abstraction](./basic-software/BasicSoftware-IoHwAb/) — `Source/Basic Software/IoHwAb`
- [Memory Abstraction Interface](./basic-software/BasicSoftware-MemIf/) — `Source/Basic Software/MemIf`
- [Non-Volatile Random Access Memory Manager](./basic-software/BasicSoftware-NvM/) — `Source/Basic Software/NvM`
- [Operating System (OSEK/AUTOSAR OS)](./basic-software/BasicSoftware-Os/) — `Source/Basic Software/Os`
- [Transport Protocol](./basic-software/BasicSoftware-Tp/) — `Source/Basic Software/Tp`
- [Vector Standard Library](./basic-software/BasicSoftware-VStdLib/) — `Source/Basic Software/VStdLib`
- [Universal Measurement and Calibration Protocol Interface](./basic-software/BasicSoftware-Xcp/) — `Source/Basic Software/Xcp`
- [Diagnostic Event Manager Interface](./basic-software/BasicSoftware-DemIf/) — `Source/Basic Software/DemIf`
- [Diagnostic Services](./basic-software/BasicSoftware-DiagSvc/) — `Source/Basic Software/DiagSvc`
- [Fault Logging](./basic-software/BasicSoftware-FaultLog/) — `Source/Basic Software/FaultLog`
- [Vehicle Power Mode Management](./basic-software/BasicSoftware-VehPwrMd/) — `Source/Basic Software/VehPwrMd`
