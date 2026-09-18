---
title: "Diagnostics Manager — Model Design Document: Diagnostics_Manager_FailAction_MDD"
description: "Model Design Document for Diagnostics Manager (converted)."
---

# Diagnostics Manager — Model Design Document: Diagnostics_Manager_FailAction_MDD

> Source: `DiagMgr/doc/Diagnostics_Manager_FailAction_MDD.docx` (245,265 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- Diagnostics Manager Fail Action

# High-Level Description

# Figures

## Component Diagram

# Variable Data Dictionary

## Module Internal Variables

### User defined typedef definition/declaration

# Constant Data Dictionary

## Calibration Constants

## Program(fixed) Constants

### Embedded Constants

#### Local

#### Global

### Module specific Lookup Tables Constants

Note: “ Refer *” -  Refer to Diagnostics_Manager_GeneratedCfg_MDD

Note Size and elements of Table constants varies across projects. Check project configuration files Under UTP/ Contract folder for data.

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

TableSize_m()

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

### Diagnostic Manager Periodic 1

#### Description

## Local Functions/Macros Used by this MDD only

### Read Bits

#### Description

IF  (Data & BitMask) = 0

Return (FALSE)

ELSE
	Return(TRUE)

END IF

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

## Initialization Functions

None

## Periodic Functions

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

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

## Global and Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

(Item #1)

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

|  |  | DiagStsNonRecRmpToZeroFltPres_Cnt_lgc |

|  |  | DiagStsCtrldDisRmpPres_Cnt_lgc |

|  |  | DiagStsRecRmpToZeroFltPres_Cnt_lgc |

|  |  | DiagStsHWASbSystmFltPres_Cnt_lgc |

|  |  | DiagStsDefVehSpd_Cnt_lgc |

|  |  | DiagStsDefTemp_Cnt_lgc |

|  |  | DiagStsScomHWANotValid_Cnt_lgc |

|  |  | DiagStsWIRDisable_Cnt_lgc |

|  |  | DiagRampRate_XpmS_f32 |

|  |  | DiagRampValue_Uls_f32 |

|  |  | DiagRmpToZeroActive_Cnt_lgc |

|  |  |  |

|  |  |  |

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Datatype | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment<br/>{Data Type} |

| DiagSts#_Cnt_M_b16[2] | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx |

| ActiveRmpRate#_UlspmS_M_f32[2] | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx | Refer to Diagnostics_Manager_GeneratedCfg_MDD.docx |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

|  |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

|  |

|  |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

|  |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| DIAGMGR_NUMAPPS |

| D_DIAGSTSNONRECRMPTOZEROBIT_CNT_B16 |

| D_DIAGSTSRECRMPTOZEROBIT_CNT_B16 |

| D_DIAGSTSCTRLDDISRMPBIT_CNT_B16 |

| D_DIAGSTSHWASBSYSTMFLTBIT_CNT_B16 |

| D_DIAGSTSDEFVEHSPDBIT_CNT_B16 |

| D_DIAGSTSDEFTEMPBIT_CNT_B16 |

| D_DIAGSTSSCOMHWANOTVALIDBIT_CNT_B16 |

| D_DIAGSTSWIRDISABLEBIT_CNT_B16 |

|  |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| T_DiagMgrDiagSts_Ptr_b16[SIZE] | N/A | Refer * | AP_DIAGMGR_CONST |

| T_DiagMgrRmpRate_Ptr_f32[SIZE] | N/A | Refer * | AP_DIAGMGR_CONST |

|  |  |  |  |


**Table 8 (from source document):**


| Function Name | DiagMgr_Per1 | Type | Min | Max |

| Arguments Passed | none |  |  |  |

| Return Value | none |  |  |  |
