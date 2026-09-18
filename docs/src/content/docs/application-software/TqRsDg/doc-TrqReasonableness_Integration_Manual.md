---
title: "Torque Reasonableness Diagnostics — Integration manual: TrqReasonableness_Integration_Manual"
description: "Integration manual for Torque Reasonableness Diagnostics (converted)."
---

# Torque Reasonableness Diagnostics — Integration manual: TrqReasonableness_Integration_Manual

> Source: `TqRsDg/doc/TrqReasonableness_Integration_Manual.docx` (78,245 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Integration Manual

For

Torque Reasonableness Diagnostic

VERSION: 4.0

DATE: 05-Aug-2016

Prepared By:

Software Group,

Nexteer Automotive,

Saginaw, MI, USA

Location: The official version of this document is stored in the Nexteer Configuration Management System.

Revision History

Table of Contents

1	Abbrevations And Acronyms	4

2	References	5

3	Dependencies	6

3.1	SWCs	6

3.2	Global Functions(Non RTE) to be provided to Integration Project	6

4	Configuration REQUIREMeNTS	7

4.1	Build Time Config	7

4.2	Configuration Files to be provided by Integration Project	7

4.3	Da Vinci Parameter Configuration Changes	7

4.4	DaVinci Interrupt Configuration Changes	7

4.5	Manual Configuration Changes	7

5	Integration  DATAFLOW REQUIREMENTS	8

5.1	Required Global Data Inputs	8

5.2	Required Global Data Outputs	8

5.3	Specific Include Path present	8

6	Runnable Scheduling	9

7	Memory Map REQUIREMENTS	10

7.1	Mapping	10

7.2	Usage	10

7.3	NvM Blocks	10

8	Compiler Settings	11

8.1	Preprocessor MACRO	11

8.2	Optimization Settings	11

9	Appendix	12

# Abbrevations And Acronyms

# References

This section lists the title & version of all the documents that are referred for development of this document

# Dependencies

## SWCs

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

None

# Configuration REQUIREMeNTS

## Build Time Config

## Configuration Files to be provided by Integration Project

<Configuration file that will generated from this components that will require Da Vinci Config generation or manual generation. Describe each parameter >

## Da Vinci Parameter Configuration Changes

## DaVinci Interrupt Configuration Changes

## Manual Configuration Changes

# Integration  DATAFLOW REQUIREMENTS

## Required Global Data Inputs

CorrMtrPosElec_Rev_ f32

EstKe_VpRadpS_ f32

EstR_Ohm_ f32

MRFMtrVel_MtrRadpS_ f32

MtrCurrDaxRef_Amp_ f32

MtrCurrQaxFinalRef_Amp_ f32

MtrVoltDax_Volt_ f32

MtrVoltQax_Volt_ f32

OutputRampMult_Uls_ f32

TrqLimitMin_MtrNm_ f32

## Required Global Data Outputs

MtrCurrIdptSig_Cnt_u08

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

.

# Memory Map REQUIREMENTS

## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

Table 1: ARM Cortex R4 Memory Usage

## NvM Blocks

None

# Compiler Settings

## Preprocessor MACRO

N/A

## Optimization Settings

N/A

# Appendix

N/A


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial version | Selva | 1.0 | 10-Apr-13 |

| 2 | Updated for the new torque reasonableness | Selva | 2.0 | 23-Nov-13 |

| 3 | Updated for new output (v5) of the FDD | Selva | 3.0 | 25-Mar-15 |

| 4 | Updated to version 6 of FDD and to new template | SB | 4.0 | 05-Aug-16 |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |

|  | <ADD  more to the table if applicable> |

|  |  |

|  |  |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| <1> | <MDD Guidelines> | Proces release 04.02.01 |

| <2> | <Software Naming Conventions> | Proces release 04.02.01 |

| <3> | <Coding standards> | Proces release 04.02.01 |

| <4> | FDD – SF31_CurrentReasonablenessDiagnostic | 006 |

|  | <Add if more available> |  |


**Table 4 (from source document):**


| Module | Required Feature |

| None |  |


**Table 5 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 6 (from source document):**


| Parameter | Notes | SWC |

| None |  |  |


**Table 7 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| None |  |  |  |


**Table 8 (from source document):**


| Constant | Notes | SWC |

| None |  |  |
