---
title: "Signal Conditioning — Model Design Document: SignalConditioning_MDD"
description: "Model Design Document for Signal Conditioning (converted)."
---

# Signal Conditioning — Model Design Document: SignalConditioning_MDD

> Source: `SgnlCond/doc/SignalConditioning_MDD.docx` (123,495 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module – Signal Conditioning

# High-Level Description

This function conditions a signal received from SER prior to its distribution to other functions. Typical conditioning methods may include filters, slew rates, gain values or limits.

# Figures

## Diagram – Function Data Sharing

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

## Lookup Table Definitions

# Software Module Implementation

## Initialization Functions

None

## Periodic Functions

### Per: SignlCondn _Per1

#### Design Rationale

NOTE: For “starttime” calculations there is tendency for underflow and this is expected in s/w design. So for unittesting, VBA model should be implemented

such that it handles underflow and behaves like source code design.

#### Program Flow Start

#### Rte_Call_SignlCondn_Per1_CP0_CheckpointReached()Store Module Inputs to Local copies

SrlComVehSpd_Kph_T_f32 = Rte_IRead_SignlCondn_Per1_SrlComVehSpeed_Kph_f32

SrlComVehLonAccel_KphpS_T_f32 = Rte_IRead_SignlCondn_Per1_SrlCom_VehicleLonAccel_KphpS_f32()

#### Signal Conditioning

#### Store Local copy of outputs into Module Outputs

Rte_Iwrite_SignlCondn_Per1_VehicleSpeed_Kph_f32 (SignlCondn_CurrSrlComVehSpd_Kph_M_f32)

Rte_IWrite_SignlCondn_Per1_Vehicle_LonAccel_KphpS_f32(SignlCondn_CurrSrlComVehLonAccel_KphpS_M_f32)

#### Program Flow End

Rte_Call_SignlCondn_Per1_CP1_CheckpointReached()

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

# Requirements

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

INLINE functions defined in globalmacro.h are not unit tested

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs (Global Variable Name) | Module Outputs (Global Variable Name) |

| SrlComVehSpd_Kph_f32 |  |

| SrlCom_VehicleLonAccel_KphpS_f32 | Vehicle_LonAccel_KphpS_f32 |


**Table 2 (from source document):**


| Variable Name | Resolution | (min) | (max) | Software Segment |

| SignlCondn_CurrSrlComVehSpd_Kph_M_f32 | Single precision floating point | See DataDictionary | See DataDictionary | SIGNLCONDN_START_SEC_VAR_NOINIT_32 |

| SignlCondn_CurrSrlComVehLonAccel_KphpS_M_f32 | Single precision floating point | See DataDictionary | See DataDictionary | SIGNLCONDN_START_SEC_VAR_NOINIT_32 |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | (min) | (max) |


**Table 4 (from source document):**


| Constant Name |

| k_VehSpdSlewRate_KphpSec_f32 |

| k_VehAccelSlewRate_KphpSecSq_f32 |


**Table 5 (from source document):**


| Constant Name | Resolution | Value |

| D_VEHLONACCELGAIN_KPHPS_F32 | N/A | 3.6 |

| D_VEHSPDLOLMT_KPH_F32 | Single precision Float | 0.0 |

| D_VEHSPDHILMT_KPH_F32 | Single precision Float | 511.0 |

| D_VEHLONACCELLOLMT_KPHPS_F32 | Single precision Float | (-50.0) |

| D_VEHLONACCELHILMT_KPHPS_F32 | Single precision Float | 50.0 |


**Table 6 (from source document):**


| Constant Name |

| D_2MS_SEC_F32 |

| BC_SIGNLCONDN_FAULTINJECTIONPOINT |

| FLTINJ_SRLCOMVEHSPD_SGNLCOND |

| FLTINJ_SRLCOMVEHLONACCEL_SGNLCOND |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Function Name | Calling Frequency | in which the function is called |

| SignlCondn_Per1 | 2 ms | ALL States |

|  |  |  |
