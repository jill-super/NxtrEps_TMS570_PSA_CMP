---
title: "Compliance Error Handling — Integration manual: ComplErr_Integration_Manual"
description: "Integration manual for Compliance Error Handling (converted)."
---

# Compliance Error Handling — Integration manual: ComplErr_Integration_Manual

> Source: `ComplErr/doc/ComplErr_Integration_Manual.docx` (33,801 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual –ComplErr

Table of Contents

1	Integration Manual –ComplErr	1

1	Dependencies	2

1.1	SWCs	2

1.2	Global Functions (Non RTE) to be provided to Integration Project	2

1.2.1	ComplErr_Per1()	2

2	Configuration	2

2.1	Build Time Config	2

2.2	Configuration Files to be provided by Integration Project	2

2.2.1	Da Vinci Parameter Configuration Changes	2

2.2.2	DaVinci Interrupt Configuration Changes	2

2.2.3	Manual Configuration Changes	2

3	Integration	3

3.1	Required Global Data Inputs	3

3.2	Required Global Data Outputs	3

3.3	Specific Include Path present	3

4	Runnable Scheduling	4

5	Memory Mapping	5

5.1	Mapping	5

5.2	Usage	5

5.3	Non  RTE NvM Blocks	5

5.4	RTE NvM Blocks	5

6	Compiler Settings	5

6.1	Preprocessor MACRO	5

6.2	Optimization Settings	5

7	Revision Control Log	6

# Dependencies

## SWCs

Note: Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be referred. Developer should track the references.

## Global Functions (Non RTE) to be provided to Integration Project

### ComplErr_Per1()

# Configuration

## Build Time Config

## Configuration Files to be provided by Integration Project

<Configuration file that will be generated from this components that will require Da Vinci Config generation or manual generation. Describe each parameter >

### Da Vinci Parameter Configuration Changes

### DaVinci Interrupt Configuration Changes

### Manual Configuration Changes

# Integration

## Required Global Data Inputs

None

## Required Global Data Outputs

None

## Specific Include Path present

None

# Runnable Scheduling

This section specifies the required runnable scheduling.

# Memory Mapping

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

# Revision Control Log


**Table 1 (from source document):**


| Module | Required Feature |

| None |  |


**Table 2 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 3 (from source document):**


| Parameter | Notes | SWC |

| None |  |  |


**Table 4 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| None |  |  |  |


**Table 5 (from source document):**


| Constant | Notes | SWC |

| None |  |  |


**Table 6 (from source document):**


| Runnable | Scheduling Requirements | Trigger |

| ComplErr_Per1 | None | RTE(2ms) |


**Table 7 (from source document):**


| Memory Section | Contents | Notes |

| RTE_START_SEC_AP_COMPLERR_APPL_CODE |  |  |

|  |  |  |

|  |  |  |

|  |  |  |


**Table 8 (from source document):**


| Feature | RAM | ROM |

| N/A |  |  |
