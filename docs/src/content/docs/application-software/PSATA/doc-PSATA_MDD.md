---
title: "PSA Torque Assist Handling — Model Design Document: PSATA_MDD"
description: "Model Design Document for PSA Torque Assist Handling (converted)."
---

# PSA Torque Assist Handling — Model Design Document: PSATA_MDD

> Source: `PSATA/doc/PSATA_MDD.docx` (145,742 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Module Design Document

For

CF14 PSA Torque Arbitrator

VERSION: .0

DATE: --201.

Prepared By:

Krishna Anne,

Nexteer Automotive,

Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

# Abbrevations And Acronyms

# References

This section lists the title & version of all the documents that are referred for development of this document

# PSA State Handler High-Level Description

The PSA Torque Arbitrator will be  equipped for EPS Systems with functions including Ramping and smoothing of PosServo command and Safety function. The safety function will monitor the PSA State Handler and PSA Torque Arbitrator.

# Design details of software module

## Graphical representation of PSA Torque Arbitrator

## Data Flow Diagram

Refer FDD

## Module level DFD

Refer FDD

## Sub-Module level DFD

Refer FDD

## COMPONENT FLOW DIAGRAM

Refer FDD

# Variable Data Dictionary

## User defined typedef definition/declaration

## Variable definition for enumerated types

# Constant Data Dictionary

## Program(fixed) Constants

## Embedded Constants

## Local

## Global

## Module specific Lookup Tables Constants

# Software Module Implementation

## Sub-Module Functions

## Initialization Functions

## Init: PSATA_Init1

## Design Rationale

Refer FDD

## Module Outputs

None

## Module Internal

PSATA_FilterdTrqSV_HwNm_M_Str

PSATA_LxaDiTranTi_Sec_M_f32

## PERIODIC FUNCTIONS

## Per: PSATA_per1

## Design Rationale

Design follows implemenetation in FDD.

## Store Module Inputs to Local copies

Refer FDD

## (Processing of function)………

Refer to FDD  (Block ‘PSATA_Per1’)

## Store Local copy of outputs into Module Outputs

Refer FDD.

## Interrupt Functions

None

## Serial Communication Functions

None

## Local Function/Macro Definitions

## LOCAL FUNCTION #1

## Description

Implementation of ‘TorqueArbitration’ block in ‘PSATA_Per1’. This function determines LxaPosServoCmd and APAPosSrvoCmd based on the current EPSStateForLxa and ApaState.

## LOCAL FUNCTION #2

## Description

Implementation of ‘APA Supervision’ block in ‘PSATA_Per1’. This function determines the APA output torque overlay and monitors PosSrvo for errors.

## Local Function #3

## Description

This function monitors 'State Handler' and 'PosServo' for errors. Sets 'PosSrvoNTC_Cnt_lgc'  signal accordingly.

Note: This implementation corresponds to lower half of APA NTC block.

## Local Function #4

## Description

Implementation of 'PosServoSmoothing' block. PosServoCmd changes instantly from zero when disabled to non-zero when enabled, and vice-versa. This routine calculates a scale factor for the PosServoCmd to smoothly ramp it in and out. First, it produces a linear scale factor, then feeds the linear factor into a lookup table to non-linearize it.This produces softer transitions when scale factor is near zero or near unity. The scale factor can decrease more rapidly when driver hand wheel torque is present.

## LOCAL FUNCTION #5

## Description

Implementation of 'LxASupervision' block.

## LOCAL FUNCTION #6

## Description

Implementation of ‘LxaPosSrvoCmdLimit’ block.

Calculates the limited Lxa PosServo command.

## LOCAL FUNCTION #7

## Description

Implementation of 'LxaPosSrvoSmotngFactor' block.

Calculates the Lxa PosSrvo Smoothing Factor.

## LOCAL FUNCTION #8

## Description

Implementation of LxaPosSrvoSmotng’ block.

Calculates the Lxa PosSrvo Smoothed Command.

## LOCAL FUNCTION #9

## Description

Implementation of 'LxaNTC' block.Performs Lxa fault diagnostics.

## LOCAL FUNCTION #10

## Description

Implementation of 'LxaPosSrvoSftySmotngFactor' block.

Calculates LxaPosSrvoSftySmotngFactor.

## LOCAL FUNCTION #11

## Description

Implementation of 'LxaPosSrvoSftySmotng' block.

Calculates LxaOpTrqOv.

## LOCAL FUNCTION #12

## Description

Implementation of 'SafetyTorqueArbitration' block.

Calculates OpTrqOv.

## LOCAL FUNCTION #13

## Description

Re-usable function for NTC diagnostics used in Supervision submodule.

Updates PN counter and sets NTC if necessary.

## GLObAL Function/Macro Definitions

None

## Tranisition FUNCTIONS

None

# Known Limitations With Design

# UNIT TEST CONSIDERATION

1.

FDD describes  functionality and structural breakdown of this component. Data dictionary contains all attributes of varibales and calibrations used.

# Appendix


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial Version | Sankardu Varadapureddi | 1.0 | 10-Mar-2015 |

| 2 | Updated for FDD v2.1.0 | Nick Saxton | 2.0 | 15-Jun-2016 |

| 3 | Updated for FDD v3.0.0 | Krishna Anne | 3.0 | 23-Feb-2017 |

| 4 | Updated as per UT findings | Krishna Anne | 4.0 | 08-Mar-2017 |

| 5 | Update to FDD 4.1.0 | Mateusz Bartocha | 5.0 | 20-Sep-2017 |

|  |  |  |  |  |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |

| FDD | Functional Design Document |

| CF | Customer Function |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| 1 | MDD Guidelines |  |

| 2 | Software Naming Conventions | . |

| 3 | Software Design and Coding standards | 2.1 |

| 4 | CF14 PSA State handler FDD | .0.0 |


**Table 4 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |

|  |  |  |  |  |


**Table 5 (from source document):**


| Enum  Name | Element Name | Value |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |


**Table 6 (from source document):**


| Constant Name | Resolution | Units | Value |

|  |  |  |  |

|  |  |  |  |

| D_POSSRVONTCENABLE_MTRNM_F32 | single preicision float | MTRNM | 0.0F |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

| D_FLTEPSILON_ULS_F32 | Single precision float | ULS | 0.0000001192092896F |

|  |  |  |  |

|  |  |  |  |


**Table 7 (from source document):**


| Constant Name |

| D_ZERO_CNT_U8 |

| D_ZERO_ULS_F32 |

| D_TRUE_CNT_LGC |

| D_2MS_SEC_F32 |

|  |

|  |

| D_FALSE_CNT_LGC |

| D_ONE_ULS_F32 |

|  |

|  |

|  |


**Table 8 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |
