---
title: "Tuning Selection Authority — Model Design Document: Tuning_Select_Authority_MDD"
description: "Model Design Document for Tuning Selection Authority (converted)."
---

# Tuning Selection Authority — Model Design Document: Tuning_Select_Authority_MDD

> Source: `TuningSelAuth/doc/Tuning_Select_Authority_MDD.docx` (101,129 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

Tuning Select Authority

May 17, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

Spandana Balani,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	TuningSelAuth  & High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of TuningSelAuth	5

2.2	Data Flow Diagram	5

2.2.1	Module level DFD	5

2.2.2	Sub-Module level DFD	5

2.3	Component diagram	5

2.4	Variable Data Dictionary	5

2.4.1	User defined ‘typedef’ definition/declaration	5

2.4.2	Variable definition for enumerated types	5

2.5	Constant Data Dictionary	5

2.5.1	Program Constants	5

2.5.2	Module Specific Lookup Tables	6

2.6	Software Module Implementation	6

2.6.1	Sub-Module Functions	6

2.6.2	Interrupt Service Routines	7

2.6.3	_SCOMM () Functions	7

2.6.4	Module Internal (Local) Functions	7

2.6.5	Transition Functions	7

3	Known Limitations with Design	8

4	UNIT TEST CONSIDERATION	9

Appendix A	Abbreviations and Acronyms	10

Appendix B	Glossary	11

Appendix C	References	12

# TuningSelAuth  & High-Level Description

This function broadcasts an authority to allow switching between calibration subsets while driving.  It compares handwheel torque and vehicle speed to calibratable thresholds and outputs either a zero or a one.

# Design details of software module

## Graphical representation of TuningSelAuth

## Data Flow Diagram

### Module level DFD

N/A

### Sub-Module level DFD

N/A

## Component diagram

N/A

## Variable Data Dictionary

### User defined ‘typedef’ definition/declaration

N/A

### Variable definition for enumerated types

N/A

## Constant Data Dictionary

### Program Constants

#### Local Constants

Refer .m file

#### Global Constants

Refer .m file

* Note: For unit testing purposes, these arrays of pointers are of size [3] and [3][5] respectively and are defined as pointers to uint16 (as opposed to pointers to tuning structures) for simplicity.

### Module Specific Lookup Tables

None

## Software Module Implementation

<The detailed design of the function is provided in the FDD. The detail design shall only be add to the MDD when it is not provided in the FDD or the FDD is not adequate and clarification is needed.>

### Sub-Module Functions

#### Initialization sub-module TuningSelAuth_Init1()

#### Design Rationale

LPF_KUpdate_f32 is used to initialize the LPF filter instead of the full LPF_Init_f32 macro as an optimization since the required initial state of the filter is 0, which is the initialized value of the RAM, so there is no need to explicitly initialize the state variables in this init function.

Store Module Inputs to Local copies

Refer to FDD

#### (Processing of function)………

Refer to FDD

#### Store Local copy of outputs into Module Outputs

Refer to FDD

#### Periodic sub-module TuningSelAuth_Per1()

Refer ‘TuningSelAuthPer1’ block in the Simulink model.

#### Design Rationale

None

#### Store Module Inputs to Local copies

Refer ‘TuningSelAuthPer1’ block in the Simulink model.

#### (Processing of function)………

Refer ‘TuningSelAuthPer1’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘TuningSelAuthPer1’ block in the Simulink model.

#### Non Periodic sub-module {_NONPer()}

None

### Interrupt Service Routines

None

### _SCOMM () Functions

None

### Module Internal (Local) Functions

None

### Transition Functions

None

# Known Limitations with Design

The FDD indicates that this module will store the EEPROM value for tuning set, however, this implementation doesn’t provide this block.  Instead, it is assumed that some other module will contain the tuning selection block.  This was done to enable programs that don’t have multiple tuning sets to just use the default “0” without having to manage an EEPROM block.

# UNIT TEST CONSIDERATION

INLINE functions defined in “GlobalMacro.h” are not unit tested.

For unit testing purposes inputs - TunPer_Ptr_Str,  TunSet_Ptr_Str are defined  as pointers to uint16 (as opposed to pointers to tuning structures) for simplicity.

For unit testing purposes, arrays of pointers  - T_TunSetSelectionTbl_Ptr_Str[],T_TunPersSelectionTbl_Ptr_Str[][] are of size [3] and [3][5] respectively and are defined as pointers to uint16 (as opposed to pointers to tuning structures) for simplicity.

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


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial MDD implementing FDD SF-23 v001 | VK | 1.0 | 03Jul12 |

| 2 | Updates to provide the switching of tuning sets and personalities | LWW | 2.0 | 03/08/12 |

| 3 | Added checkpoints and memmap software segment is updated for static variables | Selva | 3.0 | 24-Sep-12 |

| 4 | Updated trigger rate for Per1 | BWL | 4.0 | 24-Oct-12 |

| 5 | Updated per1 for tune-on-the-fly phase 1 support. | KJS | 5.0 | 30-Jul-13 |

| 6 | Updated to version 4 and 5 of FDD | SB | 6.0 | 17-May-16 |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 2 (from source document):**


| Constant Name |

| T_TunSetSelectionTbl_Ptr_Str[] * |

| T_TunPersSelectionTbl_Ptr_Str[][] * |


**Table 3 (from source document):**


| Abbreviation or Acronym | Description |

|  |  |

|  |  |


**Table 4 (from source document):**


| Term | Definition | Source |

| MDD | Module Design Document |  |

| DFD | Data Flow Diagram |  |


**Table 5 (from source document):**


| Ref. # | Title | Version |

| 1 | AUTOSAR Specification of Memory Mapping (Link:AUTOSAR_SWS_MemoryMapping.pdf) | v1.3.0 R4.0 Rev 2 |

| 2 | MDD Guideline | Process release 04.02.01 |

| 3 | Software Naming Conventions.doc | Process release 04.02.01 |

| 4 | Software Design and Coding Standards.doc | Process release 04.02.01 |

| 5 | FDD SF023A_TuningSelAuth_Design | See Synergy Subproject version |
