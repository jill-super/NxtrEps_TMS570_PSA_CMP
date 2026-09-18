---
title: "PSA State Handler — Model Design Document: PSASH_MDD"
description: "Model Design Document for PSA State Handler (converted)."
---

# PSA State Handler — Model Design Document: PSASH_MDD

> Source: `PSAStHdlr/doc/PSASH_MDD.docx` (202,580 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

CF13 PSA State Handler

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

SEPG,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

# Introduction

## Purpose

Module Design Document for CF13 PSA State Handler.

## Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance.

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.

May: indicates an optional action.

# CF13 PSA State Handler & High-Level Description

PSA state handler function will determine the state of the City Park. The states include Unavailable, Available, Control in Progress and Defective.

The states of the City Park State Handler Function are dependent upon Vehicle speed, Activation Request from the PSA City Park Controller, System Ambient temperature, Thermal Derating and Hand wheel Torque.

This City Park State Handler provides input to the Torque Arbitrator of City Park function.

# Design details of software module

## Graphical representation of CF13 PSA State Handler

## Data Flow Diagram

Refer FDD

### Module level DFD

Refer FDD

### Sub-Module level DFD

Refer FDD

## Component diagram

Refer FDD

## Variable Data Dictionary

### User defined ‘typedef’ definition/declaration

### Variable definition for enumerated types

## Constant Data Dictionary

### Program Constants

#### Local Constants

#### Global Constants

### Module Specific Lookup Tables

## Software Module Implementation

### Sub-Module Functions

#### Initialization sub-module PSASH_Init1

Refer FDD

#### Periodic sub-module PSASH_Per1

Refer FDD

#### Non Periodic sub-module {_NONPer()}

None

### Interrupt Service Routines

None

### _SCOMM () Functions

None

### Module Internal (Local) Functions

#### Local Function ComputeLxaDrvrBhvr

Implementation of "Compute_LxaDrvrBhvr" block in the FDD.

#### Local Function ComputeLxaHwAgThd

Implementation of "Compute_LxaHwAgThd" block. This function determines 'LxaHwAgDetnCntrNStep_Cnt_T_u16', ‘LxaHwAgDetnCntrPStep_Cnt_T_u16' and ‘LxaHwAgThd_HwDeg_T_f32'.

#### Local Function ComputeLxaHwVelThd

Implementation of "Compute_LxaHwVelThd" block.

#### Local Function ComputeLxaHowDetnTime

Implementation of "Compute_LxaHowDetnTime" block. This function determines 'LxaDrvrAbsntDetdTi_Sec_T_f32'.

#### Local Function ComputeLxaInactivOnDrvrBhvr

Implementation of "Compute_LxaInactivOnDrvrBhvr" state flow in the FDD.

#### Local Function LxaHwAgMon

Implementation of "LxaHwAgMon" state flow in the FDD.

#### Local Function LxaHwTrqMon

Implementation of "LxaHwTrqMon" state flow in the FDD.

#### Local Function LxaHwVelMon

Implementation of "LxaHwVelMon" state flow in the FDD.

#### Local Function ComputeLxaDrvrAbsntDetd

Implementation of "Compute_LxaDrvrAbsntDetd" state flow in the FDD.

#### Local Function ComputeLxaInactivRstTmr

Implementation of "Compute_LxaInactivRstTmr" block flow in the FDD.

#### Local Function ComputeEPSState

Implementation of "Compute_EPSState" block. This function determines 'EPSState_Cnt_T_enum’.

#### Local Function ComputeEPSStateForLxa

Implementation of "Compute_EPSStateForLxa" state flow in the FDD.

#### Local Function ComputeEPSStateForLxa_ParentTransitions

Fragment of implementation of "Compute_EPSStateForLxa" state flow.

#### Local Function ComputeEPSStateForLxa_ChildTransitions

Fragment of implementation of "Compute_EPSStateForLxa" state flow.

#### Local Function ComputeAPA

Implementation of "APA" block in the FDD.

#### Local Function ComputeApaAllw

Implementation of "Compute_ApaAllw" block in the FDD.

#### Local Function ComputeApaLimits

Implementation of "Compute_ApaLimits" block in the FDD.

#### Local Function ComputeApaDrvrIntv

Implementation of "Compute_ApaDrvrIntv" block in the FDD.

#### Local Function ComputeApaHwAgCtrlErr

Implementation of "Compute_ApaHwAgCtrlErr" block in the FDD.

#### Local Function ComputeApaFltActv

#### Local Function ComputeApaState

Implementation of "Compute_ApaState" state flow in the FDD.

#### Local Function ComputeApaState_ParentTransitions

Fragment of implementation of "Compute_ApaState" state flow.

#### Local Function ComputeApaState_ChildTransitions

Fragment of implementation of "Compute_ApaState" state flow.

#### Local Function ComputePosSrvoEnable

Implementation of " Compute_PosSrvoEnable" block in the FDD

### Transition Functions

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

FDD describes functionality and structural breakdown of this component. Data dictionary contains all attributes of variables and calibrations used.

# Abbreviations and Acronyms

# Glossary

Note: Terms and definitions from the source “Nexteer Automotive” take precedence over all other definitions of the same term.  Terms and definitions from the source “Nexteer Automotive” are formulated from multiple sources, including the following:

ISO 9000

ISO/IEC 12207

ISO/IEC 15504

Automotive SPICE® Process Reference Model (PRM)

Automotive SPICE® Process Assessment Model (PAM)

ISO/IEC 15288

ISO 26262

IEEE Standards

SWEBOK

PMBOK

Existing Nexteer Automotive documentation

# References


**Table 1 (from source document):**


| Description | Author | Version | Date |

| Initial Version | Sankardu Varadapureddi | 1.0 | 27-Feb-2015 |

| Updated for FDD version 4.1.0 | Sankardu Varadapureddi | 2.0 | 6-June-2016 |

| Updated till FDD version 5.1.0 | Krishna Anne | 3.0 | 26-Oct-2016 |

| Updated till FDD version 5.3.0 Fix for anomaly EA3#13197 | Krishna Anne | 4.0 | 15-Dec-2016 |

| Updated for FDD version 6.1.0 | Krishna Anne | 5.0 | 23-Feb-2017 |

| Updated for FDD version 7.0.0 | Krzysztof Byrski | 6.0 | 16-Aug-2017 |

|  |  |  |  |

|  |  |  |  |


**Table 2 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |


**Table 3 (from source document):**


| Enum  Name | Element Name | Value |

| None |  |  |


**Table 4 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_APA_UNAVAILABLE_CNT_U08 | 1 | Cnt | 0 |

| D_APA_UNAVAILABLE_THERMALLIMIT_CNT_U08 | 1 | Cnt | 1 |

| D_APA_UNAVAILABLE_NOAUTHORIZATION_CNT_U08 | 1 | Cnt | 2 |

| D_APA_DEFECT_CNT_U08 | 1 | Cnt | 3 |

| D_APA_AVAILABLE_CNT_U08 | 1 | Cnt | 4 |

| D_APA_AVAILABLE_VEHICLESPEEDTOOHIGH_CNT_U08 | 1 | Cnt | 5 |

| D_APA_AVAILABLE_HWTORQUETOOHIGH_CNT_U08 | 1 | Cnt | 6 |

| D_APA_AVAILABLE_MOTORSTALLED_CNT_U08 | 1 | Cnt | 7 |

| D_APA_AVAILABLE_HWANGLECONTROLERROR_CNT_U08 | 1 | Cnt | 8 |

| D_APA_CONTROLPROGRESS_CNT_U08 | 1 | Cnt | 9 |

| D_APA_DEFAULT_CNT_U08 | 1 | Cnt | 255 |

| D_LXA_UNAUTHORIZED_CNT_U08 | 1 | Cnt | 0 |

| D_LXA_AUTHORIZED_CNT_U08 | 1 | Cnt | 1 |

| D_LXA_AVAILABLE_CNT_U08 | 1 | Cnt | 2 |

| D_LXA_ACTIVE_CNT_U08 | 1 | Cnt | 3 |

| D_LXA_DEFECT_CNT_U08 | 1 | Cnt | 4 |

| D_LXA_DEFAULT_CNT_U08 | 1 | Cnt | 255 |

| D_FLTEPSILON_ULS_F32 | Single Precision float | Uls | 1.192092896e-07 |

| D_HWTRQBUFSIZE_ULS_U08 | 1 | Uls | 250 |

| D_HWTRQRATEMAXLIM_HWDEGPS_F32 | Single Precision float | HwDegPS | 2000.0 |

| D_HWTRQRATEMINLIM_HWDEGPS_F32 | Single Precision float | HwDegPS | 0.0 |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

| D_POSSERVOHWAGMAXLIM_HWDEG_F32 | Single Precision float | HwDeg | 1.0 |

| D_POSSERVOHWAGMINLIM_HWDEG_F32 | Single Precision float | HwDeg | -10 |

| D_SAMPLETIME_CNT_U16 | 1 | Cnt | 2 |

| D_U16MAX_CNT_U16 | 1 | Cnt | 65535U |

| D_U16MAX_HWDEG_F32 | Single Precision float | HwDeg | 65535U.0 |

|  |  |  |  |

| D_ZERO_HWDEG_F32 | Single Precision float | HwDeg | 0.0 |

| D_ZERO_HWNMPS_F32 | Single Precision float | HwNmPS | 0.0 |

| D_ZERO_SEC_F32 |  | Sec | 0.0 |


**Table 5 (from source document):**


| Constant Name |

| D_FALSE_CNT_LGC |

| D_TRUE_CNT_LGC |

| D_2MS_SEC_F32 |

| D_MSECPERSEC_ULS_F32 |

| D_MTRTRQCMDHILMT_MTRNM_F32 |

| D_ONE_ULS_F32 |

| D_ZERO_ULS_F32 |

| D_PSAAPASTINIT_CNT_ENUM |

| D_PSAAPATRANCAUSEINIT_CNT_ENUM |

| D_PSAEPSSTLXAINIT_CNT_ENUM |

| D_PSALXASTINIT_CNT_ENUM |

| D_ZERO_CNT_S8 |

| D_ZERO_CNT_U16 |

| D_ONE_CNT_U8 |

| D_ZERO_CNT_U8 |


**Table 6 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None | - | - | - |


**Table 7 (from source document):**


| Function Name | ComputeLxaDrvrBhvr | Type | Min | Max |

|  |  |  |  |  |

|  | LxaSelected_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | HOWState_Cnt_T_s08 | sint8 | -3 | 3 |

|  | LxaInpVld_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | LxaState_Cnt_T_enum | enum | 0 | 6 |

|  | HandwheelVelocity_HwRadpS_T_f32 | float32 | -32 | 32 |

|  | HwTqFild_HwNm_T_f32 | float32 | -10 | 10 |

|  | LpaSeld_Cnt_T_lgc | boolean | FALSE | TRUE |

|  |  | float32 |  | 1 |

|  |  |  |  |  |

| Return Value | DrvrIntvDetd_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | HwTrqRate_HwNmpS_T_f32 | float32 | 0 | 2000 |


**Table 8 (from source document):**


| Function Name | ComputeLxaHwAgThd | Type | Min | Max |

| Arguments Passed | VehicleSpeed_Kph_T_u9p7 | uint16 | 0 | 65408 |

|  |  | float32 |  | 10 |

| Return Value | LxaHwAgDetnCntrNStep_Cnt_T_u16 | uint16 | 0 | 65535 |

|  | LxaHwAgDetnCntrPStep_Cnt_T_u16 | uint16 | 0 | 65535 |

|  | LxaHwAgThd_HwDeg_T_f32 | float32 | 0 | 65535 |
