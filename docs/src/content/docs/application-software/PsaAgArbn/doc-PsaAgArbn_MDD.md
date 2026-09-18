---
title: "PSA Steering Angle Arbitration — Model Design Document: PsaAgArbn_MDD"
description: "Model Design Document for PSA Steering Angle Arbitration (converted)."
---

# PSA Steering Angle Arbitration — Model Design Document: PsaAgArbn_MDD

> Source: `PsaAgArbn/doc/PsaAgArbn_MDD.docx` (125,682 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

PsaAgArbn

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

2	PsaAgArbn & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of PsaAgArbn	6

3.2	Component diagram	6

3.3	Variable Data Dictionary	6

3.3.1	User defined ‘typedef’ definition/declaration	6

3.3.2	Variable definition for enumerated types	7

3.4	Constant Data Dictionary	7

3.4.1	Program Constants	7

3.4.2	Module Specific Lookup Tables	7

3.5	Software Module Implementation	7

3.5.1	Sub-Module Functions	7

3.5.2	Interrupt Service Routines	8

3.5.3	_SCOMM () Functions	8

3.5.4	Module Internal (Local) Functions	8

3.5.5	Transition Functions	10

4	Known Limitations with Design	11

5	UNIT TEST CONSIDERATION	12

# Introduction

## Purpose

The purpose of this document is to create Module Design Document for CF039A PsaAgArbn.

# PsaAgArbn & High-Level Description

This function produces a readjusted steering column angle available at wakeup .The EPS produces and emits the relative column angle. The ESC estimates the offset, associated with an offset accuracy and emits them. If the offset determined by the ESC is better than the one already used by the EPS, the EPS will replace its effective offset by the new offset coming from ESC.

# Design details of software module

Refer FDD (Ref [5])

## Graphical representation of PsaAgArbn

## Component diagram

Refer FDD (Ref [5])

## Variable Data Dictionary

Refer Variable Dictionary sheet of component’s Data Dictionary.

### User defined ‘typedef’ definition/declaration

None

### Variable definition for enumerated types

## Constant Data Dictionary

### Program Constants

#### Local Constants

#### Global Constants

None

### Module Specific Lookup Tables

None

## Software Module Implementation

### Sub-Module Functions

#### Initialization: PsaAgArbn_Init1

Refer FDD Design (Simulink model)

#### Periodic: PsaAgArbn_Per1

Refer FDD Design (Simulink model)

#### Non Periodic sub-module {_NONPer()}

None

### Interrupt Service Routines

None

### _SCOMM () Functions

#### PsaAgArbn_SCom_PsaAaCmd

### Module Internal (Local) Functions

#### ESCOffsMngr

#### OffsConsistencyFltMngt

#### SnsrMon

#### RecommendedState

#### GenRawAbsltHwPosnSignals

#### VehCondChk

#### SwitchOffs

### Transition Functions

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

None

#### Abbreviations and Acronyms

#### Glossary

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

#### References


**Table 1 (from source document):**


| Description | Author | Version | Date |

| Initial Version<br/>of CF039A PsaAgArbn | JK | 1.0 | 03/15/17 |

| Updated to FDD v1.2.0 | JK | 2.0 | 04/05/2017 |

| Updated to FDD v1.3.0 | ML | 3.0 | 04/26/2017 |

|  |  |  |  |


**Table 2 (from source document):**


| Enumerated data type name | Enumerators | Value |

|  | INIT | 0U |

|  | POWERCUT | 1U |

|  | PROCESSING | 2U |

|  | DEFECT | 3U |

|  | MODININ | 0U |

|  | MODREL | 1U |

|  | MODABSLT | 2U |

|  | MODFAIL | 3U |


**Table 3 (from source document):**


| Constant Name | Resolution | Units | Value |

| Refer .m file for constants |  |  |  |


**Table 4 (from source document):**


| Function Name | PsaAgArbn_SCom_PsaAaCmd | Type | Min | Max |

| Arguments Passed | DiagCmd_Cnt_enum | PsaAgArbnDiagCmdReq_Enum | 0 | 2 |

| Return Value | N/A |  |  |  |


**Table 5 (from source document):**


| Function Name | ESCOffsMngr | Type | Min | Max |

| Arguments Passed | EscDataVldFromSerlCom_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | EscOffsFromSerlCom_HwDeg_T_f32 | float32 | -1630.0F | 1630.0F |

|  | EscPrecisionFromSerlCom_HwDeg_T_f32 | float32 | 0.0F | 29.0F |

| Return Value | N/A |  |  |  |


**Table 6 (from source document):**


| Function Name | OffsConsistencyFltMngt | Type | Min | Max |

| Arguments Passed |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

| Return Value | N/A |  |  |  |


**Table 7 (from source document):**


| Function Name | SnsrMon | Type | Min | Max |

| Arguments Passed | CumMechMtrPosStatus_Cnt_T_u08 | uint8 | 0U | 255U |

|  | EscOffsEna_Cnt_T_lgc | boolean | FALSE | TRUE |

|  | AlignedCumMechMtrPosStatus_Cnt_T_u08 | uint8 | 0U | 255U |

|  | AlignedRelHwPos_HwDeg_T_f32 | float32 | -10125.0F | 10125.0F |

|  | RelHwPos_HwDeg_T_f32 | float32 | -3200.0F | 3200.0F |

| Return Value | N/A |  |  |  |


**Table 8 (from source document):**


|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |
