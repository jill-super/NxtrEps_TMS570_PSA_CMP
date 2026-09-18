---
title: "Microcontroller Abstraction Layer"
description: "AUTOSAR Microcontroller Abstraction Layer: microcontroller peripherals and memory drivers (Analog-to-Digital Converter, Direct Memory Access, Flash memory, timers, serial interfaces)."
---

# Microcontroller Abstraction Layer

AUTOSAR Microcontroller Abstraction Layer: microcontroller peripherals and memory drivers (Analog-to-Digital Converter, Direct Memory Access, Flash memory, timers, serial interfaces).

## Modules in this layer

| Module (long name) | Directory | Origin |
|---|---|---|
| [Analog-to-Digital Converter Driver](./microcontroller-abstraction/Adc/) | `Adc` | Custom (in-house) |
| [Direct Memory Access Driver](./microcontroller-abstraction/Dma/) | `Dma` | Custom (in-house) |
| [Flash EEPROM Emulation Driver](./microcontroller-abstraction/Fee/) | `Fee` | Third-party — Texas Instruments |
| [Flash Memory Driver (F021 Flash Application Programming Interface)](./microcontroller-abstraction/Fls/) | `Fls` | Third-party — Texas Instruments |

### Vector MICROSAR peripheral drivers (inside the system integration project)

- [Digital Input-Output Driver](./microcontroller-abstraction/BasicSoftware-Dio/) — `Source/Basic Software/Dio`
- [Port Pin Driver](./microcontroller-abstraction/BasicSoftware-Port/) — `Source/Basic Software/Port`
- [General Purpose Timer Driver](./microcontroller-abstraction/BasicSoftware-Gpt/) — `Source/Basic Software/Gpt`
