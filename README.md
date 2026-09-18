# Electric Power Steering (EPS) System for PSA CMP

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Language: C](https://img.shields.io/badge/language-C-blue.svg)
![Standard: AUTOSAR](https://img.shields.io/badge/standard-AUTOSAR-4CAF50.svg)
![Safety: ISO 26262 ASIL D](https://img.shields.io/badge/safety-ISO_26262_ASIL_D-red.svg)
![Docs: Astro Starlight](https://img.shields.io/badge/docs-Astro_Starlight-BC52EE.svg)
![Microcontroller: TMS570](https://img.shields.io/badge/microcontroller-TMS570-orange.svg)

> **Documentation site:** the full AUTOSAR-layered reference lives in [`docs/`](docs/) (Astro + Starlight project; start at [`docs/src/content/docs/index.md`](docs/src/content/docs/index.md)). Badges above are static on purpose so repository forks keep working without edits.

An AUTOSAR-based Electric Power Steering controller firmware for the PSA Common Modular Platform, targeting the Texas Instruments TMS570 microcontroller and developed to ISO 26262 ASIL D processes. Most control logic is C; Windows batch files and generator templates wire the Vector MICROSAR tooling (DaVinci Configurator, Runtime Environment Generator).

- **Module titles everywhere use expanded long names** (short directory names are kept in code spans, e.g. Steering Power Assist Control (`Assist`)). The [glossary](docs/src/content/docs/general/glossary.md) lists every expansion.

## Table of contents

- [Features](#features)
- [Repository structure](#repository-structure)
- [AUTOSAR layers and module origins](#autosar-layers-and-module-origins)
- [Vector-provided versus in-house code](#vector-provided-versus-in-house-code)
- [Installation and build](#installation-and-build)
- [Documentation](#documentation)
- [PSA Common Modular Platform vehicles](#psa-common-modular-platform-vehicles)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Precise power-assisted steering control** — base assist, damping, return, hysteresis and stability compensation, plus high-frequency and frequency-dependent paths.
- **Functional-safety monitoring** — independent firewall software components for assist, damping, return and end-of-travel damping; torque reasonableness diagnostics; temporal (program-flow) monitors; shutdown and loss-of-assist management.
- **Vehicle integration** — handwheel torque arbitration and correlation for Advanced Driver Assistance Systems, steering-angle arbitration, vehicle-dynamics and vehicle-speed interfaces, PSA state handling and diagnostic gateways.
- **AUTOSAR foundation** — Vector MICROSAR Basic Software and Runtime Environment, DaVinci-generated configuration, Texas Instruments Flash drivers, TTTech watchdog stack.
- **Calibration and diagnostics** — Universal Measurement and Calibration Protocol interface, Diagnostics Manager with Diagnostic Event Manager interface and fail-actions, non-volatile memory management with Flash EEPROM Emulation.

## Repository structure

```text
<repository root>/
├── docs/                                   # Documentation site (Astro + Starlight project root)
│   ├── astro.config.mjs                    # Starlight config; Pages URL derived from origin remote
│   ├── package.json
│   └── src/content/docs/                   # Site content, organised by AUTOSAR layer
│       ├── application-software/           # Application Software modules + converted design docs
│       ├── complex-device-drivers/         # Complex Device Driver modules + converted design docs
│       ├── basic-software/                 # Basic Software services + Vector stack pages
│       ├── microcontroller-abstraction/    # Microcontroller Abstraction drivers
│       ├── runtime-environment/            # Runtime Environment + generated configuration notes
│       ├── libraries/                      # Shared libraries and platform types
│       ├── system-integration/             # Top-level integration project notes
│       └── general/                        # Glossary, build guide, safety notes, inventory
├── <Module>/                               # One folder per software component, e.g. Steering Power Assist Control (Assist)/
│   ├── src/                                # Component implementation (*.c)
│   ├── include/                            # Public headers (where present)
│   ├── autosar/                            # AUTOSAR description (DaVinci *.dcf, *.arxml)
│   ├── generate/                           # Generator templates (*.tt) + generation batch files
│   ├── tools/                              # Integration / Runtime Environment generation wiring
│   ├── doc/                                # Model Design Documents + integration manuals (Word/PDF originals)
│   └── utp/                                # Unit-test plans and Tessy evidence (indexed, not converted)
├── PSA_CMP_EPS_TMS570/                     # System integration project (SwProject, High-Level Design Documents, Tools)
├── LICENSE                                 # MIT License
└── README.md                               # This file
```

Each software-component folder follows the same inner layout (`src/`, `autosar/`, `generate/`, `tools/`, `doc/`, `utp/`); only the file prefixes differ (`Ap_` = Application Software Component, `Sa_` = Sensor/Actuator Software Component, `Cd_` = Complex Device Driver).

## AUTOSAR layers and module origins


<details>
<summary><strong>Application Software</strong> — 58 modules (click to expand)</summary>

| Module (long name) | Directory | Origin |
|---|---|---|
| Absolute Handwheel Position (I2C Vehicle Dynamics Interface) | `AbsHwPos_TcI2cVd` | Custom (in-house) |
| Active Pull Compensation | `ActivePull` | Custom (in-house) |
| Steering Power Assist Control | `Assist` | Custom (in-house) |
| Steering Assist Firewall (Safety Monitor) | `AssistFirewall` | Custom (in-house) |
| Assist Summation Limiter (Current Mode) | `AstLmt_CM` | Custom (in-house) |
| Average Friction Learning | `AvgFricLrn` | Custom (in-house) |
| Battery Voltage Diagnostics | `BVDiag` | Custom (in-house) |
| Battery Voltage Sensing | `BatteryVoltage` | Custom (in-house) |
| Bulk Capacitor Pre-Charge Control | `BkCpPc` | Custom (in-house) |
| Commutated Motor Current Measurement | `CmMtrCurr` | Custom (in-house) |
| Compliance Error Handling | `ComplErr` | Custom (in-house) |
| Controller Polarity Detection (Brushless Motor) | `CtrlPolarityBrshlss` | Custom (in-house) |
| Controller Temperature Monitoring | `CtrlTemp` | Custom (in-house) |
| Steering Damping Control | `Damping` | Custom (in-house) |
| Damping Firewall (Safety Monitor) | `DampingFirewall` | Custom (in-house) |
| Digital Motor Sensor Board Interface | `DigMSB` | Custom (in-house) |
| End-of-Travel Actuator Management | `EOTActuatorMng` | Custom (in-house) |
| Electric Power Consumption Management | `ElePwr` | Custom (in-house) |
| End-of-Travel Damping Firewall | `EtDmpFw` | Custom (in-house) |
| Fault Injection (Test Support) | `FltInjection` | Custom (in-house) |
| Frequency-Dependent Damping and Inertia Compensation | `FrqDepDmpnInrtCmp` | Custom (in-house) |
| Hands-Off-Wheel Detection | `HOWDetect` | Custom (in-house) |
| High-Load Stall Management | `HiLoadStall` | Custom (in-house) |
| High-Frequency Assist Control | `HighFreqAssist` | Custom (in-house) |
| Hardware Power-Up Sequencing | `HwPwUp` | Custom (in-house) |
| Handwheel Torque Arbitration for Advanced Driver Assistance Systems | `HwTqArbn_2TqADAS` | Custom (in-house) |
| Handwheel Torque Correlation for Advanced Driver Assistance Systems | `HwTqCorrln_2TqADAS` | Custom (in-house) |
| Hysteresis Compensation | `HystComp` | Custom (in-house) |
| Limiter Conditioning | `LmtCod` | Custom (in-house) |
| Loss-of-Assist Management | `LoaMgr` | Custom (in-house) |
| End-of-Travel Learning | `LrnEOT` | Custom (in-house) |
| Motor Control (Current Mode) | `MtrCtrl_CM` | Custom (in-house) |
| Motor Temperature Estimation | `MtrTempEst` | Custom (in-house) |
| Motor Velocity Sensing (Digital) | `MtrVel_Digi` | Custom (in-house) |
| Over-Voltage Monitor | `OvrVoltMon` | Custom (in-house) |
| PSA Diagnostic Message Queue | `PSADMQ` | Custom (in-house) |
| PSA Diagnostic Service Gateway | `PSADSG` | Custom (in-house) |
| PSA State Handler | `PSAStHdlr` | Custom (in-house) |
| PSA Torque Assist Handling | `PSATA` | Custom (in-house) |
| Position Servo Control | `PosServo` | Custom (in-house) |
| PSA Steering Angle Arbitration | `PsaAgArbn` | Custom (in-house) |
| Power Limit Function (Current Regulation) | `PwrLmtFuncCr` | Custom (in-house) |
| Steering Return Control | `Return` | Custom (in-house) |
| Steering Return Firewall (Safety Monitor) | `ReturnFirewall` | Custom (in-house) |
| Motor Driver Diagnostics (Servo Drive Diagnostics) | `SVDiag` | Custom (in-house) |
| Signal Conditioning | `SgnlCond` | Custom (in-house) |
| State Output Control | `StOpCtrl` | Custom (in-house) |
| Stability Compensation | `StabilityComp` | Custom (in-house) |
| Frequency Sweep Excitation (Test Support) | `Sweep` | Custom (in-house) |
| Thermal Duty Cycle Management | `ThrmDutyCycle` | Custom (in-house) |
| Temporal Monitor (Program Flow Monitoring) | `TmprlMon` | Custom (in-house) |
| Torque Reasonableness Diagnostics | `TqRsDg` | Custom (in-house) |
| Translational Damping Control | `TranlDampg` | Custom (in-house) |
| Torque Loss-of-Assist Handling | `TrqLOA` | Custom (in-house) |
| Tuning Selection Authority | `TuningSelAuth` | Custom (in-house) |
| Vehicle Dynamics Interface | `VehDyn` | Custom (in-house) |
| Vehicle Speed Limiter | `VehSpdLmt` | Custom (in-house) |
| Universal Measurement and Calibration Protocol Interface | `Xcp` | Custom (in-house) |

</details>

<details>
<summary><strong>Complex Device Drivers</strong> — 9 modules (click to expand)</summary>

| Module (long name) | Directory | Origin |
|---|---|---|
| High-End Timer Configuration and Use | `Nhet1CfgAndUse_35D` | Custom (in-house) |
| Non-Volatile Memory Manager (Flash EEPROM Interface) | `NvMMgr` | Custom (in-house) |
| Non-Volatile Memory Proxy | `NvMProxy` | Custom (in-house) |
| Motor Phase Current Feedback Measurement | `PhaseAbcFdbkMeas` | Custom (in-house) |
| Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode) | `SVDrvr_CM` | Custom (in-house) |
| Shutdown Mechanisms (Safe State Control) | `ShtdnMech` | Custom (in-house) |
| Serial Peripheral Interface Driver | `SpiNxt` | Custom (in-house) |
| TMS570 Microcontroller Diagnostics | `TMS570_uDiag` | Custom (in-house) |
| Enhanced Pulse-Width Modulation Driver | `ePWM_Up` | Custom (in-house) |

</details>

<details>
<summary><strong>Basic Software — Services and ECU Abstraction</strong> — 2 modules (click to expand)</summary>

| Module (long name) | Directory | Origin |
|---|---|---|
| Diagnostics Manager | `DiagMgr` | Custom (in-house) |
| States and Modes (System State Manager) | `StaMd` | Custom (in-house) |

</details>

<details>
<summary><strong>Microcontroller Abstraction Layer</strong> — 4 modules (click to expand)</summary>

| Module (long name) | Directory | Origin |
|---|---|---|
| Analog-to-Digital Converter Driver | `Adc` | Custom (in-house) |
| Direct Memory Access Driver | `Dma` | Custom (in-house) |
| Flash EEPROM Emulation Driver | `Fee` | Third-party — Texas Instruments |
| Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls` | Third-party — Texas Instruments |

</details>

<details>
<summary><strong>Shared Libraries and Platform Types</strong> — 4 modules (click to expand)</summary>

| Module (long name) | Directory | Origin |
|---|---|---|
| Diagnostics Communication Common Services | `CMS_Common` | Custom (in-house) |
| Timing Trace Library (Gliwa T1) | `GliwaT1` | Third-party — Gliwa |
| Standard Software Library (Filters, Interpolation, Math) | `NxtrLib` | Custom (in-house) |
| Standard Type Definitions (AUTOSAR Platform Types) | `StdDef` | Vector-provided |

</details>

<details>
<summary><strong>System Integration Project</strong> — 2 modules (click to expand)</summary>

| Module (long name) | Directory | Origin |
|---|---|---|
| Static Analysis Configuration | `QAC` | Custom (in-house) |
| TMS570 Microcontroller Startup and Boot | `TMS570_Startup` | Custom (in-house) |

</details>


<details>
<summary><strong>Vector MICROSAR Basic Software stack</strong> — 21 modules inside the system integration project (click to expand)</summary>

| Module (long name) | Location | Origin |
|---|---|---|
| Controller Area Network Driver and Interface | `SwProject/Source/Basic Software/Can` | Vector-provided |
| Cyclic Redundancy Check Library | `SwProject/Source/Basic Software/Crc` | Vector-provided |
| Diagnostic Event Manager | `SwProject/Source/Basic Software/Dem` | Vector-provided |
| Default Error Tracer | `SwProject/Source/Basic Software/Det` | Vector-provided |
| Digital Input-Output Driver | `SwProject/Source/Basic Software/Dio` | Vector-provided |
| Electronic Control Unit State Manager | `SwProject/Source/Basic Software/EcuM` | Vector-provided |
| General Purpose Timer Driver | `SwProject/Source/Basic Software/Gpt` | Vector-provided |
| Interaction Layer (Signal Gateway) | `SwProject/Source/Basic Software/Il` | Vector-provided |
| Input-Output Hardware Abstraction | `SwProject/Source/Basic Software/IoHwAb` | Vector-provided |
| Microcontroller Unit Driver | `SwProject/Source/Basic Software/Mcu` | Custom (in-house) |
| Memory Abstraction Interface | `SwProject/Source/Basic Software/MemIf` | Vector-provided |
| Non-Volatile Random Access Memory Manager | `SwProject/Source/Basic Software/NvM` | Vector-provided |
| Operating System (OSEK/AUTOSAR OS) | `SwProject/Source/Basic Software/Os` | Vector-provided |
| Port Pin Driver | `SwProject/Source/Basic Software/Port` | Vector-provided |
| Software Integration Package Version Check | `SwProject/Source/Basic Software/SipVersionCheck` | Vector-provided |
| Transport Protocol | `SwProject/Source/Basic Software/Tp` | Vector-provided |
| Vector Standard Library | `SwProject/Source/Basic Software/VStdLib` | Vector-provided |
| Watchdog Driver | `SwProject/Source/Basic Software/Wdg` | Third-party — TTTech |
| Watchdog Interface | `SwProject/Source/Basic Software/WdgIf` | Third-party — TTTech |
| Watchdog Manager | `SwProject/Source/Basic Software/WdgM` | Third-party — TTTech |
| Universal Measurement and Calibration Protocol Interface | `SwProject/Source/Basic Software/Xcp` | Vector-provided |

</details>

## Vector-provided versus in-house code

- **Custom (in-house)** — control logic written for this controller (Nexteer copyright). Most Application Software and Complex Device Driver modules. A `Generator: MICROSAR RTE Generator` banner in a file header only means the skeleton came from Vector tooling; the behaviour is in-house.
- **Vector-provided** — Vector MICROSAR Basic Software, Runtime Environment and DaVinci-generated configuration (look for `Copyright … by Vector Informatik GmbH`).
- **Third-party, Texas Instruments** — Flash EEPROM Emulation Driver (`Fee`) and Flash Memory Driver (`Fls`), plus device headers.
- **Third-party, TTTech** — Watchdog Driver, Watchdog Interface and Watchdog Manager.
- **Third-party, Gliwa** — Timing Trace Library (`GliwaT1`, prebuilt archive + thin glue layer).

Full policy and per-module verdicts: [`docs/src/content/docs/general/origin-policy.md`](docs/src/content/docs/general/origin-policy.md).

## Installation and build

> Windows host with the Vector DaVinci / MICROSAR toolchains and the Texas Instruments compiler is expected (see the [build guide](docs/src/content/docs/general/build-guide.md)).

1. Clone the repository.
2. Open the DaVinci project under the system integration project (`Tools/AsrProject`) and run generation for the Runtime Environment and Basic Software configuration.
3. Run each component's generation batch file (`<Module>/generate/*_Generate.bat`), then its integration wiring (`<Module>/tools/Integrate.bat`, `RteGen.bat` where present).
4. Compile with the Texas Instruments toolchain, link with `SwProject/Linker.cmd` (see `SwProject/postbuild.bat`), and flash the resulting image onto the TMS570 microcontroller.
5. Calibrate and measure through the Universal Measurement and Calibration Protocol interface; persistent data flows through the Non-Volatile Memory Manager / Flash EEPROM Emulation path.

## Documentation

- **Published site source:** [`docs/`](docs/) — Astro + Starlight project. Preview locally with `npm install` + `npm run dev` inside `docs/`; build with `npm run build` (output in `docs/dist/`). The Pages `site`/`base` URLs are derived automatically from the `origin` remote, so forks need no configuration edits.
- **Per-module pages** state purpose, origin badge, key files, runnables, dependencies and linked design documents.
- **Converted design documents** sit next to their module page. Modern Word, PDF-text and text files were converted to Markdown; legacy binary Word files are represented by structured summaries (the originals in `doc/` remain authoritative). Full status: [`docs/src/content/docs/general/document-inventory.md`](docs/src/content/docs/general/document-inventory.md).
- **Unit-test evidence** (`utp/` Tessy reports) is indexed, not converted: it is evidence, not specification.

## PSA Common Modular Platform vehicles

The PSA Common Modular Platform underpins vehicles including the Peugeot 208 and 2008, Opel Corsa and Crossland, DS 3 Crossback, Citroën C3 and related Stellantis models.

## Contributing

Contributions are welcome via pull requests. Keep Vector-provided and third-party sources unmodified (change configuration instead), keep the `doc/` design records in step with code changes, and use expanded long names in documentation.

## License

This project is licensed under the MIT License — see [LICENSE](LICENSE).
