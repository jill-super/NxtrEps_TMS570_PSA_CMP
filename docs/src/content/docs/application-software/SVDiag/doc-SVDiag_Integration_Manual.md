---
title: "Motor Driver Diagnostics (Servo Drive Diagnostics) — Integration manual: SVDiag_Integration_Manual"
description: "Integration manual for Motor Driver Diagnostics (Servo Drive Diagnostics) (converted)."
---

# Motor Driver Diagnostics (Servo Drive Diagnostics) — Integration manual: SVDiag_Integration_Manual

> Source: `SVDiag/doc/SVDiag_Integration_Manual.docx` (80,819 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Integration Manual

For

Sine Voltage Generation Diagnostics (ES-49)

VERSION: 2

DATE: 02-12-2014

Prepared By:

Rijvi Ahmed,

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

Global function (except the ones that are defined in RTE modules) that is defined in this component but used by other function

# Configuration REQUIREMeNTS

## Build Time Config

## Configuration Files to be provided by Integration Project

None

## Da Vinci Parameter Configuration Changes

## DaVinci Interrupt Configuration Changes

## Manual Configuration Changes

# Integration  DATAFLOW REQUIREMENTS

## Required Global Data Inputs

ExpectedOnTimeA_Cnt_u32

ExpectedOnTimeB_Cnt_u32

ExpectedOnTimeC_Cnt_u32

LRPRCorrectedMtrPosCaptured_Rev_f32

LRPRModulationIndexCaptured_Uls_f32

LRPRPhaseadvanceCaptured_Cnt_s16

MeasuredOnTimeA_Cnt_u32

MeasuredOnTimeB_Cnt_u32

MeasuredOnTimeC_Cnt_u32

MotorVelMRFUnfiltered_MtrRadpS_f32

MtrElecMechPolarity_Cnt_s08

PDActivateTest_Cnt_lgc

MtrDrvrInitStart_Cnt_lgc

*

## Required Global Data Outputs

SVDiag_LowPhReasErrorAcc_Cnt_u16

SVDiag_HighResPhsReasDisable_u8

SVDiag_LowResPhsReasDisable_u8

SVDiag_MtrDrvInitComp_Cnt_lgc

SVDiag_GateDriveFltAcc_Cnt_u16

SVDiag_GenGateDriveFltAcc_Cnt_u16

SVDiag_OnStateFltAcc_Cnt_u16

*

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

None


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial version | VT | 1 | 03-Oct-2013 |

| 2 | Updated for FDD rev.008 and updated the template. | Rijvi | 2 | 01-Dec-2014 |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

|  |  |  |


**Table 4 (from source document):**


| Module | Required Feature |

| None | None |


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
