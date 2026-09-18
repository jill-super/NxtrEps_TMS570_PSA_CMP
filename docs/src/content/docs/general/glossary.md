---
title: "Glossary (expanded names)"
description: "Every abbreviation and short module name expanded to its long form."
---

# Glossary (expanded names)

Short directory names are kept in code spans next to the long name everywhere in this site and in the root readme.

## General abbreviations

| Short | Long / meaning |
|---|---|
| Application Software | Top AUTOSAR layer: control and estimation functions. |
| AUTOSAR | Automotive Open System Architecture: the layered automotive software standard used here. |
| Basic Software | AUTOSAR layer with system services, hardware abstraction and microcontroller drivers. |
| Complex Device Drivers | AUTOSAR layer for hardware-near drivers outside the standardised driver set. |
| DaVinci Configurator | Vector configuration tool whose output (`Generated Configuration Data`) wires the Basic Software and Runtime Environment. |
| Electronic Control Unit | The embedded controller this firmware runs on (replaces the abbreviation ECU). |
| MICROSAR | Vector implementation of AUTOSAR Basic Software and the Runtime Environment. |
| Microcontroller Abstraction Layer | Lowest Basic Software group: direct peripheral drivers (replaces the abbreviation MCAL). |
| Runtime Environment | AUTOSAR middleware connecting software components (replaces the abbreviation RTE). |
| Advanced Driver Assistance Systems | Driver-support functions consuming arbitrated torque (replaces ADAS). |
| Loss of Assist | Degraded-steering state handled by dedicated managers (replaces LOA). |
| Non-Volatile Memory | Persisted data store: manager, proxy and Flash EEPROM Emulation (replaces NvM). |
| Universal Measurement and Calibration Protocol | Calibration and measurement interface (replaces XCP). |
| Controller Area Network | Vehicle bus (replaces CAN). |
| Unified Diagnostic Services | Diagnostics protocol on top of the Transport Protocol (replaces UDS). |
| OSEK | Operating-system standard the AUTOSAR Operating System descends from. |
| Model Design Document | Per-module design record kept next to the code (replaces MDD). |
| Software Component | AUTOSAR unit of application functionality (`Ap_` prefix) or sensor/actuator access (`Sa_` prefix). |
| End of Travel | Steering rack travel limits (replaces EOT). |
| Program Flow Monitoring | Temporal Monitor / watchdog supervision of runnable timing. |

## Module short names → long names

