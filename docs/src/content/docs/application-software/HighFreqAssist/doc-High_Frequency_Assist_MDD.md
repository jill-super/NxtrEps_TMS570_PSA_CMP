---
title: "High-Frequency Assist Control — Model Design Document: High_Frequency_Assist_MDD"
description: "Model Design Document for High-Frequency Assist Control (converted)."
---

# High-Frequency Assist Control — Model Design Document: High_Frequency_Assist_MDD

> Source: `HighFreqAssist/doc/High_Frequency_Assist_MDD.docx` (976,943 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module –

# High-Level Description

This module compensates for system inertia and road feedback.  It puts handwheel torque through a high-pass filter and multiplies it by a tunable gain parameter to compensate for these factors.

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

Abs_s16_m

IntplVarXY_u16_u16Xu16Y_Cnt

BilinearXMYM_u16_u16XMu16YM_Cnt

TableSize_m

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

### Per: _Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_HighFreqAssist_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

HwTorque_HwNm_T_f32 = Rte_IRead_HighFreqAssist_Per1_HwTorque_HwNm_f32()

VehicleSpeed_Kph_T_f32 = Rte_IRead_HighFreqAssist_Per1_VehicleSpeed_Kph_f32()

WIRCmdAmpBlnd_MtrNm_T_f32 = Rte_IRead_HighFreqAssist_Per1_WIRCmdAmpBlnd_MtrNm_f32()

HwTorque_HwNm_T_s4p11 = FPM_FloatToFixed_m(HwTorque_HwNm_T_f32, s4p11_T)

AbsHwTorque_HwNm_T_u5p11 = Abs_s16_m(HwTorque_HwNm_T_s4p11)

VehicleSpeed_Kph_T_u9p7 = FPM_FloatToFixed_m(VehicleSpeed_Kph_T_f32, u9p7_T)

WIRCmdAmpBlnd_MtrNm_T_u4p12 = FPM_FloatToFixed_m(WIRCmdAmpBlnd_MtrNm_T_f32, u4p12_T)

#### Determine Filter Frequency

#### Determine Gain

#### Filter and Output

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_HighFreqAssist_Per1_HighFreqAssist_MtrNm_f32(HighFreqAssist_MtrNm_T_f32);

#### Program Flow End

Rte_Call_HighFreqAssist_Per1_CP1_CheckpointReached()

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

The periodic function is called at a rate of 2ms in all states.

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

INLINE functions in GlobalMacro.h are not unit tested

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 | HighFreqAssist_MtrNm_f32 |

| HwTorque_HwNm_f32 | HwTorque_HwNm_f32 |  |

| WIRCmdAmpBlnd_MtrNm_f32 | WIRCmdAmpBlnd_MtrNm_f32 |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

|  |

|  |

|  |

|  |

|  |

|  |

|  |

| t2_TorqX0_HwNm_u5p11[1][] |

| t2_TorqX1_HwNm_u5p11[1][] |

| t2_GainY0_MtrNmpHwNm_u3p13[1][] |

| t2_GainY1_MtrNmpHwNm_u3p13[1][] |

| t2_WIRBlendX_MtrNm_u4p12[1][5] |

| t2_WIRBlendY_Uls_u1p15[1][5] |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| <None> |  |  |  |

|  |  |  |  |


**Table 6 (from source document):**


| Constant Name |

|  |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Data | Value |

| Rte_InitValue_HighFreqAssist_MtrNm_f32 | 0 |

| Rte_InitValue_HwTorque_HwNm_f32 | 0 |

| Rte_InitValue_VehicleSpeed_Kph_f32 | 0 |

| Rte_InitValue_WIRCmdAmpBlnd_MtrNm_f32 | 0 |
