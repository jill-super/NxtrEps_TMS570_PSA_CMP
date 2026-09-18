---
title: "Complex Device Drivers"
description: "Hardware-near Complex Device Drivers (AUTOSAR Complex Device Drivers): motor sensing, power stage, memory proxy and microcontroller diagnostics."
---

# Complex Device Drivers

Hardware-near Complex Device Drivers (AUTOSAR Complex Device Drivers): motor sensing, power stage, memory proxy and microcontroller diagnostics.

## Modules in this layer

| Module (long name) | Directory | Origin |
|---|---|---|
| [High-End Timer Configuration and Use](./complex-device-drivers/Nhet1CfgAndUse_35D/) | `Nhet1CfgAndUse_35D` | Custom (in-house) |
| [Non-Volatile Memory Manager (Flash EEPROM Interface)](./complex-device-drivers/NvMMgr/) | `NvMMgr` | Custom (in-house) |
| [Non-Volatile Memory Proxy](./complex-device-drivers/NvMProxy/) | `NvMProxy` | Custom (in-house) |
| [Motor Phase Current Feedback Measurement](./complex-device-drivers/PhaseAbcFdbkMeas/) | `PhaseAbcFdbkMeas` | Custom (in-house) |
| [Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode)](./complex-device-drivers/SVDrvr_CM/) | `SVDrvr_CM` | Custom (in-house) |
| [Shutdown Mechanisms (Safe State Control)](./complex-device-drivers/ShtdnMech/) | `ShtdnMech` | Custom (in-house) |
| [Serial Peripheral Interface Driver](./complex-device-drivers/SpiNxt/) | `SpiNxt` | Custom (in-house) |
| [TMS570 Microcontroller Diagnostics](./complex-device-drivers/TMS570_uDiag/) | `TMS570_uDiag` | Custom (in-house) |
| [Enhanced Pulse-Width Modulation Driver](./complex-device-drivers/ePWM_Up/) | `ePWM_Up` | Custom (in-house) |

### Project-level Complex Device Driver helpers (inside the system integration project)

- [Complex Device Driver Interface](./complex-device-drivers/SystemIntegration-CDDInterface/) — `SwProject/CDDInterface`
- [Serial Communication Driver](./complex-device-drivers/SystemIntegration-SrlComDriver/) — `SwProject/SrlComDriver`
- [Serial Communication Input](./complex-device-drivers/SystemIntegration-SrlComInput/) — `SwProject/SrlComInput`
- [Serial Communication Output](./complex-device-drivers/SystemIntegration-SrlComOutput/) — `SwProject/SrlComOutput`
