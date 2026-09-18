---
title: "Electric Power Consumption Management — Integration manual: ElePwr_Integration_Manual"
description: "Integration manual for Electric Power Consumption Management (converted)."
---

# Electric Power Consumption Management — Integration manual: ElePwr_Integration_Manual

> Source: `ElePwr/doc/ElePwr_Integration_Manual.docx` (39,606 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual –ElePwr

Table of Contents

1	Dependencies	2

1.1	SWCs	2

1.2	Global Functions(Non RTE) to be provided to Integration Project	2

2	Configuration	3

2.1	Build Time Config	3

2.2	Configuration Files to be provided by Integration Project	3

2.2.1	Da Vinci Parameter Configuration Changes	3

2.2.2	DaVinci Interrupt Configuration Changes	3

2.2.3	Manual Configuration Changes	3

3	Integration	4

3.1	Required Global Data Inputs	4

3.2	Required Global Data Outputs	4

3.3	Specific Include Path present	4

4	Runnable Scheduling	5

5	Memory Mapping	6

5.1	Mapping	6

5.2	Usage	6

5.3	Non  RTE NvM Blocks	6

5.4	RTE NvM Blocks	6

6	Compiler Settings	6

6.1	Preprocessor MACRO	6

6.2	Optimization Settings	6

7	Revision Control Log	7

# Dependencies

## SWCs

Note : Referencing the external components should be avoided in most cases. Only in unavoidable circumstance external components should be refered. Developer should track the references.

## Global Functions(Non RTE) to be provided to Integration Project

< None>

# Configuration

## Build Time Config

## Configuration Files to be provided by Integration Project

Ap_ElePwr_Cfg.h for checkpoint enable

### Da Vinci Parameter Configuration Changes

### DaVinci Interrupt Configuration Changes

### Manual Configuration Changes

# Integration

## Required Global Data Inputs

MtrCurrDax_Amp_f32

MtrCurrQax_Amp_f32

MtrVoltDax_Volt_f32

MtrVoltQax_Volt_f32

Vecu_Volt_f32

## Required Global Data Outputs

ElectricPower_Watt_f32

SupplyCurrent_Amp_f32

## Specific Include Path present

No

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

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log


**Table 1 (from source document):**


| Module | Required Feature |

| <Name of SWC> | <Addition of global data, function*. |


**Table 2 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 3 (from source document):**


| Parameter | Notes | SWC |

| <None> |  |  |


**Table 4 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| <None> |  |  |  |


**Table 5 (from source document):**


| Constant | Notes | SWC |

| <None> |  |  |


**Table 6 (from source document):**


| Init | Scheduling Requirements | Trigger |

|  |  |  |


**Table 7 (from source document):**


| Runnable | Scheduling Requirements | Trigger |

| ElePwr_Per1 | triggered on TimingEvent | 10ms |


**Table 8 (from source document):**


| Memory Section | Contents | Notes |

| ELEPWR_START_SEC_VAR_CLEARED_32 |  |  |