| Directory | Long name |
|---|---|
| `AbsHwPos_TcI2cVd` | Absolute Handwheel Position (I2C Vehicle Dynamics Interface) |
| `ActivePull` | Active Pull Compensation |
| `Adc` | Analog-to-Digital Converter Driver |
| `Assist` | Steering Power Assist Control |
| `AssistFirewall` | Steering Assist Firewall (Safety Monitor) |
| `AstLmt_CM` | Assist Summation Limiter (Current Mode) |
| `AvgFricLrn` | Average Friction Learning |
| `BVDiag` | Battery Voltage Diagnostics |
| `BatteryVoltage` | Battery Voltage Sensing |
| `BkCpPc` | Bulk Capacitor Pre-Charge Control |
| `CDDInterface` | Complex Device Driver Interface |
| `CMS_Common` | Diagnostics Communication Common Services |
| `CMS_PSA` | Communication Management Stack (PSA Integration) |
| `Can` | Controller Area Network Driver and Interface |
| `ChkPt` | Checkpoint Hooks (Watchdog Supervision Support) |
| `CmMtrCurr` | Commutated Motor Current Measurement |
| `ComplErr` | Compliance Error Handling |
| `Crc` | Cyclic Redundancy Check Library |
| `CtrlPolarityBrshlss` | Controller Polarity Detection (Brushless Motor) |
| `CtrlTemp` | Controller Temperature Monitoring |
| `CustBattDiag` | Customer Battery Diagnostics |
| `Damping` | Steering Damping Control |
| `DampingFirewall` | Damping Firewall (Safety Monitor) |
| `Dem` | Diagnostic Event Manager |
| `DemIf` | Diagnostic Event Manager Interface |
| `Det` | Default Error Tracer |
| `DfltConfigData` | Default Configuration Data |
| `DiagMgr` | Diagnostics Manager |
| `DiagSvc` | Diagnostic Services |
| `DigMSB` | Digital Motor Sensor Board Interface |
| `Dio` | Digital Input-Output Driver |
| `Dma` | Direct Memory Access Driver |
| `EOTActuatorMng` | End-of-Travel Actuator Management |
| `EcuM` | Electronic Control Unit State Manager |
| `ElePwr` | Electric Power Consumption Management |
| `EtDmpFw` | End-of-Travel Damping Firewall |
| `FaultLog` | Fault Logging |
| `Fee` | Flash EEPROM Emulation Driver |
| `Fls` | Flash Memory Driver (F021 Flash Application Programming Interface) |
| `FltInjection` | Fault Injection (Test Support) |
| `FrqDepDmpnInrtCmp` | Frequency-Dependent Damping and Inertia Compensation |
| `GliwaT1` | Timing Trace Library (Gliwa T1) |
| `Gpt` | General Purpose Timer Driver |
| `HOWDetect` | Hands-Off-Wheel Detection |
| `Header` | System Header Files |
| `HiLoadStall` | High-Load Stall Management |
| `HighFreqAssist` | High-Frequency Assist Control |
| `HwPwUp` | Hardware Power-Up Sequencing |
| `HwTqArbn_2TqADAS` | Handwheel Torque Arbitration for Advanced Driver Assistance Systems |
| `HwTqCorrln_2TqADAS` | Handwheel Torque Correlation for Advanced Driver Assistance Systems |
| `HystComp` | Hysteresis Compensation |
| `Il` | Interaction Layer (Signal Gateway) |
| `IoHwAb` | Input-Output Hardware Abstraction |
| `IoHwAbstractionUsr` | Input-Output Hardware Abstraction (User Modules) |
| `LmtCod` | Limiter Conditioning |
| `LoaMgr` | Loss-of-Assist Management |
| `LrnEOT` | End-of-Travel Learning |
| `Mcu` | Microcontroller Unit Driver |
| `MemIf` | Memory Abstraction Interface |
| `MtrCtrl_CM` | Motor Control (Current Mode) |
| `MtrTempEst` | Motor Temperature Estimation |
| `MtrVel_Digi` | Motor Velocity Sensing (Digital) |
| `Nhet1CfgAndUse_35D` | High-End Timer Configuration and Use |
| `NtWrap` | Hardware Abstraction Wrapper |
| `NvM` | Non-Volatile Random Access Memory Manager |
| `NvMMgr` | Non-Volatile Memory Manager (Flash EEPROM Interface) |
| `NvMProxy` | Non-Volatile Memory Proxy |
| `NxtrLib` | Standard Software Library (Filters, Interpolation, Math) |
| `Os` | Operating System (OSEK/AUTOSAR OS) |
| `OvrVoltMon` | Over-Voltage Monitor |
| `PSADMQ` | PSA Diagnostic Message Queue |
| `PSADSG` | PSA Diagnostic Service Gateway |
| `PSAStHdlr` | PSA State Handler |
| `PSATA` | PSA Torque Assist Handling |
| `PhaseAbcFdbkMeas` | Motor Phase Current Feedback Measurement |
| `Port` | Port Pin Driver |
| `PosServo` | Position Servo Control |
| `PsaAgArbn` | PSA Steering Angle Arbitration |
| `PwrLmtFuncCr` | Power Limit Function (Current Regulation) |
| `QAC` | Static Analysis Configuration |
| `Return` | Steering Return Control |
| `ReturnFirewall` | Steering Return Firewall (Safety Monitor) |
| `SVDiag` | Motor Driver Diagnostics (Servo Drive Diagnostics) |
| `SVDrvr_CM` | Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode) |
| `SgnlCond` | Signal Conditioning |
| `ShtdnMech` | Shutdown Mechanisms (Safe State Control) |
| `SipVersionCheck` | Software Integration Package Version Check |
| `SpiNxt` | Serial Peripheral Interface Driver |
| `SrlComDriver` | Serial Communication Driver |
| `SrlComInput` | Serial Communication Input |
| `SrlComOutput` | Serial Communication Output |
| `StOpCtrl` | State Output Control |
| `StaMd` | States and Modes (System State Manager) |
| `StabilityComp` | Stability Compensation |
| `StdDef` | Standard Type Definitions (AUTOSAR Platform Types) |
| `Sweep` | Frequency Sweep Excitation (Test Support) |
| `TMS570_Startup` | TMS570 Microcontroller Startup and Boot |
| `TMS570_uDiag` | TMS570 Microcontroller Diagnostics |
| `ThrmDutyCycle` | Thermal Duty Cycle Management |
| `TmprlMon` | Temporal Monitor (Program Flow Monitoring) |
| `Tp` | Transport Protocol |
| `TqRsDg` | Torque Reasonableness Diagnostics |
| `TranlDampg` | Translational Damping Control |
| `TrqLOA` | Torque Loss-of-Assist Handling |
| `TuningSelAuth` | Tuning Selection Authority |
| `VStdLib` | Vector Standard Library |
| `VehDyn` | Vehicle Dynamics Interface |
| `VehPwrMd` | Vehicle Power Mode Management |
| `VehSpdLmt` | Vehicle Speed Limiter |
| `Wdg` | Watchdog Driver |
| `WdgIf` | Watchdog Interface |
| `WdgM` | Watchdog Manager |
| `Xcp` | Universal Measurement and Calibration Protocol Interface |
| `ePWM_Up` | Enhanced Pulse-Width Modulation Driver |
