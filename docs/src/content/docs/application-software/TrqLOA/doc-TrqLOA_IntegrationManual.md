---
title: "Torque Loss-of-Assist Handling — Integration manual: TrqLOA_IntegrationManual"
description: "Integration manual for Torque Loss-of-Assist Handling (converted)."
---

# Torque Loss-of-Assist Handling — Integration manual: TrqLOA_IntegrationManual

> Source: `TrqLOA/doc/TrqLOA_IntegrationManual.docx` (80,968 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Integration Manual

For

Torque Loss of Assist Function

VERSION: .0

DATE: 27-FEB-2015

Prepared By:

Spandana Balani

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

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

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

MotAgLoaMtgtnEn_Cnt_lgc

MtrVelCRF_MtrRadpS_f32

VehicleSpeedValid_Cnt_lgc

VehicleSpeed_Kph_f32

## Required Global Data Outputs

TrqLOAAvail_Cnt_lgc

TrqLOACmd_MtrNm_f32

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

## Non  RTE NvM Blocks

Note : Size of the NVM block if configured in developer

## RTE NvM Blocks

Note : Size of the NVM block if configured in developer

# Compiler Settings

## Preprocessor MACRO

None

## Optimization Settings

None

# Appendix

<This section is for appendix>


**Table 1 (from source document):**


| Rev # | Change Description | Date | Author |

| 1 | Initial version | 27-Feb-15 | SB |

|  |  |  |  |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |

|  | <ADD  more to the table if applicable> |

|  |  |

|  |  |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| 1 | FDD SF48A Torque Loss of Assist Function | .0.0 |


**Table 4 (from source document):**


| Module | Required Feature |

| None | <Addition of global data, function>*. |


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
