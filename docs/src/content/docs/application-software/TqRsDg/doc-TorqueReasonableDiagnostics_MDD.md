---
title: "Torque Reasonableness Diagnostics — Model Design Document: TorqueReasonableDiagnostics_MDD"
description: "Model Design Document for Torque Reasonableness Diagnostics (converted)."
---

# Torque Reasonableness Diagnostics — Model Design Document: TorqueReasonableDiagnostics_MDD

> Source: `TqRsDg/doc/TorqueReasonableDiagnostics_MDD.docx` (2,292,979 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

Torque Reasonableness Diagnostic

Aug 05, 2016

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

Spandana Balani,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	TqRsDg  & High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of TqRsDg	5

2.2	Data Flow Diagram	5

2.2.1	Module level DFD	5

2.2.2	Sub-Module level DFD	5

2.3	Component diagram	5

2.4	Variable Data Dictionary	5

2.4.1	User defined ‘typedef’ definition/declaration	5

2.4.2	Variable definition for enumerated types	5

2.5	Constant Data Dictionary	6

2.5.1	Program Constants	6

2.5.2	Module Specific Lookup Tables	6

2.6	Software Module Implementation	6

2.6.1	Sub-Module Functions	6

2.6.2	Interrupt Service Routines	7

2.6.3	_SCOMM () Functions	7

2.6.4	Module Internal (Local) Functions	8

2.6.5	Transition Functions	8

3	Known Limitations with Design	9

4	UNIT TEST CONSIDERATION	10

Appendix A	Abbreviations and Acronyms	11

Appendix B	Glossary	12

Appendix C	References	13

# TqRsDg  & High-Level Description

The Torque Reasonableness Diagnostic compares the commanded electromagnetic motor torque (calculated from the commanded Iq and Id currents) to the measured electromagnetic torque (calculated from the measured Iq and Id currents) and sets a diagnostic flag when the error is outside of calibration boundaries for calibration time periods. This diagnostic is intended to trip due to a variety of possible errors within the closed loop control of the motor control, including but not exclusive to certain current measurement errors and output drive errors.

# Design details of software module

## Graphical representation of TqRsDg

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

The filter constants were derived from the requirements in SF-09 in conjunction with the following filter analyses.  Note that the upper frequency limits defined in the requirements for some values were not achievable.  The data dictionary reflects the limits of both the requirements and the software limitations.

#### Global Constants

### Module Specific Lookup Tables

None

## Software Module Implementation

<The detailed design of the function is provided in the FDD. The detail design shall only be add to the MDD when it is not provided in the FDD or the FDD is not adequate and clarification is needed.>

### Sub-Module Functions

#### Initialization sub-module TqRsDg_Init1()

#### Design Rationale

Init block is missing in the design. Filter initializations are done here.

#### Store Module Inputs to Local copies

None

#### (Processing of function)………

LPF_Init_f32_m(D_ZERO_ULS_F32, k_CurrDiagPrimLPFKn_Hz_f32, D_2MS_SEC_F32, &TqRsDg_AlpaCurrDiagPrimLPF_M_Str)

LPF_Init_f32_m(D_ZERO_ULS_F32, k_CurrDiagPrimLPFKn_Hz_f32, D_2MS_SEC_F32, &TqRsDg_BetaCurrDiagPrimLPF_M_Str)

LPF_Init_f32_m(D_ZERO_ULS_F32, k_CurrDiagSecLPFKn_Hz_f32, D_2MS_SEC_F32, &TqRsDg_AlpaCurrDiagSecLPF_M_Str)

LPF_Init_f32_m(D_ZERO_ULS_F32, k_CurrDiagSecLPFKn_Hz_f32, D_2MS_SEC_F32, &TqRsDg_BetaCurrDiagSecLPF_M_Str)

#### Store Local copy of outputs into Module Outputs

None

#### Periodic sub-module TqRsDg_Per1()

Refer ‘SF-31 Current Reasonableness Diagnostic’ block in the Simulink model.

#### Design Rationale

None

#### Store Module Inputs to Local copies

CorrMtrPosElec_Rev_T_f32    = Rte_IRead_TqRsDg_Per1_CorrMtrPosElec_Rev_f32();

EstKe_VpRadpS_T_f32         = Rte_IRead_TqRsDg_Per1_EstKe_VpRadpS_f32();

EstR_Ohm_T_f32              = Rte_IRead_TqRsDg_Per1_EstR_Ohm_f32();

MRFMtrVel_MtrRadpS_T_f32    = Rte_IRead_TqRsDg_Per1_MRFMtrVel_MtrRadpS_f32();

MtrCurrDaxRef_Amp_T_f32     = Rte_IRead_TqRsDg_Per1_MtrCurrDaxRef_Amp_f32();

MtrCurrQaxFinalRef_Amp_T_f32 = Rte_IRead_TqRsDg_Per1_MtrCurrQaxFinalRef_Amp_f32();

MtrVoltDax_Volt_T_f32       = Rte_IRead_TqRsDg_Per1_MtrVoltDax_Volt_f32();

MtrVoltQax_Volt_T_f32       = Rte_IRead_TqRsDg_Per1_MtrVoltQax_Volt_f32();

OutputRampMult_Uls_T_f32    = Rte_IRead_TqRsDg_Per1_OutputRampMult_Uls_f32();

TrqLimitMin_MtrNm_T_f32     = Rte_IRead_TqRsDg_Per1_TrqLimitMin_MtrNm_f32();

#### (Processing of function)………

Refer ‘SF-31 Current Reasonableness Diagnostic ‘ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Rte_IWrite_TqRsDg_Per1_MtrCurrIdptSig_Cnt_u08(MtrCurrIdptSig_Cnt_T_u08)

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

Init block is missing in the design.

Design need to be updated to use the latest filter blocks for KUpdate and OpUpdate functions.

# UNIT TEST CONSIDERATION

INLINE functions defined in “GlobalMacro.h” are not unit tested

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

| 1 | Initial Version | Selva | 1.0 | 6-Nov-12 |

| 2 | Updated to version to SF-31 version 2 | Selva | 2.0 | 23-Feb-13 |

| 3 | Anomaly fix for A_4644 | Srikanth | 3.0 | 25-Mar-13 |

| 4 | Fixes for Unit test findings | Srikanth | 4.0 | 15-Apr-13 |

| 5 | Anomaly fix for 4931 | OT | 5.0 | 30-Apr-13 |

| 6 | Updated for V3 SF31   (completely new) | Selva | 6.0 | 27-Nov-13 |

| 7 | Updated to SF-31 version 4 | VT | 7.0 | 08-Jan-14 |

| 8 | Updated to SF31 v5 | Selva | 8.0 | 23-Mar-15 |

| 9 | Updated to SF13A FDD version 6.0.0 and to new template | SB | 9.0 | 05-Aug-16 |


**Table 2 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_BIT0_ULS_U8 | Uint8 | Cnt | 1 |

| D_BIT1_ULS_U8 | Uint8 | Cnt | 2 |

| D_SQRT3OVR2_ULS_F32 | Float32 | Uls | 0.866025403784 |


**Table 3 (from source document):**


| Constant Name |

| D_ZERO_CNT_U8 |

| D_2PI_ULS_F32 |

| D_2MS_SEC_F32 |

| D_ONE_ULS_F32 |

| D_ZERO_CNT_U16 |

| D_ZERO_ULS_F32 |

| D_ONE_CNT_U8 |


**Table 4 (from source document):**


| Abbreviation or Acronym | Description |

|  |  |

|  |  |


**Table 5 (from source document):**


| Term | Definition | Source |

| MDD | Module Design Document |  |

| DFD | Data Flow Diagram |  |


**Table 6 (from source document):**


| Ref. # | Title | Version |

| 1 | AUTOSAR Specification of Memory Mapping (Link:AUTOSAR_SWS_MemoryMapping.pdf) | v1.3.0 R4.0 Rev 2 |

| 2 | MDD Guideline | Process release 04.02.01 |

| 3 | Software Naming Conventions.doc | Process release 04.02.01 |

| 4 | Software Design and Coding Standards.doc | Process release 04.02.01 |

| 5 | FDD - SF31_CurrentReasonablenessDiagnostic | 006 |
