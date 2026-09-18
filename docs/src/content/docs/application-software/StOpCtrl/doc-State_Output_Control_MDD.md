---
title: "State Output Control — Model Design Document: State_Output_Control_MDD"
description: "Model Design Document for State Output Control (converted)."
---

# State Output Control — Model Design Document: State_Output_Control_MDD

> Source: `StOpCtrl/doc/State_Output_Control_MDD.docx` (49,349 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module – State Output Control

# High-Level Description

The State Output Control Function implements the system ramping functions based on inputs from other modules.  Ramping due to diagnostics and other functions are requested and this function does the actual implementation of the ramping.  The ramping rate can also be increased through the use of a serial comm service.

# Figures

## Diagram – Function Data Sharing

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

Note : Display variables and user defined constants are allowed to have units “UlspS” (wherever applicable as per FDD) to simplify EA4 implementation and also since there is no impact on functionality.

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

## Lookup Table Definitions

# Software Module Implementation

## Initialization Functions

## Periodic Functions

### Per: StOpCtrl_Per1

#### Design Rationale

#### Program Flow Start

#### Store Module Inputs to Local copies

See FDD

#### Function Internal

See FDD

#### Store Local copy of outputs into Module Outputs

See FDD

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

## Local Function/Macro Definitions

### TargetSelection

#### Description

Implements “Target Selection” model block in FDD.

# Execution Requirements

## Execution Sequence of the Module

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |

| DiagRampRate_XpmS_32 | SysStReqDi_Cnt_lgc |

| DiagRampValue_Uls_f32 | OutputRampMult_Uls_f32 |

| OperRampRate_XpmS_f32 |  |

| OperRampValue_Uls_f32 |  |

| RampSrlComSvcDft_Cnt_lgc |  |

| DiagStsDiagRmpActive_Cnt_lgc |  |

| LoaRateLimit_UlspS_f32 |  |

| LoaScaleFctr_Uls_ f32 |  |

| StrtStopRateLimit_UlspS_f32 |  |

| StrtStopScaleFctr_Uls_ f32 |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| Please refer to the Data dictionary | NA | NA | NA | NA |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| NA |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| NA |


**Table 5 (from source document):**


| Constant Name | Resolution | Value |

|  |  |  |

|  |  |  |

| D_BIGSLEW_ULSPS_F32 | Single precision floating point | 500 |

| D_OPER_CNT_U08 | 1 | 1 |

| D_LOA_CNT_U08 | 1 | 2 |

| D_STRTSTOP_CNT_U08 | 1 | 3 |

| D_DIAG_CNT_U08 | 1 | 4 |

| D_RATELIMITLO_ULSPS_F32 | Single precision floating point | 0.01 |

| D_RATELIMITHI_ULSPS_F32 | Single precision floating point | 500.0 |

| D_TARGETSCALELO_ULS_F32 | Single precision floating point | 0.0 |

| D_TARGETSCALEHI_ULS_F32 | Single precision floating point | 1.0 |

| D_EPSILON_ULS_F32 | Single precision floating point | FLT_EPSILON |


**Table 6 (from source document):**


| Constant Name |

| D_2MS_SEC_F32 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Function Name | TargetSelection | Type | Min | Max |

| Arguments Passed | OperScaleFctr_Uls_T_f32 | float32 | 0.0 | 1.0 |

|  | LoaScaleFctr_Uls_T_f32 | float32 | 0.0 | 1.0 |

|  | StrtStopScaleFctr_Uls_T_f32 | float32 | 0.0 | 1.0 |

|  | OperRateLimit_UlspS_T_f32 | float32 | 0.1 | 5 |

|  | LoaRateLimit_UlspS_T_f32 | float32 | 0.01 | 500 |

|  | StrtStopRateLimit_UlspS_T_f32 | float32 | 0.01 | 500 |

| Output params | SelRampValue_Uls_T_f32 | float32 | 0.0 | 1.0 |

|  | SelRampRate_UlspS_T_f32 | float32 | 0.01 | 500 |

| Return Value |  |  |  |  |
