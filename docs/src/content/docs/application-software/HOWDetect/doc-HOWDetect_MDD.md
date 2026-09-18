---
title: "Hands-Off-Wheel Detection — Model Design Document: HOWDetect_MDD"
description: "Model Design Document for Hands-Off-Wheel Detection (converted)."
---

# Hands-Off-Wheel Detection — Model Design Document: HOWDetect_MDD

> Source: `HOWDetect/doc/HOWDetect_MDD.docx` (343,944 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module  -- Hands on Wheel Detect

# High-Level Description

This module is responsible for determining the driver’s hands on the steering wheel. It determines a continuous valued estimate that represents the likelihood that a drivers hands are on the steering wheel (value =1) or off the steering wheel (value=0).  A discrete value corresponding to the confidence of the estimate is also specified.

# Figures

## Diagram – Function Data Sharing

No Shared Data

### Component Diagram

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

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

(This is for lookup tables (arrays) with fixed values, same name as other tables)

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

LPF_Init_f32_m

HPF_Init_f32_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

IntplVarXY_u16_u16Xu16Y_Cnt

IntplVarXY_s16_u16Xs16Y_Cnt

BilinearXMYM_s16_u16XMs16YM_Cnt

TableSize_m

LPF_OpUpdate_f32_m

HPF_OpUpdate_f32_m

Abs_f32_m

Limit_m

## Data Hiding Functions

None

## Global Functions/Macros Defined by this Module

### Global Function #1

#### Description

None

## Local Functions/Macros Used by this MDD only

### Local Function #1

#### Description

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

### Init:  HOWDetect_Init1

#### Design Rationale

None

#### Module Outputs

None

#### Module Internal

None

## Periodic Functions

### Per:  HOWDetect_Per1()

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HOWDetect_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

HwTrq_HwNm_T_f32 = Rte_IRead_HOWDetect_Per1_HwTrq_HwNm_f32()

VehSpd_Kph_T_f32 = Rte_IRead_HOWDetect_Per1_VehSpd_Kph_f32()

#### (Processing of function)

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_HOWDetect_Per1_HOWEstimate_Uls_f32(HOWEstimate_Uls_T_f32)

Rte_IWrite_HOWDetect_Per1_HOWState_Cnt_s08(HOWState_Cnt_T_s08)

#### Program Flow End

Rte_Call_HOWDetect_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

None

### FaultRec:

None

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### Processing of function

None

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

## Shutdown Functions

None

### Shtdn:

None

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### Processing of function

None

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

## Interrupt Functions

None

### Isr:

None

#### Design Rationale

None

#### (Processing of the ISR function)

None

## Serial Communication Functions

None

### SComm:

None

#### Design Rationale

None

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### (Processing of function)

None

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

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

# Known Issues / Limitations With Design

None

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| HwTrq_HwNm_f32 | HwTrq_HwNm_f32 | HOWEstimate_Uls_f32 |

| VehSpd_Kph_f32 | VehSpd_Kph_f32 | HOWState_Cnt_s08 |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| HOWDetect_HOWEstAftRateLimiter_Uls_M_f32 | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_32 |

| HOWDetect_HOWEstAftLimiter_Uls_M_f32 | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_32 |

| HOWDetect_AbsHighFreqTrq_HwNm_D_f32 | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_32 |

| HOWDetect_AbsLowFreqTrq_HwNm_D_f32 | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_32 |

| HOWDetect_LPF1_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |

| HOWDetect_LPF2_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |

| HOWDetect_LPF3_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |

| HOWDetect_HPF_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |

| HOWDetect_LPFFinal_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |

| HOWDetect_LPFEstimate_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |

| HOWDetect_LPFState_Cnt_M_str | Single Precision Float | See Data Dictionary | See Data Dictionary | HOWDETECT_START_SEC_VAR_CLEARED_UNSPECIFIED |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |

|  |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| t_HOWVehSpd_Kph_u9p7 |

| t_HOWHighFreqGainY_Uls_u9p7 |

| t2_HOWHFRateX_HwNm_u8p8 |

| t2_HOWHFRateY_UlspS_s7p8 |

| t2_HOWLFRateX_HwNm_u8p8 |

| t2_HOWLFRateY_UlspS_s7p8 |

| t_HOWStateThresholds_Uls_u8p8 |

| k_HOWTrqInitLPFKn_Hz_f32 |

| k_HOWTrqHPFKn_Hz_f32 |

| k_HOWTrqFinalLPFKn_Hz_f32 |

| k_HOWSlewRate_HwNmpS_f32 |

| k_HOWDecaySF_Uls_f32 |

| k_HOWEstLPFKn_Hz_f32 |

| k_HOWMinVehSpd_Kph_f32 |

| k_HOWStateLPFKn_Hz_f32 |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_HOWESTIMATEMAXLIMIT_ULS_F32 | Single Precision Float | Uls | 0.5 |

| D_ABSHFTRQLIMIT_NM_F32 | Single Precision Float | Nm | 255.0 |


**Table 6 (from source document):**


| Constant Name |

| D_2MS_SEC_F32 |

| D_ONE_ULS_F32 |

| D_ZERO_ULS_F32 |

| D_ZERO_CNT_S8 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| T_HOWStateValues_Cnt_s15p0 | 1 | { -3, -2, -1, 0, 1, 2, 3 } | HOWDETECT_START_SEC_CONST_16 |


**Table 8 (from source document):**


| Function Name | None | Type | Dir. | Min | Max | UTP Tol. |

| Arguments Passed | None |  |  |  |  |  |

|  |  |  |  |  |  |  |

| Return Value | None |  |  |  |  |  |
