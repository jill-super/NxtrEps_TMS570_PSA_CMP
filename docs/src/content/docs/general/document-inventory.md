---
title: "Design document inventory"
description: "Every design document: conversion status and where to read it."
---

# Design document inventory

190 component design documents under `doc/` folders were processed: **137 converted to full Markdown** (modern Word, PDF text, text files) and **53 represented by structured summaries** (legacy binary Word `.doc`, which needs a full office converter not available in this build).

- Converted pages live next to their module (e.g. `application-software/SteeringPowerAssistControl/doc-*.md`), are hidden from the sidebar to avoid noise, and are linked from each module page's *Design documents* table.
- Legacy `.doc` summary pages name the source file, its size, the expected contents from naming conventions, and how to read the original. The `.doc` file in the repository remains authoritative.
- Unit-test evidence under `utp/` (Tessy reports, mostly PDF) and vendor datasheets under `High-Level Design Documents/` are **indexed, not converted page-by-page**: they are test evidence and third-party references, not design specification. Counts were taken from the repository tree at documentation-build time.

## All processed `doc/` files

| Page | Module (long name) | Source in repository | Status |
|---|---|---|---|
| `doc-AbsHwPos_TcI2cVd_Integration_Manual` | Absolute Handwheel Position (I2C Vehicle Dynamics Interface) | `AbsHwPos_TcI2cVd/doc/AbsHwPos_TcI2cVd_Integration_Manual.docx` | converted |
| `doc-Absolute_Handwheel_Position_TcI2cVd_MDD` | Absolute Handwheel Position (I2C Vehicle Dynamics Interface) | `AbsHwPos_TcI2cVd/doc/Absolute_Handwheel_Position_TcI2cVd_MDD.docx` | converted |
| `doc-ActivePullCmp_Integration_Manual` | Active Pull Compensation | `ActivePull/doc/ActivePullCmp_Integration Manual.doc` | summary |
| `doc-Active_Pull_Comp_MDD` | Active Pull Compensation | `ActivePull/doc/Active_Pull_Comp_MDD.docx` | converted |
| `doc-Adc2_MDD` | Analog-to-Digital Converter Driver | `Adc/doc/Adc2_MDD.docx` | converted |
| `doc-Adc_Common_MDD` | Analog-to-Digital Converter Driver | `Adc/doc/Adc_Common_MDD.docx` | converted |
| `doc-Adc_MDD` | Analog-to-Digital Converter Driver | `Adc/doc/Adc_MDD.docx` | converted |
| `doc-Integration_Manual_ADC` | Analog-to-Digital Converter Driver | `Adc/doc/Integration_Manual_ADC.docx` | converted |
| `doc-Assist_Integration_Manual` | Steering Power Assist Control | `Assist/doc/Assist_Integration_Manual.docx` | converted |
| `doc-Assist_MDD` | Steering Power Assist Control | `Assist/doc/Assist_MDD.docx` | converted |
| `doc-Assist_Firewall_MDD` | Steering Assist Firewall (Safety Monitor) | `AssistFirewall/doc/Assist_Firewall_MDD.docx` | converted |
| `doc-Assist_Sum_Limit_CurrentMode_MDD` | Assist Summation Limiter (Current Mode) | `AstLmt_CM/doc/Assist_Sum_Limit_CurrentMode_MDD.docx` | converted |
| `doc-AstLmt_CM_IntegrationManual` | Assist Summation Limiter (Current Mode) | `AstLmt_CM/doc/AstLmt_CM_IntegrationManual.docx` | converted |
| `doc-Average_Friction_Learning_MDD` | Average Friction Learning | `AvgFricLrn/doc/Average_Friction_Learning_MDD.docx` | converted |
| `doc-AvgFricLrn_Integration_Manual` | Average Friction Learning | `AvgFricLrn/doc/AvgFricLrn_Integration_Manual.docx` | converted |
| `doc-BVDiag_Integration_Manual` | Battery Voltage Diagnostics | `BVDiag/doc/BVDiag_Integration_Manual.docx` | converted |
| `doc-Battery_Voltage_Diagnostics` | Battery Voltage Diagnostics | `BVDiag/doc/Battery_Voltage_Diagnostics.doc` | summary |
| `doc-BatteryVoltage_Integration_Manual` | Battery Voltage Sensing | `BatteryVoltage/doc/BatteryVoltage_Integration_Manual.docx` | converted |
| `doc-Battery_Voltage_MDD` | Battery Voltage Sensing | `BatteryVoltage/doc/Battery_Voltage_MDD.doc` | summary |
| `doc-Bulk_Cap_Precharge_MDD` | Bulk Capacitor Pre-Charge Control | `BkCpPc/doc/Bulk_Cap_Precharge_MDD.docx` | converted |
| `doc-CmMtrCurr_Integration_Manual` | Commutated Motor Current Measurement | `CmMtrCurr/doc/CmMtrCurr_Integration_Manual.docx` | converted |
| `doc-CmMtrCurr_MDD` | Commutated Motor Current Measurement | `CmMtrCurr/doc/CmMtrCurr_MDD.docx` | converted |
| `doc-ComplErr_Integration_Manual` | Compliance Error Handling | `ComplErr/doc/ComplErr_Integration_Manual.docx` | converted |
| `doc-Compliance_Error_MDD` | Compliance Error Handling | `ComplErr/doc/Compliance_Error_MDD.docx` | converted |
| `doc-Integration_Manual_CtrlPolarityBrshlss` | Controller Polarity Detection (Brushless Motor) | `CtrlPolarityBrshlss/doc/Integration Manual CtrlPolarityBrshlss.doc` | summary |
| `doc-MDD_CtrlPolarityBrshlss` | Controller Polarity Detection (Brushless Motor) | `CtrlPolarityBrshlss/doc/MDD CtrlPolarityBrshlss.doc` | summary |
| `doc-Controller_Temperature_MDD` | Controller Temperature Monitoring | `CtrlTemp/doc/Controller_Temperature_MDD.docx` | converted |
| `doc-CtrlTemp_Integration_Manual` | Controller Temperature Monitoring | `CtrlTemp/doc/CtrlTemp_Integration_Manual.docx` | converted |
| `doc-Damping_Integration_Manual` | Steering Damping Control | `Damping/doc/Damping_Integration_Manual.docx` | converted |
| `doc-Damping_MDD` | Steering Damping Control | `Damping/doc/Damping_MDD.docx` | converted |
| `doc-DampingFirewall_IntegrationManual` | Damping Firewall (Safety Monitor) | `DampingFirewall/doc/DampingFirewall_IntegrationManual.docx` | converted |
| `doc-Damping_Firewall_MDD` | Damping Firewall (Safety Monitor) | `DampingFirewall/doc/Damping_Firewall_MDD.doc` | summary |
| `doc-Diagnostics_Manager_Core_MDD` | Diagnostics Manager | `DiagMgr/doc/Diagnostics_Manager_Core_MDD.docx` | converted |
| `doc-Diagnostics_Manager_DemIf_MDD` | Diagnostics Manager | `DiagMgr/doc/Diagnostics_Manager_DemIf_MDD.docx` | converted |
| `doc-Diagnostics_Manager_FailAction_MDD` | Diagnostics Manager | `DiagMgr/doc/Diagnostics_Manager_FailAction_MDD.docx` | converted |
| `doc-Diagnostics_Manager_GeneratedCfg_MDD` | Diagnostics Manager | `DiagMgr/doc/Diagnostics_Manager_GeneratedCfg_MDD.docx` | converted |
| `doc-Integration_Manual__DiagMgr` | Diagnostics Manager | `DiagMgr/doc/Integration Manual _DiagMgr.doc` | summary |
| `doc-DigMSB_Integration_Manual` | Digital Motor Sensor Board Interface | `DigMSB/doc/DigMSB_Integration_Manual.docx` | converted |
| `doc-DigtalMSB_MDD` | Digital Motor Sensor Board Interface | `DigMSB/doc/DigtalMSB_MDD.docx` | converted |
| `doc-Dma_Integration_Manual` | Direct Memory Access Driver | `Dma/doc/Dma Integration Manual.docx` | converted |
| `doc-Dma_MDD` | Direct Memory Access Driver | `Dma/doc/Dma_MDD.docx` | converted |
| `doc-EOTActuatorManagement_Integration_Manual` | End-of-Travel Actuator Management | `EOTActuatorMng/doc/EOTActuatorManagement_Integration_Manual.docx` | converted |
| `doc-End_of_Travel_Actuator_Management_MDD` | End-of-Travel Actuator Management | `EOTActuatorMng/doc/End_of_Travel_Actuator_Management_MDD.docx` | converted |
| `doc-ElePwr_Integration_Manual` | Electric Power Consumption Management | `ElePwr/doc/ElePwr_Integration_Manual.docx` | converted |
| `doc-Electric_Power_Consumption_MDD` | Electric Power Consumption Management | `ElePwr/doc/Electric_Power_Consumption_MDD.docx` | converted |
| `doc-EOTDampingFirewall_MDD` | End-of-Travel Damping Firewall | `EtDmpFw/doc/EOTDampingFirewall_MDD.doc` | summary |
| `doc-AutoSAR_FEE_Parameter_Configuration` | Flash EEPROM Emulation Driver | `Fee/doc/AutoSAR FEE Parameter Configuration.pdf` | summary |
| `doc-AutoSAR_FEE_User_Guide` | Flash EEPROM Emulation Driver | `Fee/doc/AutoSAR FEE User Guide.pdf` | converted |
| `doc-DataSheet_TMS570LS0714` | Flash EEPROM Emulation Driver | `Fee/doc/DataSheet_TMS570LS0714.pdf` | converted |
| `doc-DataSheet_TMS570LS1227` | Flash EEPROM Emulation Driver | `Fee/doc/DataSheet_TMS570LS1227.pdf` | converted |
| `doc-F021_Flash_API_License_Agreement` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/F021_Flash_API_License_Agreement.pdf` | converted |
| `doc-Release_Notes` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/Release_Notes.pdf` | converted |
| `doc-SPNA148` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/SPNA148.pdf` | converted |
| `doc-SPNU501F` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/SPNU501F.pdf` | converted |
| `doc-SPNZ210` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/SPNZ210.pdf` | converted |
| `doc-build_information` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/build_information.txt` | converted |
| `doc-readme` | Flash Memory Driver (F021 Flash Application Programming Interface) | `Fls/doc/readme.txt` | converted |
| `doc-Fault_Injection_MDD` | Fault Injection (Test Support) | `FltInjection/doc/Fault_Injection_MDD.docx` | converted |
| `doc-Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD` | Frequency-Dependent Damping and Inertia Compensation | `FrqDepDmpnInrtCmp/doc/Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD.docx` | converted |
| `doc-GliwaT1_IntegrationManual` | Timing Trace Library (Gliwa T1) | `GliwaT1/doc/GliwaT1_IntegrationManual.doc` | summary |
| `doc-HOWDetect_Integration_Manual` | Hands-Off-Wheel Detection | `HOWDetect/doc/HOWDetect_Integration_Manual.docx` | converted |
| `doc-HOWDetect_MDD` | Hands-Off-Wheel Detection | `HOWDetect/doc/HOWDetect_MDD.docx` | converted |
| `doc-HiLoadStall_MDD` | High-Load Stall Management | `HiLoadStall/doc/HiLoadStall_MDD.docx` | converted |
| `doc-HighFreqAssist_Integration_Manual` | High-Frequency Assist Control | `HighFreqAssist/doc/HighFreqAssist_Integration_Manual.docx` | converted |
| `doc-High_Frequency_Assist_MDD` | High-Frequency Assist Control | `HighFreqAssist/doc/High_Frequency_Assist_MDD.docx` | converted |
| `doc-Hardware_Power_Up_MDD` | Hardware Power-Up Sequencing | `HwPwUp/doc/Hardware_Power_Up_MDD.docx` | converted |
| `doc-HwPwUp_Integration_Manual` | Hardware Power-Up Sequencing | `HwPwUp/doc/HwPwUp_Integration_Manual.docx` | converted |
| `doc-HwTqArbn_Integration_Manual` | Handwheel Torque Arbitration for Advanced Driver Assistance Systems | `HwTqArbn_2TqADAS/doc/HwTqArbn_Integration_Manual.doc` | summary |
| `doc-HwTqArbn_MDD` | Handwheel Torque Arbitration for Advanced Driver Assistance Systems | `HwTqArbn_2TqADAS/doc/HwTqArbn_MDD.doc` | summary |
| `doc-HwTqCorrln_Integration_Manual` | Handwheel Torque Correlation for Advanced Driver Assistance Systems | `HwTqCorrln_2TqADAS/doc/HwTqCorrln_Integration_Manual.doc` | summary |
| `doc-HwTqCorrln_MDD` | Handwheel Torque Correlation for Advanced Driver Assistance Systems | `HwTqCorrln_2TqADAS/doc/HwTqCorrln_MDD.doc` | summary |
| `doc-HystComp_Integration_Manual` | Hysteresis Compensation | `HystComp/doc/HystComp_Integration_Manual.docx` | converted |
| `doc-Hysteresis_Compensation_MDD` | Hysteresis Compensation | `HystComp/doc/Hysteresis_Compensation_MDD.doc` | summary |
| `doc-LimCod_Integration_Manual` | Limiter Conditioning | `LmtCod/doc/LimCod_Integration_Manual.doc` | summary |
| `doc-Limiter_Conditioning_MDD` | Limiter Conditioning | `LmtCod/doc/Limiter_Conditioning_MDD.doc` | summary |
| `doc-LOAMgr_IntegrationManual` | Loss-of-Assist Management | `LoaMgr/doc/LOAMgr_IntegrationManual.docx` | converted |
| `doc-LoaMgr_MDD` | Loss-of-Assist Management | `LoaMgr/doc/LoaMgr_MDD.doc` | summary |
| `doc-LearnEOT` | End-of-Travel Learning | `LrnEOT/doc/LearnEOT.docx` | converted |
| `doc-LrnEOT_Integration_Manual` | End-of-Travel Learning | `LrnEOT/doc/LrnEOT_Integration_Manual.docx` | converted |
| `doc-CurrCmd_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/CurrCmd_MDD.doc` | summary |
| `doc-CurrParamComp_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/CurrParamComp_MDD.docx` | converted |
| `doc-MtrCntrl_Integration_Manual` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/MtrCntrl_Integration_Manual.docx` | converted |
| `doc-PICurrentContrl_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/PICurrentContrl_MDD.doc` | summary |
| `doc-PeakCurrEst_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/PeakCurrEst_MDD.docx` | converted |
| `doc-Quadrant_Detection_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/Quadrant_Detection_MDD.docx` | converted |
| `doc-TorqueCmdScaling_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/TorqueCmdScaling_MDD.doc` | summary |
| `doc-TrqCanc_MDD` | Motor Control (Current Mode) | `MtrCtrl_CM/doc/TrqCanc_MDD.docx` | converted |
| `doc-Motor_Temperature_Estimation_Integration_Manual` | Motor Temperature Estimation | `MtrTempEst/doc/Motor_Temperature_Estimation_Integration_Manual.docx` | converted |
| `doc-Motor_Temperature_Estimation_MDD` | Motor Temperature Estimation | `MtrTempEst/doc/Motor_Temperature_Estimation_MDD.docx` | converted |
| `doc-Motor_Velocity_Integration_Manual` | Motor Velocity Sensing (Digital) | `MtrVel_Digi/doc/Motor Velocity_Integration_Manual.docx` | converted |
| `doc-MotorVelocity2_MDD` | Motor Velocity Sensing (Digital) | `MtrVel_Digi/doc/MotorVelocity2_MDD.doc` | summary |
| `doc-MotorVelocity3_MDD` | Motor Velocity Sensing (Digital) | `MtrVel_Digi/doc/MotorVelocity3_MDD.doc` | summary |
| `doc-MotorVelocity_MDD` | Motor Velocity Sensing (Digital) | `MtrVel_Digi/doc/MotorVelocity_MDD.doc` | summary |
| `doc-NHetRegisters` | High-End Timer Configuration and Use | `Nhet1CfgAndUse_35D/doc/NHetRegisters.pdf` | converted |
| `doc-Nhet1CfgAndUse_Integration_Manual` | High-End Timer Configuration and Use | `Nhet1CfgAndUse_35D/doc/Nhet1CfgAndUse_Integration_Manual.doc` | summary |
| `doc-Nhet1CfgAndUse_MDD` | High-End Timer Configuration and Use | `Nhet1CfgAndUse_35D/doc/Nhet1CfgAndUse_MDD.doc` | summary |
| `doc-Fee_Interface_MDD` | Non-Volatile Memory Manager (Flash EEPROM Interface) | `NvMMgr/doc/Fee_Interface_MDD.docx` | converted |
| `doc-NvMMgr_Integration_Manual` | Non-Volatile Memory Manager (Flash EEPROM Interface) | `NvMMgr/doc/NvMMgr_Integration_Manual.docx` | converted |
| `doc-NvMProxy_Integration_Manual` | Non-Volatile Memory Proxy | `NvMProxy/doc/NvMProxy_Integration_Manual.docx` | converted |
| `doc-NvMProxy_MDD` | Non-Volatile Memory Proxy | `NvMProxy/doc/NvMProxy_MDD.docx` | converted |
| `doc-Filter_Library_Design_Document` | Standard Software Library (Filters, Interpolation, Math) | `NxtrLib/doc/Filter_Library_Design_Document.doc` | summary |
| `doc-Interpolation_Design_MDD` | Standard Software Library (Filters, Interpolation, Math) | `NxtrLib/doc/Interpolation_Design_MDD.doc` | summary |
| `doc-NxtrLib_Systemtime_Integration_Manual` | Standard Software Library (Filters, Interpolation, Math) | `NxtrLib/doc/NxtrLib_Systemtime Integration_Manual.docx` | converted |
| `doc-Optimized_SinCos_Algorithm` | Standard Software Library (Filters, Interpolation, Math) | `NxtrLib/doc/Optimized SinCos Algorithm.docx` | converted |
| `doc-OverVoltageMonitor_MDD` | Over-Voltage Monitor | `OvrVoltMon/doc/OverVoltageMonitor_MDD.docx` | converted |
| `doc-OvrVoltMon_Integration_Manual` | Over-Voltage Monitor | `OvrVoltMon/doc/OvrVoltMon_Integration_Manual.docx` | converted |
| `doc-PSADMQ_IntegrationManual` | PSA Diagnostic Message Queue | `PSADMQ/doc/PSADMQ_IntegrationManual.doc` | summary |
| `doc-PSADMQ_MDD` | PSA Diagnostic Message Queue | `PSADMQ/doc/PSADMQ_MDD.doc` | summary |
| `doc-PSADSG_IntegrationManual` | PSA Diagnostic Service Gateway | `PSADSG/doc/PSADSG_IntegrationManual.doc` | summary |
| `doc-PSADSG_MDD` | PSA Diagnostic Service Gateway | `PSADSG/doc/PSADSG_MDD.docx` | converted |
| `doc-PSASH_Integration_Manual` | PSA State Handler | `PSAStHdlr/doc/PSASH_Integration Manual.docx` | converted |
| `doc-PSASH_MDD` | PSA State Handler | `PSAStHdlr/doc/PSASH_MDD.docx` | converted |
| `doc-PSATA_Integration_Manual` | PSA Torque Assist Handling | `PSATA/doc/PSATA_Integration Manual.docx` | converted |
| `doc-PSATA_MDD` | PSA Torque Assist Handling | `PSATA/doc/PSATA_MDD.docx` | converted |
| `doc-CDDInterface10_MDD` | Complex Device Driver Interface | `PSA_CMP_EPS_TMS570/SwProject/CDDInterface/doc/CDDInterface10_MDD.doc` | summary |
| `doc-CDDInterface11_MDD` | Complex Device Driver Interface | `PSA_CMP_EPS_TMS570/SwProject/CDDInterface/doc/CDDInterface11_MDD.doc` | summary |
| `doc-CDDInterface6_MDD` | Complex Device Driver Interface | `PSA_CMP_EPS_TMS570/SwProject/CDDInterface/doc/CDDInterface6_MDD.doc` | summary |
| `doc-CDDInterface9_MDD` | Complex Device Driver Interface | `PSA_CMP_EPS_TMS570/SwProject/CDDInterface/doc/CDDInterface9_MDD.doc` | summary |
| `doc-CustomerBattDiagnostic_MDD` | Customer Battery Diagnostics | `PSA_CMP_EPS_TMS570/SwProject/CustBattDiag/doc/CustomerBattDiagnostic_MDD.docx` | converted |
| `doc-DemIf_MDD` | Diagnostic Event Manager Interface | `PSA_CMP_EPS_TMS570/SwProject/DemIf/doc/DemIf_MDD.docx` | converted |
| `doc-FaultLog_MDD` | Fault Logging | `PSA_CMP_EPS_TMS570/SwProject/FaultLog/doc/FaultLog_MDD.doc` | summary |
| `doc-IoHwAb10_MDD` | Input-Output Hardware Abstraction (User Modules) | `PSA_CMP_EPS_TMS570/SwProject/IoHwAbstractionUsr/doc/IoHwAb10_MDD.doc` | summary |
| `doc-IoHwAb9_MDD` | Input-Output Hardware Abstraction (User Modules) | `PSA_CMP_EPS_TMS570/SwProject/IoHwAbstractionUsr/doc/IoHwAb9_MDD.doc` | summary |
| `doc-SrlComDriver_MDD` | Serial Communication Driver | `PSA_CMP_EPS_TMS570/SwProject/SrlComDriver/doc/SrlComDriver_MDD.doc` | summary |
| `doc-SrlComInput_MDD` | Serial Communication Input | `PSA_CMP_EPS_TMS570/SwProject/SrlComInput/doc/SrlComInput_MDD.doc` | summary |
| `doc-SrlComOutput_MDD` | Serial Communication Output | `PSA_CMP_EPS_TMS570/SwProject/SrlComOutput/doc/SrlComOutput_MDD.doc` | summary |
| `doc-VehPwrMd_MDD` | Vehicle Power Mode Management | `PSA_CMP_EPS_TMS570/SwProject/VehPwrMd/doc/VehPwrMd_MDD.doc` | summary |
| `doc-ES36B_PhaseAbcFdbkMeas__Integration_Manual` | Motor Phase Current Feedback Measurement | `PhaseAbcFdbkMeas/doc/ES36B_PhaseAbcFdbkMeas _Integration_Manual.doc` | summary |
| `doc-ES36B_PhaseFdbkMeas__MDD` | Motor Phase Current Feedback Measurement | `PhaseAbcFdbkMeas/doc/ES36B_PhaseFdbkMeas _MDD.doc` | summary |
| `doc-PosServo_IntegrationManual` | Position Servo Control | `PosServo/doc/PosServo_IntegrationManual.doc` | summary |
| `doc-PosServo_MDD` | Position Servo Control | `PosServo/doc/PosServo_MDD.docx` | converted |
| `doc-PsaAgArbn_IntegrationManual` | PSA Steering Angle Arbitration | `PsaAgArbn/doc/PsaAgArbn_IntegrationManual.doc` | summary |
| `doc-PsaAgArbn_MDD` | PSA Steering Angle Arbitration | `PsaAgArbn/doc/PsaAgArbn_MDD.docx` | converted |
| `doc-Power_Limit_Function_CM_Integration_Manual` | Power Limit Function (Current Regulation) | `PwrLmtFuncCr/doc/Power_Limit_Function_CM_Integration_Manual.docx` | converted |
| `doc-Power_Limit_Function_CM_MDD` | Power Limit Function (Current Regulation) | `PwrLmtFuncCr/doc/Power_Limit_Function_CM_MDD.docx` | converted |
| `doc-MISRA_Compliance_Guidelines` | Static Analysis Configuration | `QAC/doc/MISRA Compliance Guidelines.docx` | converted |
| `doc-Return_MDD` | Steering Return Control | `Return/doc/Return_MDD.docx` | converted |
| `doc-Return_Firewall_MDD` | Steering Return Firewall (Safety Monitor) | `ReturnFirewall/doc/Return_Firewall_MDD.docx` | converted |
| `doc-DigPhsReasDiag_MDD` | Motor Driver Diagnostics (Servo Drive Diagnostics) | `SVDiag/doc/DigPhsReasDiag_MDD.docx` | converted |
| `doc-Motor_Driver_Diagnostics_MDD` | Motor Driver Diagnostics (Servo Drive Diagnostics) | `SVDiag/doc/Motor_Driver_Diagnostics_MDD.docx` | converted |
| `doc-SVDiag_Integration_Manual` | Motor Driver Diagnostics (Servo Drive Diagnostics) | `SVDiag/doc/SVDiag_Integration_Manual.docx` | converted |
| `doc-PWMCdd_Integration_Manual` | Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode) | `SVDrvr_CM/doc/PWMCdd_Integration_Manual.docx` | converted |
| `doc-PWM_CDD_MDD` | Space Vector Motor Drive (Pulse-Width Modulation Complex Device Driver, Current Mode) | `SVDrvr_CM/doc/PWM_CDD_MDD.docx` | converted |
| `doc-SignalConditioning_MDD` | Signal Conditioning | `SgnlCond/doc/SignalConditioning_MDD.docx` | converted |
| `doc-SignlCondn_Integration_Manual` | Signal Conditioning | `SgnlCond/doc/SignlCondn_Integration_Manual.docx` | converted |
| `doc-Shutdown_Mechanisms_MDD` | Shutdown Mechanisms (Safe State Control) | `ShtdnMech/doc/Shutdown_Mechanisms_MDD.docx` | converted |
| `doc-Spi_Nexteer_Integration_Manual` | Serial Peripheral Interface Driver | `SpiNxt/doc/Spi_Nexteer_Integration_Manual.docx` | converted |
| `doc-Spi_Nexteer_MDD` | Serial Peripheral Interface Driver | `SpiNxt/doc/Spi_Nexteer_MDD.docx` | converted |
| `doc-StateOutput_Control_IntegrationManual` | State Output Control | `StOpCtrl/doc/StateOutput Control_IntegrationManual.docx` | converted |
| `doc-State_Output_Control_MDD` | State Output Control | `StOpCtrl/doc/State_Output_Control_MDD.docx` | converted |
| `doc-StaMd_Integration_Manual` | States and Modes (System State Manager) | `StaMd/doc/StaMd_Integration_Manual.docx` | converted |
| `doc-States_And_Modes_GeneratedConfiguration_MDD` | States and Modes (System State Manager) | `StaMd/doc/States_And_Modes_GeneratedConfiguration_MDD.docx` | converted |
| `doc-States_And_Modes_MDD` | States and Modes (System State Manager) | `StaMd/doc/States_And_Modes_MDD.docx` | converted |
| `doc-StabilityCompensation2_MDD` | Stability Compensation | `StabilityComp/doc/StabilityCompensation2_MDD.docx` | converted |
| `doc-StabilityCompensation_MDD` | Stability Compensation | `StabilityComp/doc/StabilityCompensation_MDD.docx` | converted |
| `doc-Sweep1_MDD` | Frequency Sweep Excitation (Test Support) | `Sweep/doc/Sweep1_MDD.docx` | converted |
| `doc-Sweep2_MDD` | Frequency Sweep Excitation (Test Support) | `Sweep/doc/Sweep2_MDD.docx` | converted |
| `doc-TMS570_Startup_BootStartup_MDD` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/TMS570_Startup_BootStartup_MDD.docx` | converted |
| `doc-TMS570_Startup_FiqIntVect_MDD` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/TMS570_Startup_FiqIntVect_MDD.docx` | converted |
| `doc-TMS570_Startup_Integration_Manual` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/TMS570_Startup_Integration_Manual.docx` | converted |
| `doc-TMS570_Startup_SysCore_MDD` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/TMS570_Startup_SysCore_MDD.docx` | converted |
| `doc-TMS570_Startup_SysStartup_MDD` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/TMS570_Startup_SysStartup_MDD.docx` | converted |
| `doc-TMS570_Startup_errata_SSWF021_45_MDD` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/TMS570_Startup_errata_SSWF021_45_MDD.docx` | converted |
| `doc-spna106a` | TMS570 Microcontroller Startup and Boot | `TMS570_Startup/doc/spna106a.pdf` | converted |
| `doc-Cd_uDiagFPU_MDD` | TMS570 Microcontroller Diagnostics | `TMS570_uDiag/doc/Cd_uDiagFPU_MDD.docx` | converted |
| `doc-Cd_uDiagUtility_MDD` | TMS570 Microcontroller Diagnostics | `TMS570_uDiag/doc/Cd_uDiagUtility_MDD.docx` | converted |
| `doc-Cd_uDiag_Integration_Manual` | TMS570 Microcontroller Diagnostics | `TMS570_uDiag/doc/Cd_uDiag_Integration_Manual.docx` | converted |
| `doc-FlsTst_Integration_Manual` | TMS570 Microcontroller Diagnostics | `TMS570_uDiag/doc/FlsTst_Integration_Manual.docx` | converted |
| `doc-FlsTst_MDD` | TMS570 Microcontroller Diagnostics | `TMS570_uDiag/doc/FlsTst_MDD.docx` | converted |
| `doc-OsErrCallouts_MDD` | TMS570 Microcontroller Diagnostics | `TMS570_uDiag/doc/OsErrCallouts_MDD.docx` | converted |
| `doc-ThermalDutyCycle_Integration_Manual` | Thermal Duty Cycle Management | `ThrmDutyCycle/doc/ThermalDutyCycle_Integration_Manual.docx` | converted |
| `doc-Thermal_Duty_Cycle_MDD` | Thermal Duty Cycle Management | `ThrmDutyCycle/doc/Thermal_Duty_Cycle_MDD.docx` | converted |
| `doc-Temporal_Monitor_Integration_Manual` | Temporal Monitor (Program Flow Monitoring) | `TmprlMon/doc/Temporal Monitor_Integration_Manual.docx` | converted |
| `doc-Temporal_Monitor_2_MDD` | Temporal Monitor (Program Flow Monitoring) | `TmprlMon/doc/Temporal_Monitor_2_MDD.docx` | converted |
| `doc-Temporal_Monitor_MDD` | Temporal Monitor (Program Flow Monitoring) | `TmprlMon/doc/Temporal_Monitor_MDD.docx` | converted |
| `doc-TorqueReasonableDiagnostics_MDD` | Torque Reasonableness Diagnostics | `TqRsDg/doc/TorqueReasonableDiagnostics_MDD.docx` | converted |
| `doc-TrqReasonableness_Integration_Manual` | Torque Reasonableness Diagnostics | `TqRsDg/doc/TrqReasonableness_Integration_Manual.docx` | converted |
| `doc-TranlDampg_Integration_Manual` | Translational Damping Control | `TranlDampg/doc/TranlDampg_Integration_Manual.doc` | summary |
| `doc-TranlDampg_MDD` | Translational Damping Control | `TranlDampg/doc/TranlDampg_MDD.doc` | summary |
| `doc-TrqLOA_IntegrationManual` | Torque Loss-of-Assist Handling | `TrqLOA/doc/TrqLOA_IntegrationManual.docx` | converted |
| `doc-TrqLOA_MDD` | Torque Loss-of-Assist Handling | `TrqLOA/doc/TrqLOA_MDD.doc` | summary |
| `doc-TuningSelAuth_Integration_Manual` | Tuning Selection Authority | `TuningSelAuth/doc/TuningSelAuth_Integration Manual.doc` | summary |
| `doc-Tuning_Select_Authority_MDD` | Tuning Selection Authority | `TuningSelAuth/doc/Tuning_Select_Authority_MDD.docx` | converted |
| `doc-VehDyn_Integration_Manual` | Vehicle Dynamics Interface | `VehDyn/doc/VehDyn_Integration_Manual.docx` | converted |
| `doc-VehDyn_MDD` | Vehicle Dynamics Interface | `VehDyn/doc/VehDyn_MDD.docx` | converted |
| `doc-VehSpdLmt_MDD` | Vehicle Speed Limiter | `VehSpdLmt/doc/VehSpdLmt_MDD.docx` | converted |
| `doc-ApXcp_Integration_Manual` | Universal Measurement and Calibration Protocol Interface | `Xcp/doc/ApXcp_Integration_Manual.docx` | converted |
| `doc-Ap_ePWM2_MDD` | Enhanced Pulse-Width Modulation Driver | `ePWM_Up/doc/Ap_ePWM2 MDD.doc` | summary |
| `doc-ePWM_MDD` | Enhanced Pulse-Width Modulation Driver | `ePWM_Up/doc/ePWM MDD.doc` | summary |
| `doc-ePWM_Integration_Manual` | Enhanced Pulse-Width Modulation Driver | `ePWM_Up/doc/ePWM_Integration_Manual.doc` | summary |
