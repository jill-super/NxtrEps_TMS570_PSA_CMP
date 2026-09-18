---
title: "PSA Torque Assist Handling — Integration manual: PSATA_Integration Manual"
description: "Integration manual for PSA Torque Assist Handling (converted)."
---

# PSA Torque Assist Handling — Integration manual: PSATA_Integration Manual

> Source: `PSATA/doc/PSATA_Integration Manual.docx` (82,865 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Integration Manual

For

CF14 PSA Torque Arbitrator

VERSION: .0

DATE: --.

Prepared By:

,

Nexteer Automotive,

Saginaw, MI, USA

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

7.3	Non  RTE NvM Blocks	10

7.4	RTE NvM Blocks	10

8	Compiler Settings	11

8.1	Preprocessor MACRO	11

8.2	Optimization Settings	11

9	Appendix	12

# Abbrevations And Acronyms

# References

This section lists the title & version of all the documents that are referred for development of this document

# Dependencies

## SWCs

## Global Functions(Non RTE) to be provided to Integration Project

None

# Configuration REQUIREMeNTS

## Build Time Config

## Configuration Files to be provided by Integration Project

None

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

## Non  RTE NvM Blocks

## RTE NvM Blocks

# Compiler Settings

## Preprocessor MACRO

None.

## Optimization Settings

None

# Appendix


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial version | Sankardu Varadapureddi | 1.0 | 10-Mar-2015 |

| 2 | Updated for FDD v2.1.0 | Nick Saxton | 2.0 | 31-May-2016 |

| 3 | Updated for FDD v3.0.0 | Krishna Anne | 3.0 | 23-Feb-2017 |

| 4 | Updated for FDD v4.1.0 | Mateusz Bartocha | 4.0 | 20-Sep-17 |

|  |  |  |  |  |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |

|  |  |

|  |  |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| 1 | MDD Guidelines | 1.3 |

| 2 | Software Naming Conventions | 1.2 |

| 3 | Software Design and Coding Standards | 2.1 |

| 4 | FDD  - CF14 PSA Torque Arbitrator |  |

| 5 | Integration Manual Template.doc | 1.2 |


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
