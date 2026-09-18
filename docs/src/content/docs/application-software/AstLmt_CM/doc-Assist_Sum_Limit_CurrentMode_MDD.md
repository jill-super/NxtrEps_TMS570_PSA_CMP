---
title: "Assist Summation Limiter (Current Mode) — Model Design Document: Assist_Sum_Limit_CurrentMode_MDD"
description: "Model Design Document for Assist Summation Limiter (Current Mode) (converted)."
---

# Assist Summation Limiter (Current Mode) — Model Design Document: Assist_Sum_Limit_CurrentMode_MDD

> Source: `AstLmt_CM/doc/Assist_Sum_Limit_CurrentMode_MDD.docx` (65,406 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module –

# High-Level Description

This module combines and limits the various assist command signals from EPS modules.  It puts out several torque commands from different points in the summation and limiting process.

# Figures

## Component Diagram

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

#### Local

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

### Module specific Lookup Tables Constants

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Abs_f32_m

Sign_f32_m

Min_m

Max_m

Limit_m

DiagPStep_m

DiagNStep_m

DiagFailed_m

## Data Hiding Functions

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

### Init: AstLmt_Init

#### Design Rationale

#### Program Flow Start

N/A

#### Store Module Inputs to Local Copies

N/A

#### (Processing of function)…..

(void) Rte_Call_NxtrDiagMgr_SetNTCStatus(NTC_Num_SigPath5CrossChk, D_ZERO_CNT_U8, NTC_STATUS_PASSED)

AstLmt_LrnPnCtrFaultActv_Cnt_M_lgc = D_FALSE_CNT_LGC;

#### Store Local copy of outputs into Module Outputs

N/A

#### Program Flow End

N/A

## Periodic Functions

### Per: _Per1

#### Design Rationale

While the FDD specifies the LimitPercentFiltered output to be populated every 10 ms, the overhead required for another periodic function would be greater than including the single Max_m() macro in the main 2 ms periodic function.

#### Store Module Inputs to Local copies

DefeatLimitService_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_DefeatLimitService_Cnt_lgc()

HwTqLoaMtgtnEn_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_HwTqLoaMtgtnEn_Cnt_lgc()

LrnPnCtrEnable_Cnt_T_lgc = Rte_IRead_AstLmt_Per1_LrnPnCtrEnable_Cnt_lgc()

AssistCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistCmd_MtrNm_f32()

AssistEOTDamping_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistEOTDamping_MtrNm_f32()

AssistEOTGain_Uls_T_f32 = Rte_IRead_AstLmt_Per1_AssistEOTGain_Uls_f32()

AssistEOTLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistEOTLimit_MtrNm_f32()

AssistStallLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistStallLimit_MtrNm_f32()

AssistVehSpdLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_AssistVehSpdLimit_MtrNm_f32()

CombinedDamping_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_CombinedDamping_MtrNm_f32()

EotActvCmd_MtrNm_T_f32	= Rte_IRead_AstLmt_Per1_EotActvCmd_MtrNm_f32()

LimitedReturn_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_LimitedReturn_MtrNm_f32()

LrnPnCtrTCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_LrnPnCtrTCmd_MtrNm_f32()

OpTrqOvr_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_OpTrqOvr_MtrNm_f32()

OutputRampMult_Uls_T_f32 = Rte_IRead_AstLmt_Per1_OutputRampMult_Uls_f32()

PowerLimitPerc_Uls_T_f32 = Rte_IRead_AstLmt_Per1_PowerLimitPerc_Uls_f32()

PullCompCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_PullCompCmd_MtrNm_f32()

ThermalLimitPerc_Uls_T_f32 = Rte_IRead_AstLmt_Per1_ThermalLimitPerc_Uls_f32()

ThermalLimit_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_ThermalLimit_MtrNm_f32()

VehSpd_Kph_T_f32 = Rte_IRead_AstLmt_Per1_VehSpd_Kph_f32()

WheelImbalanceCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_WheelImbalanceCmd_MtrNm_f32()

TSMitCommand_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_TSMitCommand_MtrNm_f32()

TloaCmd_MtrNm_T_f32 = Rte_IRead_AstLmt_Per1_TloaCmd_MtrNm_f32()

#### Functional Implementation

Implemented in Matlab Simulink.

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_AstLmt_Per1_LimitPercentFiltered_Uls_f32(LimitPercentFiltered_Uls_T_f32)

Rte_IWrite_AstLmt_Per1_PreLimitTorque_MtrNm_f32(PreLimitTorque_MtrNm_T_f32)

Rte_IWrite_AstLmt_Per1_PreLimitForStall_MtrNm_f32(PreLimitForStall_MtrNm_T_f32)

Rte_IWrite_AstLmt_Per1_TrqLimitMin_MtrNm_f32(TrqLimitMin_MtrNm_T_f32)

Rte_IWrite_AstLmt_Per1_SumLimTrqCmd_MtrNm_f32(SumLimTrqCmd_MtrNm_T_f32)

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

### SCom: AstLmt_SCom_ManualTrqCmd

Implemented in Matlab Simulink.

#### Design Rationale

None

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

Rte_Read_VehSpd_Kph_f32(&VehSpd_Kph_T_f32)

#### Process Manual Torque Command

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

N/A

# Execution Requirements

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

INLINE functions defined in GlobalMacro.h are not unit tested.

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| AssistCmd_MtrNm_f32 | AssistCmd_MtrNm_f32 | LimitPercentFiltered_Uls_f32 |

| AssistEOTDamping_MtrNm_f32 | AssistEOTDamping_MtrNm_f32 | PreLimitForStall_MtrNm_f32 |

| AssistEOTGain_Uls_f32 | AssistEOTGain_Uls_f32 | PreLimitTorque_MtrNm_f32 |

| AssistEOTLimit_MtrNm_f32 | AssistEOTLimit_MtrNm_f32 | SumLimTrqCmd_MtrNm_T_f32 |

| AssistStallLimit_MtrNm_f32 | AssistStallLimit_MtrNm_f32 | TrqLimitMin_MtrNm_f32 |

| AssistVehSpdLimit_MtrNm_f32 | AssistVehSpdLimit_MtrNm_f32 |  |

| CombinedDamping_MtrNm_f32 | CombinedDamping_MtrNm_f32 |  |

| DefeatLimitService_Cnt_lgc | DefeatLimitService_Cnt_lgc |  |

| LimitedReturn_MtrNm_f32 | LimitedReturn_MtrNm_f32 |  |

| LrnPnCtrEnable_Cnt_lgc | LrnPnCtrEnable_Cnt_lgc |  |

| LrnPnCtrTCmd_MtrNm_f32 | LrnPnCtrTCmd_MtrNm_f32 |  |

| OpTrqOvr_MtrNm_f32 | OpTrqOvr_MtrNm_f32 |  |

| OutputRampMult_Uls_f32 | OutputRampMult_Uls_f32 |  |

| PowerLimitPerc_Uls_f32 | PowerLimitPerc_Uls_f32 |  |

| PrkAssistCmd_MtrNm_f32 | PrkAssistCmd_MtrNm_f32 |  |

| PullCompCmd_MtrNm_f32 | PullCompCmd_MtrNm_f32 |  |

| ThermalLimitPerc_Uls_f32 | ThermalLimitPerc_Uls_f32 |  |

| ThermalLimit_MtrNm_f32 | ThermalLimit_MtrNm_f32 |  |

| VehSpd_Kph_f32 | VehSpd_Kph_f32 |  |

| WheelImbalanceCmd_MtrNm_f32 | WheelImbalanceCmd_MtrNm_f32 |  |

| TSMitCommand_MtrNm_f32 | TSMitCommand_MtrNm_f32 |  |

| HwTqLoaMtgtnEn_Cnt_T_lgc | HwTqLoaMtgtnEn_Cnt_T_lgc |  |

| TloaCmd_MtrNm_f32 | TloaCmd_MtrNm_f32 |  |

| EotActvCmd_MtrNm_f32 | EotActvCmd_MtrNm_f32 |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| AstLmt_ManualTrqCmd_MtrNm_M_f32 | Single Precision Float | -16 | 15.9995 | ASTLMT_START_SEC_VAR_CLEARED_32 |

| AstLmt_ManualTrqCmdEn_Cnt_M_lgc | n/a | FALSE | TRUE | ASTLMT_START_SEC_VAR_CLEARED_BOOLEAN |

| AstLmt_LrnPnCtrFaultActv_Cnt_D_lgc | n/a | FALSE | TRUE | ASTLMT_START_SEC_VAR_CLEARED_BOOLEAN |

| AstLmt_LrnPnCtrFaultActv_Cnt_M_lgc | n/a | FALSE | TRUE | ASTLMT_START_SEC_VAR_CLEARED_BOOLEAN |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| k_SumLim_CmdSftyLimr_MtrNm_f32 |

| k_SumLim_LrnPnCtrDebounce_Cnt_str |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_MTRTRQZERO_MTRNM_F32 | Single precision floating point | MtrNm | 0.0 |

| D_VEHSPDTHRESH_KPH_F32 | Single precision floating point | Kph | 3.0 |

| D_LIMITPCTLO_ULS_F32 | Single precision floating point | Uls | 0.0 |

| D_LIMITPCTHI_ULS_F32 | Single precision floating point | Uls | 1.0 |

| D_CMDTHRESHOLD_ULS_F32 | Single precision floating point | Uls | 0.01 |


**Table 6 (from source document):**


| Constant Name |

| D_ZERO_ULS_F32 |

| D_ONE_ULS_F32 |

| D_MTRTRQCMDLOLMT_MTRNM_F32 |

| D_MTRTRQCMDHILMT_MTRNM_F32 |

| D_FALSE_CNT_LGC |

| D_TRUE_CNT_LGC |

| D_ZERO_CNT_U8 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Data | Value |

| Rte_InitValue_AssistCmd_MtrNm_f32 | 0.0 |

| Rte_InitValue_AssistEOTDamping_MtrNm_f32 | 0.0 |

| Rte_InitValue_AssistEOTGain_Uls_f32 | 1.0 |

| Rte_InitValue_AssistEOTLimit_MtrNm_f32 | 8.8 |

| Rte_InitValue_AssistStallLimit_MtrNm_f32 | 8.8 |

| Rte_InitValue_AssistVehSpdLimit_MtrNm_f32 | 8.8 |

| Rte_InitValue_CombinedDamping_MtrNm_f32 | 0.0 |

| Rte_InitValue_DefeatLimitService_Cnt_lgc | FALSE |

| Rte_InitValue_EotActvCmd_MtrNm_f32 | 0.0 |

| Rte_InitValue_HwTqLoaMtgtnEn_Cnt_lgc | FALSE |

| Rte_InitValue_LimitPercentFiltered_Uls_f32 | 0 |

| Rte_InitValue_LimitedReturn_MtrNm_f32 | 0 |

| Rte_InitValue_LrnPnCtrEnable_Cnt_lgc | FALSE |

| Rte_InitValue_LrnPnCtrTCmd_MtrNm_f32 | 0.0 |

| Rte_InitValue_OpTrqOvr_MtrNm_f32 | 0.0 |

| Rte_InitValue_OutputRampMult_Uls_f32 | 0.0 |

| Rte_InitValue_PowerLimitPerc_Uls_f32 | 0.0 |

| Rte_InitValue_SumLimTrqCmd_MtrNm_f32 | 0.0 |

| Rte_InitValue_PreLimitForStall_MtrNm_f32 | 0.0 |

| Rte_InitValue_PreLimitTorque_MtrNm_f32 | 0.0 |

| Rte_InitValue_PrkAssistCmd_MtrNm_f32 | 0.0 |

| Rte_InitValue_PullCompCmd_MtrNm_f32 | 0.0 |

| Rte_InitValue_ThermalLimit_MtrNm_f32 | 8.8 |

| Rte_InitValue_ThermalLimitPerc_Uls_f32 | 0.0 |

| Rte_InitValue_VehSpd_Kph_f32 | 0.0 |

| Rte_InitValue_WheelImbalanceCmd_MtrNm_f32 | 0.0 |
