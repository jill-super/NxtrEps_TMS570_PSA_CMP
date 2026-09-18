---
title: "End-of-Travel Actuator Management — Model Design Document: End_of_Travel_Actuator_Management_MDD"
description: "Model Design Document for End-of-Travel Actuator Management (converted)."
---

# End-of-Travel Actuator Management — Model Design Document: End_of_Travel_Actuator_Management_MDD

> Source: `EOTActuatorMng/doc/End_of_Travel_Actuator_Management_MDD.docx` (1,892,847 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module --

# High-Level Description

The end of travel actuator management limit reduces the level of assist from the motor as the steering system approaches the mechanical end of stop of the system.

# Figures

## Diagram – Component

## Diagram – Function Data Sharing

N/A

### Diagram – Function (_Per1)

Note: The state control block needs to be evaluated  prior to completing the End of Travel (Soft End Stops) block. More information contained within the MDD.

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

## Module Display Variables

This section identifies the name, range and resolutions for display specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

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

(This is for lookup tables (arrays) with fixed values, same name as other tables)

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Abs_f32_m

S ign_f32_m

Abs_s16_m

FPM_FixedToFloat_m

FPM_FloatToFixed_m

IntplVarXY_u16_u16Xu16Y_Cnt

LPF_SvUpdate_s16InFixKTrunc_m

LPF_OpUpdate_s16InFixKTrunc_m

Max_m

BilinearXMYM_u16_u16XMu16YM_Cnt

## Data Hiding Functions

N/A

## Global Functions/Macros Defined by this Module

N/A

## Local Functions/Macros Used by this MDD only

### EOT Determination

#### Description

### End of Travel Impact (Original)

#### Description

### End of Travel Impact (Soft Stops) – Determine Limit Position

#### Description

### End of Travel Impact (Soft Stops) – Calculate Exit Gain Value

#### Description

### End of Travel Impact (Soft Stops) – Calculate Enter Gain Value

#### Description

### End of Travel Impact (Soft Stops) – Calculate EOT Gain Value

#### Description

### End of Travel Impact (Soft Stops) – Low Pass Filter

#### Description

### End of Travel Impact (Soft Stops) – Calculate EOT Damping Value

#### Description

### End of Travel Impact (Soft Stops) – Soft Stop State Control

#### Description

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

N/A

## Periodic Functions

### Per: _Per1

#### Design Rationale

N/A

#### Program Flow Start

#### Rte_Call_EOTActuatorMng_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

#### (Processing of function)………

#### Store Local copy of outputs into Module Outputs

#### Program Flow End

Rte_Call_EOTActuatorMng_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

N/A

## Shutdown Functions

N/A

## Interrupt Functions

N/A

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Filter Analysis / Design

# Known Issues / Limitations With Design

INLINE functions defined in globalmacro.h are not unit tested.

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| HwTorque_HwNm_f32 | HwTorque_HwNm_f32 | AssistEOTLimit_MtrNm_f32 |

| CwEOT_HwDeg_f32 | CwEOT_HwDeg_f32 | AssistEOTGain_Uls_f32 |

| CcwEOT_HwDeg_f32 | CcwEOT_HwDeg_f32 | AssistEOTDamping_MtrNm_f32 |

| CwFound_Cnt_lgc | CwFound_Cnt_lgc |  |

| CcwFound_Cnt_lgc | CcwFound_Cnt_lgc |  |

| HandWheelPos_HwDeg_f32 | HandWheelPos_HwDeg_f32 |  |

| HandWheelAuth_Uls_f32 | HandWheelAuth_Uls_f32 |  |

| CRFMotorVel_MtrRadpS_f32 | CRFMotorVel_MtrRadpS_f32 |  |

| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 |  |

| PreLimitTorque_MtrNm_f32 | PreLimitTorque_MtrNm_f32 |  |

| EOTDisable_Cnt_lgc | EOTDisable_Cnt_lgc |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| EOTImpactPos_HwDeg_M_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| PrevEOTGain_Uls_M_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| FiltHWTrqSV_HwNm_M_s7p24 | p-24 | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| SESState_Uls_M_enum | Enum (see typedef table) | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_UNSPECIFIED |

| FiltEOTGainSV_HwNm_M_u1p31 | p-31 | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

|  |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| typedef enum _sesState {} sesState_T; | DISABLED | Uls | 0 | 0 |

|  | ENTERING | Uls | 1 | 1 |

|  | NORMAL | Uls | 2 | 2 |

|  | EXITING | Uls | 3 | 3 |


**Table 4 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Legal Range<br/>(max) | Software Segment | Software Segment |

| EOTDet_Cnt_D_lgc | Boolean | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_BOOLEAN | EOTACTUATORMNG_START_SEC_VAR_CLEARED_BOOLEAN |

| EOTImpact_HwDeg_D_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| LimitPosition_HwDeg_D_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| EOTEnterGain_Uls_D_f32` | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| EOTExitgain_Uls_D_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| EOTGain_Uls_D_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| FiltEOTGain_Uls_D_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |

| EOTDamping_MtrNm_D_f32 | Single Precision Floating Point | see data dictionary | see data dictionary | see data dictionary | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 | EOTACTUATORMNG_START_SEC_VAR_CLEARED_32 |


**Table 5 (from source document):**


| Constant Name |

| k_SoftStopEOTEnable_Cnt_lgc |

| k_EOTDefltPosition_HwDeg_u12p4 |

| t_SpdIptTblXTbl_HwDeg_u12p4[2] |

| t_SpdIptTblYTbl_MtrRadpS_u12p4[2] |

| k_SpdIptScale_MtrNmpRadpS_u4p12 |

| k_PosRampStep_HwDeg_u12p4 |

| k_MinRackTrvl_HwDeg_u12p4 |

| k_MaxRackTrvl_HwDeg_u12p4 |

| t2_EOTEnterGainX_HwDeg_u12p4[4][4] |

| t2_EOTEnterGainY_Uls_u1p15[4][4] |

| t_EOTEnterGainVspd_Kph_u9p7[4] |

| k_EOTStateHwTrqLPFKn_Cnt_u16 |

| k_EOTDeltaTrqThrsh_HwNm_u9p7 |

| t_TrqTableX_HwNm_u8p8[2] |

| k_EOTEnterLPFKn_Cnt_u16 |

| k_EOTExitLPFKn_Cnt_u16 |

| t2_EOTPosDepDmpTblX_HwDeg_u12p4[4][2] |

| t2_EOTPosDepDmpTblY_MtrNmpRadpS_u0p16[4][2] |

| t2_EOTExPosDepDmpTblY_MtrNmpRadps_u0p16[4][2] |

| t_EOTDmpVspd_Kph_u9p7[4] |

| k_EOTImpSpdEn_Kph_u9p7 |

|  |

|  |


**Table 6 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_HWPOSAUTHHILMT_ULS_F32 | Single Precision Floating Point | Uls | 1.0 |

| D_ONE_ULS_U16 | uint16 | Uls | 1U |

| D_MINUSONE_ULS_S16 | sint16 | Uls | -1U |

| D_MINUSONE_ULS_F32 | Single Precision Floating Point | Uls | -1.0 |

| D_2MSLPFKN5HZ_CNT_U16 | uint16 | Cnt | 3991 |

| D_SESSTATE_PRI1_ULS_U16 | uint16 | Uls | 0x01 |

| D_SESSTATE_PRI2_ULS_U16 | uint16 | Uls | 0x02 |

| D_SESSTATE_PRI3_ULS_U16 | uint16 | Uls | 0x04 |

| D_SESSTATE_PRI4_ULS_U16 | uint16 | Uls | 0x08 |

| D_EOTDAMPHILMT_MTRNM_F32 | Single Precision Floating Point | MtrNm | 8.8 |

| D_EOTDAMPLOLMT_MTRNM_F32 | Single Precision Floating Point | MtrNm | -8.8 |

| D_EOTGAINHILMT_ULS_F32 | Single Precision Floating Point | Uls | 1.0 |

| D_EOTGAINLOLMT_ULS_F32 | Single Precision Floating Point | Uls | 0.0 |

| D_EOTHILMT_MTRNM_F32 | Single Precision Floating Point | MtrNm | 8.8 |

| D_EOTLOLMT_MTRNM_F32 | Single Precision Floating Point | MtrNm | 0.0 |


**Table 7 (from source document):**


| Constant Name |

| D_MTRTRQCMDHILMT_MTRNM_F32 |

| D_ZERO_ULS_F32 |

|  |


**Table 8 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| t_TrqTblY_Uls_u2p14 | U2p14_T | 0, 1 | AUTOMATIC |
