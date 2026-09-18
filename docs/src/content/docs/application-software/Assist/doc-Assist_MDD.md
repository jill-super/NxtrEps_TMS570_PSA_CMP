---
title: "Steering Power Assist Control — Model Design Document: Assist_MDD"
description: "Model Design Document for Steering Power Assist Control (converted)."
---

# Steering Power Assist Control — Model Design Document: Assist_MDD

> Source: `Assist/doc/Assist_MDD.docx` (234,628 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- Assist

# High-Level Description

The Assist Function applies an appropriate level of motor torque based on handwheel torque and vehicle speed.

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

FPM_FloatToFixed_m

FPM_FixedToFloat_m

Sign_f32_m

Abs_f32_m

BilinearXMYM_s16_u16XMs16YM_Cnt

BilinearXMYM_u16_u16XMu16YM_Cnt

IntplVarXY_u16_u16Xu16Y_Cnt

TableSize_m

Limit_m

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

None

## Periodic Functions

### Per: Assist_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_Assist_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

HwTrq_HwNm_T_f32 = Rte_IRead_Assist_Per1_HwTrq_HwNm_f32()

VehSpd_Kph_T_u9p7 = FPM_FloatToFixed_m((Rte_Iread_Assist_Per1_VehSpd_Kph_f32()), u9p7_T)

HystAdd_HwNm_T_f32 =Rte_Iread_Assist_Per1_HysteresisAdd_HwNm_f32()

DutyCycleLevel_Cnt_T_u16p0 = FPM_FloatToFixed_m(Rte_IRead_Assist_Per1_DutyCycleLevel_Uls_f32(), u16p0_T)

AssistDDFactor_Uls_T_f32 = Rte_Iread_Assist_Per1_AssistDDFactor_Uls_f32()

IpTrqOvr_HwNm_T_f32 = Rte_Iread_Assist_Per1_IpTrqOvr_HwNm_f32()

WIRCmdAmpBlnd_MtrNm_T_u5p11  = FPM_FloatToFixed_m((Rte_Iread_Assist_Per1_WIRCmdAmpBlnd_MtrNm_f32()), u5p11_T)

DwnldAsstGain_Uls_T_f32 = Rte_Iread_Assist_Per1_ DwnldAsstGain_Uls_f32()

DftAsstTbl_Cnt_T_lgc = Rte_Iread_Assist_Per1_DftAsstTbl_Cnt_lgc ()

Temporary variables:

SignModTrq_Uls_T_s32

ModTrq_HwNm_T_u8p8

WIR0_MtrNm_T_s4p11

WIRBlend_Uls_T_u2p14

WIR1_MtrNm_T_s4p11

WIR0_MtrNm_T_s6p25

WIR1_MtrNm_T_ s6p25

AssistTrq_MtrNm_T_s6p25

AssistTrq_MtrNm_T_f32

ThermalAssistScl_Uls_T_u2p14

ThermalAssistScl_Uls_T_f32

BaseAssistCmd_MtrNm_T_f32

ModTrq_HwNm_T_f32

AbsModTrq_HwNm_T_f32

#### Base Assist Calculation

#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_Assist_Per1_BaseAssistCmd_MtrNm_f32(BaseAssistCmd_MtrNm_T_f32)

#### Program Flow End

Rte_Call_Assist_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None.

## Serial Communication Functions

None

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

Range for  HystAdd_HwNm unknown during design of revision 8 of this document.  The assumption is -16 to 16 Nm based on calibration values in the HystAdd FDD document.

INLINE functions in GlobalMacro.h are not unit tested

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |

| HwTrq_HwNm_f32 | BaseAssistCmd_MtrNm_f32 |

| HwTrqHysAdd_HwNm_f32 |  |

| VehSpd_Kph_f32 |  |

| AssistDDFactor_Uls_f32 |  |

| IpTrqOvr_HwNm_f32 |  |

| WIRCmdAmpBlnd_MtrNm_f32 |  |

| DftAsstTbl_Cnt_lgc |  |

| DwnldAsstGain_Uls_f32 |  |

| DutyCycleLevel_Uls_f32 |  |


**Table 2 (from source document):**


| Variable Name | Resolution | (min) | (max) | Software Segment |

| WIRBlend_Uls_D_u2p14 | 2-14 | 0 | 1 | ASSIST_START_SEC_VAR_CLEARED_16 |

| ThermalAssistScl_Uls_D_u2p14 | 2-14 | 0 | 1 | ASSIST_START_SEC_VAR_CLEARED_16 |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | (min) | (max) |


**Table 4 (from source document):**


| Constant Name |

| t2_AsstHwtX0_HwNm_u8p8[][] |

| t2_AsstHwtX1_HwNm_u8p8[][] |

| t2_AsstAsstY0_MtrNm_s4p11[][] |

| t2_AsstAsstY1_MtrNm_s4p11[][] |

|  |

|  |

| t2_AsstWIRBlndX_MtrNm_u5p11[][] |

| t2_AsstWIRBlendY_Uls_u2p14[][] |

| t_AsstThermSclX_Cnt_u16p0[] |

| t_AsstThermSclY_Uls_u2p14[] |


**Table 5 (from source document):**


| Constant Name | Resolution | Value |

| D_WIRBLENDFRAC_ULS_U2P14 | 2-14 | 1 |

| D_ASSTTRQLLMT_MTRNM_F32 | Single precision floating point | -0.1 |


**Table 6 (from source document):**


| Constant Name |

| BC_ASSIST_FAULTINJECTIONPOINT |

| STD_ON |

| FLTINJ_ASSIST |

| D_MTRTRQCMDHILMT_MTRNM_F32 |

| D_MTRTRQCMDLOLMT_MTRNM_F32 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Data | Value |

| HwTrq_HwNm_f32 | 0 |

| HwTrqHysAdd_HwNm_f32 | 0 |

| VehSpd_Kph_f32 | 0 |

| AssistDDFactor_Uls_f32 | 1 |

| IpTrqOvr_HwNm_f32 | 0 |

| WIRCmdAmpBlnd_MtrNm_f32 | 0 |

| DftAsstTbl_Cnt_lgc | FALSE |

| DwnldAsstGain_Uls_f32 | 0 |

| BaseAssistCmd_MtrNm_f32 | 0 |

| Rte_InitValue_DutyCycleLevel_Uls_f32 | 0 |
