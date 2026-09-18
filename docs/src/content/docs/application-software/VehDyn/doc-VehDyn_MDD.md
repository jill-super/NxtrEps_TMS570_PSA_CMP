---
title: "Vehicle Dynamics Interface — Model Design Document: VehDyn_MDD"
description: "Model Design Document for Vehicle Dynamics Interface (converted)."
---

# Vehicle Dynamics Interface — Model Design Document: VehDyn_MDD

> Source: `VehDyn/doc/VehDyn_MDD.docx` (188,724 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

VehDyn

March 08, 2018

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

SEPG,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	VehDyn & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of VehDyn	6

3.2	Data Flow Diagram	6

3.2.1	Module level DFD	6

3.2.2	Sub-Module level DFD	6

3.3	Component diagram	6

3.4	Variable Data Dictionary	7

3.4.1	User defined ‘typedef’ definition/declaration	7

3.4.2	Variable definition for enumerated types	7

3.5	Constant Data Dictionary	8

3.5.1	Program Constants	8

3.5.2	Module Specific Lookup Tables	8

3.6	Software Module Implementation	9

3.6.1	Sub-Module Functions	9

3.6.2	Interrupt Service Routines	9

3.6.3	_SCOMM () Functions	9

3.6.4	Module Internal (Local) Functions	10

3.6.5	Transition Functions	12

4	Known Limitations with Design	13

5	UNIT TEST CONSIDERATION	14

Appendix A	Abbreviations and Acronyms	15

Appendix B	Glossary	16

Appendix C	References	17

# Introduction

## Purpose

Module Design Document for SF42 - VehDyn.

## Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance.

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.

May: indicates an optional action.

# VehDyn & High-Level Description

This module calculates HandWheel AutoCentering and determines the Vehicle Dynamics HandWheel Position and Vehicle Dynamics Authority.

# Design details of software module

## Graphical representation of VehDyn

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

Refer FDD

### Sub-Module Functions

#### Initialization sub-module VehDyn_Init1()

Assignment of calibrations to Hi, Lo and Det speed dependant structures for use with vehicle dynamics is done here as the copy of calibrations only needs to be done once and there are variables internal to the structures that must also be initialized.

#### Periodic sub-module VehDyn_Per1

Vehicle dynamics takes advantage of the fact that the conditions for determining use of the high speed algorithm follow the exact same procedure as in the common autocentering algorithm. Therefore, a third structure is used to determine the switch to high speed using a combination of  cals defined for LoSpd AutoCentering, HiSpd Autocentering, and “HiSpdTimer4” in the FDD. Instead of using the output generated from this autocenterring algorithm, the Filter2Enable_Cnt_lgc flag is examined and when it becomes TRUE, high speed autocentering is allowed.

### Interrupt Service Routines

None

### _SCOMM () Functions

#### VehDyn_SCom_ResetCenter

Refer FDD

#### VehDyn_SCom_ForceCenter

Refer FDD

### Module Internal (Local) Functions

#### Local Function SerialCommMethod

#### Local Function Autocenter_f32

#### Local Function TrvlExclsn

#### Local Function Arbn_f32

#### Local Function SmoothHwPos_f32

### Transition Functions

#### VehDyn_Trns1

This function implements the Power Off functions defined in the FDD model.

# Known Limitations with Design

INLINE functions defined in GlobalMacro.h are not unit tested.

Component name should be changed from “Vehicle Dynamics” or “VehDyn” to “Vehicle Center Determination by Motor Position” or VCDMotPos according to ICR 4616 and FDD rev 002.

VehDyn_SCom_ForceCenter function is required as a manufacturing service for C1XX program and Jared updated the same in v007 of source code (13191) and was supposed to be updated in the next revision of FDD. But in the latest version of FDD v006 released, it’s not implemented.

# UNIT TEST CONSIDERATION

None

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

| Initial Version (SF-42 v001) | KMC | 1.0 | 19-Aug-13 |

| Local constant value and  variable ranges/resolutions updated per FDD data dictionary updates. | KMC | 2.0 | 11-Sep-13 |

| Updated to SF-42 VCDMotPos version 002 | SB | 3.0 | 25-Aug-14 |

| Unit Test Findings Resolved | KPIT, SB | 4.0 | 4-Sep-14 |

| Updated to SF-42 VCDMotPos version 3 | SB | 5.0 | 31-Oct-14 |

| Updated to SF-42 VCDMotPos v004 | SB | 6.0 | 16-Jan-15 |

| Updated to SF-42 VCDMotPos rev 005 | SB | 7.0 | 02-Feb-15 |

| Added SCom function for force center position | JWJ | 8.0 | 27-Feb-15 |

| Updated  to SF-42 VCDMotPos  ver 006 | JK | 9.0 | 13-Aug-15 |

| Updated to SF-42A VehCentrDtmnByMotPosn v7 | SB | 10.0 | 30-Nov-15 |

| Updated to SF-42A VehCentrDtmnByMotPosn v7.1.0 | SB | 11.0 | 15-Dec-15 |

| Updated to SF-42A VehCentrDtmnByMotPosn v7.2.0 (changed max auth to 1) | OT | 12.0 | 7-Jan-15 |

| Updated to SF-42 FDD rev 7.3.0 (Fix for anomaly EA3#6247) | KK | 13.0 | 24-Feb-16 |

| Updated as per Unit Test Findings | KPIT | 14.0 | 06-Apr-2016 |

| Updated inputs/constants, changed cal name, added updated graph | ML | 15.0 | 24-May-17 |

| Updated to FDD rev 9.0.0, new template | Krzysztof Byrski | 16.0 | 08-Mar-2018 |


**Table 2 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| AUTOCNTRTYPE_Str | MtrVel_MtrRadpS_f32 | float32 | 0 | 700 |

| AUTOCNTRTYPE_Str | VehSpd_kph_f32 | float32 | 0 | 255 |

| AUTOCNTRTYPE_Str | FiltPinTrq_HwNm_f32 | float32 | 0 | 20 |

| AUTOCNTRTYPE_Str | CntrWindow_HwDeg_f32 | float32 | 0 | 100 |

| AUTOCNTRTYPE_Str | Timer1Thresh_mS_u16 | uint16 | 0 | 60000 |

| AUTOCNTRTYPE_Str | Timer2Thresh_mS_u16 | uint16 | 0 | 60000 |

| AUTOCNTRTYPE_Str | Timer1_mS_u32 | uint32 | FULL | FULL |

| AUTOCNTRTYPE_Str | Timer2_mS_u32 | uint32 | FULL | FULL |

| AUTOCNTRTYPE_Str | RelHwPosFilt1SV_HwDeg_str | LPF32KSV_Str | N/A | N/A |

| AUTOCNTRTYPE_Str | RelHwPosFilt1SV_HwDeg_str.SV_Uls_f32 | float32 | -3200 | 3200 |

| AUTOCNTRTYPE_Str | RelHwPosFilt1SV_HwDeg_str.K_Uls_f32 | float32 | 2.51327E-06 | 0.001255848 |

| AUTOCNTRTYPE_Str | RelHwPosFilt2SV_HwDeg_str | LPF32KSV_Str | N/A | N/A |

| AUTOCNTRTYPE_Str | RelHwPosFilt2SV_HwDeg_str.SV_Uls_f32 | float32 | -3200 | 3200 |

| AUTOCNTRTYPE_Str | RelHwPosFilt2SV_HwDeg_str.K_Uls_f32 | float32 | 2.51327E-06 | 0.001255848 |

| AUTOCNTRTYPE_Str | Filter1Enable_Cnt_lgc | boolean | FALSE | TRUE |

| AUTOCNTRTYPE_Str | Filter2Enable_Cnt_lgc | boolean | FALSE | TRUE |

| AUTOCNTRTYPE_Str | Filter1Initialized_Cnt_lgc | boolean | FALSE | TRUE |

| AUTOCNTRTYPE_Str | Filter2Initialized_Cnt_lgc | boolean | FALSE | TRUE |


**Table 3 (from source document):**


| Enum  Name | Element Name | Value |

| None |  |  |


**Table 4 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_FCENTROFFSCON_CNT_U08 | 1 | Cnt | 1 |

| D_HWPOSMAX_HWDEG_F32 | Single Precision Float | HwDeg | 1600 |

| D_HWPOSMIN_HWDEG_F32 | Single Precision Float | HwDeg | -1600 |

| D_LASTPOSNCON_CNT_U08 | 1 | Cnt | 5 |

| D_MAXAUTHORITY_ULS_F32 | Single Precision Float | Uls | 1 |

| D_NOAUTHORITY_ULS_F32 | Single Precision Float | Uls | 0 |

| D_SRLCON_CNT_U08 | 1 | Cnt | 2 |

| D_TRVLEXCLSNCON_CNT_U08 | 1 | Cnt | 4 |

| D_VEHDYNCON_CNT_U08 | 1 | Cnt | 3 |


**Table 5 (from source document):**


| Constant Name |

| D_FALSE_CNT_LGC |

| D_TRUE_CNT_LGC |

| D_2MS_SEC_F32 |

| D_ZERO_ULS_F32 |


**Table 6 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 7 (from source document):**


| Function Name | SerialCommMethod | Type | Min | Max |

| Arguments Passed | SrlHwAg_HwDeg_T_f32 | float32 | -1600 | 1600 |

|  | SrlHwAgVld_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | RelHwPos_HwDeg_T_f32 | float32 | -1600 | 1600 |

|  | FildPinionTq_HwNm_T_f32 | float32 | -890 | 890 |

|  | MtrVelCRF_MtrRadpS_T_f32 | float32 | -1118 | 1118 |

|  | HwTorque_HwNm_T_f32 | float32 | -10 | 10 |

| Return Value | Vld_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | HwAg_HwDeg_T_f32 | float32 | -4800 | 4800 |


**Table 8 (from source document):**


| Function Name | Autocenter_f32 | Type | Min | Max |

| Arguments Passed | FiltPinTrq_HwNm_T_f32 | float32 | -18.8 | 18.8 |

|  | MtrVelCRF_MtrRadpS_T_f32 | float32 | -1350 | 1350 |

|  | VehicleSpeed_Kph_T_f32 | float32 | 0 | 512 |

|  | VehSpdValid_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | AutoCntr_Cnt_T_str | AUTOCNTRTYPE_Str* | FULL | FULL |

|  | AutoCntr_Cnt_T_str.MtrVel_MtrRadpS_f32 | AUTOCNTRTYPE_Str* | 0 | 700 |

|  | AutoCntr_Cnt_T_str.VehSpd_kph_f32 | AUTOCNTRTYPE_Str* | 0 | 255 |

|  | AutoCntr_Cnt_T_str.FiltPinTrq_HwNm_f32 | AUTOCNTRTYPE_Str* | 0 | 20 |

|  | AutoCntr_Cnt_T_str.Timer1_mS_u32 | AUTOCNTRTYPE_Str* | 0 | 429496725 |

|  | AutoCntr_Cnt_T_str.Timer1Thresh_mS_u16 | AUTOCNTRTYPE_Str* | 0 | 60000 |

|  | AutoCntr_Cnt_T_str.RelHwPosFilt1SV_HwDeg_str.SV | AUTOCNTRTYPE_Str* | -3200 | 3200 |

|  | AutoCntr_Cnt_T_str.RelHwPosFilt1SV_HwDeg_str.K | AUTOCNTRTYPE_Str* | 2.51327E-06 | 0.001255848 |

|  | AutoCntr_Cnt_T_str.RelHwPosFilt2SV_HwDeg_str.SV | AUTOCNTRTYPE_Str* | -3200 | 3200 |

|  | AutoCntr_Cnt_T_str.RelHwPosFilt2SV_HwDeg_str.K | AUTOCNTRTYPE_Str* | 2.51327E-06 | 0.001255848 |

|  | AutoCntr_Cnt_T_str.CntrWindow_HwDeg_f32 | AUTOCNTRTYPE_Str* | 0 | 100 |

|  | AutoCntr_Cnt_T_str.Timer2Thresh_mS_u16 | AUTOCNTRTYPE_Str* | 0 | 60000 |

|  | AutoCntr_Cnt_T_str.Timer2_mS_u32 | AUTOCNTRTYPE_Str* | 0 | 4294967295 |

|  | AutoCntr_Cnt_T_str.RelHwPosFilt1SV_HwDeg_str.SV | AUTOCNTRTYPE_Str* | -3200 | 3200 |

|  | AutoCntr_Cnt_T_str.FiltPinTrq_HwNm_f32 | AUTOCNTRTYPE_Str* | 0 | 20 |

|  | OffsetRelHwPos_HwDeg_T_f32 | float32 | -1600 | 1600 |

|  | RelHwPos_HwDeg_T_f32 | float32 | -1600 | 1600 |

| Return Value | AutoCntrHwPos_HwDeg_T_f32 | float32 | -3200 | 3200 |
