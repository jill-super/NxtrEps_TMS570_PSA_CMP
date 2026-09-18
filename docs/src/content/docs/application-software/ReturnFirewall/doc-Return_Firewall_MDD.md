---
title: "Steering Return Firewall (Safety Monitor) — Model Design Document: Return_Firewall_MDD"
description: "Model Design Document for Steering Return Firewall (Safety Monitor) (converted)."
---

# Steering Return Firewall (Safety Monitor) — Model Design Document: Return_Firewall_MDD

> Source: `ReturnFirewall/doc/Return_Firewall_MDD.docx` (388,390 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module –

# High-Level Description

This module limits the return command according to safety requirements.

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

BilinearXMYM_s16_s16XMs16YM_Cnt

TableSize_m

Limit_m

Rte_Call_NxtrDiagMgr_SetNTCStatus

## Data Hiding Functions

None

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

#### Rte_Call_ReturnFirewall_Per1_CP0_CheckpointReachedStore Module Inputs to Local copies

HandwheelPosition_HwDeg_T_f32 = Rte_IRead_ReturnFirewall_Per1_HandwheelPosition_HwDeg_f32()

ReturnCmd_MtrNm_T_f32 = Rte_Iread_ReturnFirewall_Per1_ReturnCmd_MtrNm_f32()

VehicleSpeed_Kph_T_f32 = Rte_Iread_ReturnFirewall_Per1_VehicleSpeed_Kph_f32()

VehicleSpeed_Kph_T_u9p7 = FPM_FloatToFixed_m(VehicleSpeed_Kph_T_f32, u9p7_T)

HandwheelPosition_HwDeg_T_s11p4 = FPM_FloatToFixed_m(HandwheelPosition_HwDeg_T_f32, s11p4_T)

#### Perform Boundary Lookups and Limiting

#### Store Local copy of outputs into Module Outputs

UprBound_MtrNm_D_f32 = UprBound_MtrNm_T_f32

LwrBound_MtrNm_D_f32 = LwrBound_MtrNm_T_f32

#### Program Flow End

Rte_Call_ReturnFirewall_Per1_CP1_CheckpointReached

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

ReturnFirewall_Per1 is executed at a rate of 2 ms.

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

| HandwheelPosition_HwDeg_f32 | HandwheelPosition_HwDeg_f32 | LimitedReturn_MtrNm_f32 |

| ReturnCmd_MtrNm_f32 | ReturnCmd_MtrNm_f32 |  |

| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 |  |

|  |  |  |

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| UprBound_MtrNm_D_f32 | Single Precision Float | -8.8 | 8.8 | RETURNFIREWALL_START_SEC_VAR_CLEARED_32 |

| LwrBound_MtrNm_D_f32 | Single Precision Float | -8.8 | 8.8 | RETURNFIREWALL_START_SEC_VAR_CLEARED_32 |

| OverBound_Cnt_D_lgc | N/A | FALSE | TRUE | RETURNFIREWALL_START_SEC_VAR_CLEARED_BOOLEAN |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| t_RtrnFWVehSpd_Kph_u9p7[] |

| t_RtrnFWUprBoundX_HwDeg_s11p4[] |

| t2_RtrnFWUprBoundY_MtrNm_s4p11[][] |

|  |

|  |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| None |  |  |  |

|  |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| D_ONE_ULS_F32 |

| D_ZERO_ULS_F32 |

| D_NEGONE_CNT_S16 |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Data | Value |

| Rte_InitValue_HandwheelPosition_HwDeg_f32 | 0 |

| Rte_InitValue_LimitedReturn_MtrNm_f32 | 0 |

| Rte_InitValue_ReturnCmd_MtrNm_f32 | 0 |

| Rte_InitValue_VehicleSpeed_Kph_f32 | 0 |
