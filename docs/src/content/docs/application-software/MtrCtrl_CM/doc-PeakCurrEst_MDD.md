---
title: "Motor Control (Current Mode) — Model Design Document: PeakCurrEst_MDD"
description: "Model Design Document for Motor Control (Current Mode) (converted)."
---

# Motor Control (Current Mode) — Model Design Document: PeakCurrEst_MDD

> Source: `MtrCtrl_CM/doc/PeakCurrEst_MDD.docx` (244,532 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module – PeakCurrEst

# High-Level Description

# Figures

## Component Diagram

## Variable Data Dictionary

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

LPF_SvUpdate_u16InFixKTrunc_m

LPF_OpUpdate_u16InFixKTrunc_m

LPF_SvUpdate_s16InFixKTrunc_m

LPF_OpUpdate_s16InFixKTrunc_m

FPM_FloatToFixed_m

FPM_FixedToFloat_m

Limit_m

## Data Hiding Functions

None

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

None

## Initialization Functions

None

## Periodic Functions

### Per: PeakCurrEst_Per1

#### Design Rationale

None

#### Program Flow Start

Rte_Call_PeakCurrEst_Per1_CP0_CheckpointReached

#### Store Module Inputs to Local copies

IvtrLoaMtgtnEn_Cnt_T_lgc   =  Rte_IRead_PeakCurrEst_Per1_IvtrLoaMtgtnEn_Cnt_lgc()

MotCurrLoaMtgtnEn_Cnt_T_lgc=  Rte_IRead_PeakCurrEst_Per1_MotCurrLoaMtgtnEn_Cnt_lgc()

EstMtrCurrQax_Amp_T_f32=Rte_IRead_PeakCurrEst_Per1_MtrCurrQaxRef_Amp_f32();

EstMtrCurrDax_Amp_T_f32=Rte_IRead_PeakCurrEst_Per1_MtrCurrDaxRef_Amp_f32();

Else

EstMtrCurrQax_Amp_T_f32=Rte_IRead_PeakCurrEst_Per1_MtrCurrQax_Amp_f32()

EstMtrCurrDax_Amp_T_f32=Rte_IRead_PeakCurrEst_Per1_MtrCurrDax_Amp_f32()

#### Module Design

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_PeakCurrEst_Per1_EstPkCurr_AmpSq_f32(EstPkCurr_AmpSq_T_f32)

#### Program Flow End

Rte_Call_PeakCurrEst_Per1_CP1_CheckpointReached

### Per: PeakCurrEst_Per2

#### Design Rationale

#### Program Flow Start

Rte_Call_PeakCurrEst_Per2_CP0_CheckpointReached()

#### Module Design

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_PeakCurrEst_Per2_FiltEstPkCurr_AmpSq_f32(FiltEstPkCurr_AmpSq_T_f32)

#### Program Flow End

#### Rte_Call_PeakCurrEst_Per2_CP1_CheckpointReached()

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

|  |  |  |

|  |  |  |

| Refer the Data Dictionary for inputs /outputs | Refer the Data Dictionary for inputs /outputs |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| Refer the Data Dictionary for Module level variables |  |  |  |  |

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

| k_EstPkCurr2msLPFKn_Uls_u16 |

| k_EstPkCurrSlowLoopLPFKn_Uls_u16 |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| None |  |  |  |

|  |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| D_ESTPKCURRLOLMT_AMPSQ_F32 |

| D_ESTPKCURRHILMT_AMPSQ_F32 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Function Name | Calling Frequency | System State(s) in which the function is called |

| PeakCurrEst_Per1 | 2ms | OFF,DISABLE,OPERATE |

| PeakCurrEst_Per2 | 100ms | OFF,DISABLE,OPERATE |
