---
title: "Motor Control (Current Mode) — Integration manual: MtrCntrl_Integration_Manual"
description: "Integration manual for Motor Control (Current Mode) (converted)."
---

# Motor Control (Current Mode) — Integration manual: MtrCntrl_Integration_Manual

> Source: `MtrCtrl_CM/doc/MtrCntrl_Integration_Manual.docx` (82,985 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

Integration Manual

For

MtrCntrl

VERSION: 5.0

DATE: July-25-2016

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

PICurrCntrl_Per1()

TrqCogCancRefPer1()

# Configuration REQUIREMeNTS

## Build Time Config

## Configuration Files to be provided by Integration Project

MtrCtrl_Cfg.h

*Refer the template file MtrCtrl_Cfg_Template.h

## Da Vinci Parameter Configuration Changes

## DaVinci Interrupt Configuration Changes

## Manual Configuration Changes

# Integration  DATAFLOW REQUIREMENTS

## Required Global Data Inputs

The global symbols mapping done in MtrCtrl_Cfg.h.

## Required Global Data Outputs

The global symbols mapping done in MtrCtrl_Cfg.h.

## Specific Include Path present

Yes

# Runnable Scheduling

This section specifies the required runnable scheduling.

*Note: In motor control ISR include Ap_MtrCtrl.h instead of CDD_Func.h

Proper Initialization of input signals should occur before running each function for the first time.  (CurrParamComp_Init).

# Memory Map REQUIREMENTS

## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

Table : ARM Cortex R4 Memory Usage

## NvM Blocks

# Compiler Settings

## Preprocessor MACRO

None

## Optimization Settings

Set optimization level greater than 3 for PICurrentCntrl and TrqCanc functions.

# Appendix

None


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial version | Selva | 1 | 25-Mar-13 |

| 2 | Updated  TrqCanc_Init in RTE Runnables and size of the NVM block CogTrqCal  is changed from 512 to 521 | Selva | 2 | 21-Oct-13 |

| 3 | Added new NVM block “Rte_Pim_CogTrqRplComp” | Selva | 3 | 23-Oct-13 |

| 4 | Added new scheduling requirement for PICurrcntrl Initialisation | Selva | 4 | 5-Mar-15 |

| 5 | Updated per design rev. 19 | Rijvi | 5 | 25-July-2016 |


**Table 2 (from source document):**


| Abbreviation | Description |

| DFD | Design functional diagram |

| MDD | Module design Document |

|  | <ADD  more to the table if applicable> |

|  |  |

|  |  |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| 1 | MDD Guidelines | Process 04.02.01 |

| 2 | Software Naming Conventions | Process 04.02.01 |

| 3 | Coding standards | Process 04.02.01 |

| 4 | FDD | Process 04.02.01 |

|  | <Add if more available> |  |


**Table 4 (from source document):**


| Module | Required Feature |

| None | <Addition of global data, function>*. |


**Table 5 (from source document):**


| Modules | Notes |  |

| PICurrentCntrl<br/>TrqCanc | Optimization level greater than 3 |  |


**Table 6 (from source document):**


| Parameter | Notes | SWC |

| <Configurator  Changes for parameters> |  |  |


**Table 7 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| <Configurator  Changes for  Interrupts> |  |  |  |


**Table 8 (from source document):**


| Constant | Notes | SWC |

| None |  |  |
