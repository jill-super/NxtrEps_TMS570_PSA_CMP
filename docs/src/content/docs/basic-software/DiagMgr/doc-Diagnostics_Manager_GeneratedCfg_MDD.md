---
title: "Diagnostics Manager — Model Design Document: Diagnostics_Manager_GeneratedCfg_MDD"
description: "Model Design Document for Diagnostics Manager (converted)."
---

# Diagnostics Manager — Model Design Document: Diagnostics_Manager_GeneratedCfg_MDD

> Source: `DiagMgr/doc/Diagnostics_Manager_GeneratedCfg_MDD.docx` (321,343 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- Diagnostics Manager Core

# High-Level Description

# Figures

## Component Diagram

# Variable Data Dictionary

## Module Internal Variables

Note: *Refer: Size varies across projects. Check Configuration files under UTP/Contract folder

### User defined typedef definition/declaration

# Constant Data Dictionary

## Calibration Constants

## Program(fixed) Constants

### Embedded Constants

#### Local

#### Global

### Note **: Global const values varies across projects. Check configuration files under UTP/Contract folder. “#” denotes application number.

### Module specific Lookup Tables Constants

**NOTE : Elements and Size of table are different across different projects and applications. Check Configuration files under UTP/Contract folder

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

TableSize_m()

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

### Diagnostic Manager Initialization

#### Description

### Diagnostic Manager Periodic Code

#### Description

### Diagnostic Manager Transition Core

#### Description

### Diagnostic Manager Get NTC Failed

#### Description

### Diagnostic Manager Get NTC Active

#### Description

### Diagnostic Manager Get NTC Status

#### Description

### Diagnostic Manager Set NTC Status

#### Description

### Diagnostic Manager Report NTC Status

#### Description

## Local Functions/Macros Used by this MDD only

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

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Datatype | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment<br/>{Data Type} |

| ResetNTCFlag_Cnt_M_u08 | Uint8 | 1 | 0<br/>FF | 0<br/>FF | DIAGMGR#_START_SEC_VAR_CLEARED_8 |

| NTCQueueIndex#_Cnt_M_u08 | Uint8 | 1 | Range depends on size of NTCInfoQueue#_Cnt_M_Str[SIZE]<br/>Refer * | Range depends on size of NTCInfoQueue#_Cnt_M_Str[SIZE]<br/>Refer * | DIAGMGR#_START_SEC_VAR_CLEARED_UNSPECIFIED |

| DiagMgrInitComp#_Cnt_M_lgc | Boolean | NA | False | True | DIAGMGR#_START_SEC_VAR_CLEARED_Unspecified |

| DiagMgr_NTCInfo#_Cnt_M_str[SIZE] | NTCInfo_Str | NA | See section 3.1.1 | See section 3.1.1 | DIAGMGR#_START_SEC_VAR_CLEARED_Unspecified |

| NTCInfoQueue#_Cnt_M_str[SIZE] | NTCInfoQueue_Str | NA | See section 3.1.1 | See section 3.1.1 | DIAGMGR#_START_SEC_VAR_CLEARED_Unspecified |

| ActDiagSts#_Cnt_M_u08 | Uint8 | 1 | 0 | 1 | DIAGMGR#_START_SEC_VAR_CLEARED_8 |

| ResetNTCFlag#_Cnt_M_u08 | Uint8 | 1 | 0<br/>FF | 0<br/>FF | DIAGMGR#_START_SEC_VAR_CLEARED_8 |

| DiagSts#_Cnt_M_b16[SIZE] | Uint16 | 1 | 0 | FULL | DIAGMGR#_START_SEC_VAR_CLEARED_Unspecified |

| ActiveRmpRate#_UlspmS_M_f32[SIZE] | Float32 | Single Precision float | 0.0001 | 0.5 | DIAGMGR#_START_SEC_VAR_CLEARED_32 |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

|  |  |  |  |  |

|  |  |  |  |  |

| typedef struct { } NTCInfo_Str | Param | uint8 | 0 | FULL |

| typedef struct { } NTCInfo_Str | Status | uint8 | 0 | FULL |

| typedef struct { } NTCInfo_Str | AgingCounter | uint8 | 0 | FULL |

| typedef struct { } NTCInfoQueue_Str | NTC | NTCNumber | 0 | 511 |

|  | Param | Uint8 | 0 | FULL |

|  | Status | NxtrDiagMgrStatus | 0 | 255 |


**Table 4 (from source document):**


| Constant Name |

| k_FltRspTbl_Cnt_str[] |

| k_FltRmpRate_UlspmS_f32[] |


**Table 5 (from source document):**


| Constant Name |

| ** DIAGMGR_NUMAPPS |

| ** DIAGMGR_EVENTNUM_# |

| ** DIAGMGR_APID_# |

|  |


**Table 6 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| T_NTCMapTbl#_Cnt_enum[SIZE] | N/A | { ** } | AP_DIAGMGR_CONST |

| T_DiagMgrNtcInfoPtr_Cnt_Str[SIZE] | N/A | ** {&DiagMgr_NTCInfo#_Cnt_M_str[0], #,<br/>} | AP_DIAGMGR_CONST |

| T_DiagMgrNtcAppInfoMap_Cnt_Str[SIZE] | N/A | ** {{ &DiagMgr_NTCInfo#_Cnt_M_str[0], #},<br/>…<br/>} | AP_DIAGMGR_CONST |


**Table 7 (from source document):**


| Function Name | DiagMgr#_Init | Type | Min | Max |

| Arguments Passed | None |  |  |  |

| Multiplicity |  |  |  |  |

| Return Value | None |  |  |  |


**Table 8 (from source document):**


| Function Name | DiagMgr#_Per | Type | Min | Max |

| Arguments Passed | None |  |  |  |

| Multiplicity |  |  |  |  |

| Return Value | none |  |  |  |
