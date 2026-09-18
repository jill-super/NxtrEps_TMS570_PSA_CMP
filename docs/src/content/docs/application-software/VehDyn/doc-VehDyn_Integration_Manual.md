---
title: "Vehicle Dynamics Interface — Integration manual: VehDyn_Integration_Manual"
description: "Integration manual for Vehicle Dynamics Interface (converted)."
---

# Vehicle Dynamics Interface — Integration manual: VehDyn_Integration_Manual

> Source: `VehDyn/doc/VehDyn_Integration_Manual.docx` (78,788 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Integration Manual

For

VehDyn

VERSION: 7.0

DATE: 08-MAR-2018

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

Ap_VehDyn_Cfg.h   (generated using Ap_VehDyn_Cfg.h.tt)

## Da Vinci Parameter Configuration Changes

## DaVinci Interrupt Configuration Changes

## Manual Configuration Changes

# Integration  DATAFLOW REQUIREMENTS

## Required Global Data Inputs

Refer FDD

## Required Global Data Outputs

Refer FDD

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

# Memory Map REQUIREMENTS

## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

Table 1: ARM Cortex R4 Memory Usage

## NvM Blocks

None

# Compiler Settings

## Preprocessor MACRO

None

## Optimization Settings

None

# Appendix


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial version | KMC | 1.0 | 19-Aug-13 |

| 2 | Updated per SF42 - VCDMotPos rev 002 | SB | 2.0 | 21-Aug-14 |

| 3 | Updated to SF42 – VCDMotPos v004 | SB | 3.0 | 16-Jan-15 |

| 4 | Updated to SF42 – VCDMotPos v006 | JK | 4.0 | 13-Aug-15 |

| 5 | New MemMap section added and Input name change | SB | 5.0 | 15-Dec-15 |

| 6 | Updated to SF-42 FDD rev 7.3.0 (Fix for anomaly EA3#6247) | KK | 6.0 | 24-Feb-16 |

| 7 | Updated to FDD rev 9.0.0, new template. | Krzysztof Byrski | 7.0 | 08-Mar-2018 |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |

| FDD | Functional Design Document |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| 1 | EA4 Software Naming Conventions | 1.02 |

| 2 | Software Design and Coding Standards | 2.01 |

| 3 | SF042A_VehCentrDtmnByMotPosn_Design | 9.0.0 |


**Table 4 (from source document):**


| Module | Required Feature |

| None |  |


**Table 5 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 6 (from source document):**


| Parameter | Notes | SWC |

| VehDynGeneral/VehDynCPEnable | Enable checkpoints if needed | VehDyn |


**Table 7 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| None |  |  |  |


**Table 8 (from source document):**


| Constant | Notes | SWC |

| None |  |  |
