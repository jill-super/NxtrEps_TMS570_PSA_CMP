---
title: "Position Servo Control — Model Design Document: PosServo_MDD"
description: "Model Design Document for Position Servo Control (converted)."
---

# Position Servo Control — Model Design Document: PosServo_MDD

> Source: `PosServo/doc/PosServo_MDD.docx` (101,573 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

PosServo

February 23, 2018

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

2	PosServo & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of PosServo	6

3.2	Data Flow Diagram	6

3.2.1	Module level DFD	6

3.2.2	Sub-Module level DFD	6

3.3	Component diagram	6

3.4	Variable Data Dictionary	6

3.4.1	User defined ‘typedef’ definition/declaration	6

3.4.2	Variable definition for enumerated types	6

3.5	Constant Data Dictionary	7

3.5.1	Program Constants	7

3.5.2	Module Specific Lookup Tables	7

3.6	Software Module Implementation	7

3.6.1	Sub-Module Functions	7

3.6.2	Interrupt Service Routines	8

3.6.3	_SCOMM () Functions	8

3.6.4	Module Internal (Local) Functions	8

3.6.5	Transition Functions	9

4	Known Limitations with Design	10

5	UNIT TEST CONSIDERATION	11

Appendix A	Abbreviations and Acronyms	12

Appendix B	Glossary	13

Appendix C	References	14

# Introduction

## Purpose

Module Design Document for SF020A PosServo.

## Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance.

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.

May: indicates an optional action.

# PosServo & High-Level Description

This module provides the ability for the EPS system to track a position input command.

# Design details of software module

## Graphical representation of PosServo

## Data Flow Diagram

Refer FDD.

### Module level DFD

### Sub-Module level DFD

## Component diagram

Refer FDD.

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

#### Initialization sub-module { PosServo_Init1()}

Refer FDD.

#### Periodic sub-module {PosServo_Per1()}

Refer FDD

#### Non Periodic sub-module {_NONPer()}

None

### Interrupt Service Routines

None

### _SCOMM () Functions

None

### Module Internal (Local) Functions

#### Local Function FilterDesiredAngle

#### Local Function TransitionControl

#### Local Function PIDControl

#### Local Function OutputTorque

### Transition Functions

None

# Known Limitations with Design

INLINE functions defined are not unit tested

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

| Initial version | YY | 1 | 07-Jun-11 |

| Corrected anomaly 2371 to prevent potential overflow of intermediate D-Term calculation. | YY | 2 | 16-Jun-11 |

| Initial version for PosServo CBD | VK | 3 | 16-Dec-11 |

| Changed VehSpd_T_u12p4 to u9p7 and changed the precision for the table associated. | VK | 4 | 09-Jan-12 |

| Changed the range for hand wheel position to be +/-900 throughout and updated the software segment | VK | 5 | 02-02-12 |

| Updated to SF-20 v002 | OT | 6 | 01-Aug-12 |

| Fixed UTP Issue (typecasting bilinear interpolation overflow) | OT | 7 | 08-Aug-12 |

| Fixed more UTP issues (fixed point math overflow) | OT | 8 | 10-Aug-12 |

| Updated to SF-20 v003 | KJS | 9 | 29-Aug-12 |

| Added checkpoints and memmap software segment is updated for static variables | Selva | 10 | 21-Sep-12 |

| UTP corrections to MDD | KJS | 11 | 19-Oct-12 |

| UTP corrections to MDD | KJS | 12 | 19-Oct-12 |

| Updated to SF v004 | SP | 13 | 15-Mar-13 |

| Updated to FDD ver 005 | Jared | 14 | 10-May-13 |

| Updated to FDD ver 006, new template | Krzysztof Byrski | 15 | 23-Feb-2018 |


**Table 2 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |


**Table 3 (from source document):**


| Enum  Name | Element Name | Value |

| None |  |  |


**Table 4 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_2MS_MS_F32 | Single Precision Float | Ms | 2 |

| D_DGAINMAX_MTRNM_F32 | Single Precision Float | MtrNm | 255 |

| D_DGAINMIN_MTRNM_F32 | Single Precision Float | MtrNm | -255 |

| D_EXECRATE_HZ_F32 | Single Precision Float | Hz | 500 |

| D_POSSERVOMAXRAMP_ULS_F32 | Single Precision Float | Uls | 1 |

| D_POSSERVOMINRAMP_ULS_F32 | Single Precision Float | Uls | 0 |

| D_RAMPCMPL_ULS_U6P10 | 0.0009765625 | Uls | 0 |

| D_ZERO_HWDEG_F32 | Single Precision Float | HwDeg | 0 |

| D_ZERO_MTRNMPHWDEGS_U12P4 | 0.0625 | MtrNmpHwDegS | 0 |

| D_ZERO_MTRNM_F32 | Single Precision Float | MtrNm | 0 |


**Table 5 (from source document):**


| Constant Name |

| D_2MS_SEC_F32 |

| D_ZERO_ULS_F32 |


**Table 6 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 7 (from source document):**


| Function Name | FilterDesiredAngle | Type | Min | Max |

| Arguments Passed | RampCmpl_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | PosSrvoHwAngle_HwDeg_T_f32 | float32 | -1600 | 1600 |

|  | HandwheelPosition_HwDeg_T_f32 | float32 | -1600 | 1600 |

|  | PosSrvoEnable_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | VehicleSpeed_Kph_T_u9p7 | uint16 | 0 | 65408 |

| Return Value | FildTarHwAg_HwDeg_T_f32 | float32 | -1600 | 1600 |


**Table 8 (from source document):**


| Function Name | TransitionControl | Type | Min | Max |

| Arguments Passed | HwTorque_HwNm_T_f32 | float32 | -10 | 10 |

|  | PosSrvoEnable_Cnt_T_lgc | boolean | FALSE | TRUE |

| Return Value | PosSrvoReturnSclFct_Uls_T_f32 | float32 | 0 | 1 |

|  | PosSrvoSmoothEnable_Uls_T_f32 | float32 | 0 | 1 |

|  | RampCmpl_Cnt_T_lgc | boolean | FALSE | TRUE |
