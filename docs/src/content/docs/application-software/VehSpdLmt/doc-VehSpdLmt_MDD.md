---
title: "Vehicle Speed Limiter — Model Design Document: VehSpdLmt_MDD"
description: "Model Design Document for Vehicle Speed Limiter (converted)."
---

# Vehicle Speed Limiter — Model Design Document: VehSpdLmt_MDD

> Source: `VehSpdLmt/doc/VehSpdLmt_MDD.docx` (418,381 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module  --

# High-Level Description

The Vehicle Speed Limiting Function determines a limited assist torque command value as a function of vehicle speed and handwheel position to manage mechanical fatigue near end-of-travel positions.

# Figures

## Diagram – Function Data Sharing

No Shared Data

### Diagram – Function

None

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

IntplVarXY_u16_u16Xu16Y_Cnt()

Abs_s16_m()

FPM_FloatToFixed_m()

FPM_FixedToFloat_m()

Limit_m()

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

### Global Function #1

#### Description

## Local Functions/Macros Used by this MDD only

### Local Function #1

#### Description

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

None

## Periodic Functions

### Per: _Per1

#### Design Rationale

None

#### Program Flow Start

#### Store Module Inputs to Local copies

HwPosAuth_Uls_T_f32 = Rte_IRead_VehSpdLmt_Per1_HwPosAuth_Uls_f32()

HwPos_HwDeg_T_f32 = Rte_IRead_VehSpdLmt_Per1_HwPos_HwDeg_f32()

VehSpd_Kph_T_f32 = Rte_IRead_VehSpdLmt_Per1_VehSpd_Kph_f32()

CCWEOTPos_HwDeg_T_f32 = Rte_IRead_VehSpdLmt_Per1_CCWPosition_HwDeg_f32()

CWEOTPos_HwDeg_T_f32 = Rte_IRead_VehSpdLmt_Per1_CWPosition_HwDeg_f32()

#### Processing

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_VehSpdLmt_Per1_AstVehSpdLimit_MtrNm_f32(AstVehSpdLimit_MtrNm_f32)

#### Program Flow End

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

# Execution Requirements

## Execution Sequence of the Module

Per1 is required to be run in the forward path

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

(Item #1)

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| VehSpd_Kph_f32 | VehSpd_Kph_f32 | AstVehSpdLimit_MtrNm_f32 |

| HwPos_HwDeg_f32 | HwPos_HwDeg_f32 |  |

| HwPosAuth_Uls_f32 | HwPosAuth_Uls_f32 |  |

| CWPosition_HwDeg_f32 | CWPosition_HwDeg_f32 |  |

| CCWPosition_HwDeg_f32 | CCWPosition_HwDeg_f32 |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| ZeroVehSpd_MtrNm_D_u5p11 | 2^-11 | 0 | 8.8 |  |

| LimitTerm_MtrNm_D_u5p11 | 2^-11 | 0 | 8.8 |  |

| BkPtOne_HwDeg_D_u12p4 | 2^-4 | 0 | 900 |  |

| BkPtTwo_HwDeg_D_u12p4 | 2^-4 | 0 | 900 |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| k_PosMaxOfstOne_HwDeg_u12p4 |

| k_PosMaxOfstTwo_HwDeg_u12p4 |

| t_MaxAsstTblX_Kph_u9p7[] |

| t_MaxAsstTblY_MtrNm_u5p11[5] |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_MAXCONF_ULS_F32 | single precision float | Unitless | 1.0 |

| D_ASTVEHSPDLMTLOLMT_MTRNM_F32 | single precision float | MtrNm | 0.0 |

| D_ASTVEHSPDLMTHILMT_MTRNM_F32 | single precision float | MtrNm | 8.8 |


**Table 6 (from source document):**


| Constant Name |

| <None> |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Function Name |  | Type | Min | Max | UTP Tol. |

| Arguments Passed |  |  |  |  |  |

|  |  |  |  |  |  |

| Return Value |  |  |  |  |  |
