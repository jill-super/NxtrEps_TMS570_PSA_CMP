---
title: "Diagnostics Manager — Model Design Document: Diagnostics_Manager_DemIf_MDD"
description: "Model Design Document for Diagnostics Manager (converted)."
---

# Diagnostics Manager — Model Design Document: Diagnostics_Manager_DemIf_MDD

> Source: `DiagMgr/doc/Diagnostics_Manager_DemIf_MDD.docx` (677,333 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- Diagnostics Manager DEM Interface

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

### Diagnostic Manager Init 1

#### Description

### Diagnostic Manager Transition 1

#### Description

Rte_Call_DemIf_RestartDem()

Rte_Call_DemIf_SetOperationCycleState(NxtrDefaultOpCycle, NXTR_CYCLE_STATE_START)

### Diagnostic Manager StaCtrl Shutdown

#### Description

Rte_Call_DemIf_SetOperationCycleState(NxtrDefaultOpCycle, NXTR_CYCLE_STATE_END)

Rte_Call_DemIf_DemShutdown()

CreateStorageArray(1U)

NvM_SetRamBlockStatus(NVM_BLOCK_DIAGMGR_NTCSTRG, TRUE)

NvM_SetRamBlockStatus(NVM_BLOCK_DIAGMGR_BLACKBOX, TRUE)

### Diagnostic Manager Periodic 2

#### Description

### Diagnostic Manager Get NTC Information

#### Description

### Diagnostic Manager Reset NTC Status

#### Description

ResetNTCFlag_Cnt_M_u08 = ~ResetNTCFlag_Cnt_M_u08

### Diagnostic Manager Read Storage Array

#### Description

CreateStorageArray(0U)

### Diagnostic Manager Clear Black Box

#### Description

### Diagnostic Manager Clear Latch Counters

#### Description

### Update Black Box

#### Description

## Local Functions/Macros Used by this MDD only

### Create Storage Array

#### Description

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

The latch active counters will not be stepped/checked on a quick ignition cycle as the Init1 function will not be called.

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| IgnCnt_Cnt_u16 | IgnCnt_Cnt_u16 |  |

| MtrTrq_MtrNm_f32 | MtrTrq_MtrNm_f32 |  |

| VehSpd_Kph_f32 | VehSpd_Kph_f32 |  |

| HwTrq_HwNm_f32 | HwTrq_HwNm_f32 |  |

| SystemState_Mode | SystemState_Mode |  |


**Table 2 (from source document):**


| Variable Name | Datatype | Resolution | Resolution | Legal Range<br/>(min) | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment<br/>{Data Type} | Software Segment<br/>{Data Type} | Software Segment<br/>{Data Type} |

| DEMEventActive_Cnt_M_lgc[D_NUMOFDEMEVENTS_CNT_U08+1] | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx |

| ResetNTCFlag_Cnt_M_u08 | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx | Diagnostics_Manager_GeneratedCfg_MDD.docx |

| LatchCounter_Cnt_u16 | uint16 | uint16 | 1 | 1 | 0 | 0 | 0 | 65535 | DIAGMGRDEMIF_START_SEC_VAR_16 |

| NTCStrgArray_Cnt_str | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx |

| NTCBlackBoxData_Cnt_str | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx | Refer to Diagnostics_Manager_Core_MDD.docx |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| Typedef struct {} NTCLatch_Str | NTC | NTCNumber | 0 | 511 |

|  | DiagSettings_Str.Threshold | Uint16 | 0 | 65535 |

|  | DiagSettings_Str.PStep | Uint16 | 0 | 65535 |

|  | DiagSettings_Str.NStep | Uint16 | 0 | 65535 |


**Table 4 (from source document):**


| Constant Name |

| t_SortedNTCs_Cnt_enum[] |

| k_FltRspTbl_Cnt_str[] |

| t_BlkBoxGrp_Ptr_u32[][] |

| t_LatchFaults_Cnt_str[] |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_EVTNOTPASSBITS_CNT_B8 | N/A | Counts | (D_TESTFAILEDBIT_CNT_B8 | D_TESTNOTCOMPLETETHISOPCYCLEBIT_CNT_B8) |

| D_AGINGCOUNTERTHRESH_CNT_U08 | N/A | Counts | 0x40 |


**Table 6 (from source document):**


| Constant Name |

| D_NUMOFDEMEVENTS_CNT_U08 |

| D_TESTFAILEDBIT_CNT_B8 |

| D_TESTNOTCOMPLETETHISOPCYCLEBIT_CNT_B8 |

| D_NTCACTIVEBITS_CNT_B8 |

| D_MAXLATCHACTIVENTCS_CNT_U08 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| T_DiagMgrNtcAppInfoMap_Cnt_Str[SIZE] |  | Refer * | AP_DIAGMGR_CONST |

| T_DiagMgrNtcInfoPtr_Cnt_Str[SIZE] |  | Refer * | AP_DIAGMGR_CONST |

|  |  |  |  |


**Table 8 (from source document):**


| Function Name | DiagMgr_Init1 | Type | Min | Max |

| Arguments Passed | none |  |  |  |

| Return Value | none |  |  |  |
