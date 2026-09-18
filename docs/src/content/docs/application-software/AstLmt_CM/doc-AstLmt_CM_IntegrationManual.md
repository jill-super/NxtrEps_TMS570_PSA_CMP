---
title: "Assist Summation Limiter (Current Mode) — Integration manual: AstLmt_CM_IntegrationManual"
description: "Integration manual for Assist Summation Limiter (Current Mode) (converted)."
---

# Assist Summation Limiter (Current Mode) — Integration manual: AstLmt_CM_IntegrationManual

> Source: `AstLmt_CM/doc/AstLmt_CM_IntegrationManual.docx` (43,861 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual –AstLmt

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

None

# Configuration

## Build Time Config

## Configuration Files to be provided by Integration Project

### Da Vinci Parameter Configuration Changes

### DaVinci Interrupt Configuration Changes

### Manual Configuration Changes

# Integration

## Required Global Data Inputs

## Required Global Data Outputs

## Used for TrqReasonable dianostics

## Specific Include Path present

No

# Runnable Scheduling

This section specifies the required runnable scheduling.

.

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

None.

# Revision Control Log


**Table 1 (from source document):**


| Module | Required Feature |

| None |  |


**Table 2 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 3 (from source document):**


| Parameter | Notes | SWC |

|  |  |  |


**Table 4 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| None |  |  |  |


**Table 5 (from source document):**


| Constant | Notes | SWC |

| None |  |  |


**Table 6 (from source document):**


| AssistCmd_MtrNm_f32 |

| AssistEOTDamping_MtrNm_f32 |

| AssistEOTGain_Uls_f32 |

| AssistEOTLimit_MtrNm_f32 |

| AssistStallLimit_MtrNm_f32 |

| AssistVehSpdLimit_MtrNm_f32 |

| CombinedDamping_MtrNm_f32 |

| DefeatLimitService_Cnt_lgc |

| LimitedReturn_MtrNm_f32 |

|  |

| LrnPnCtrEnable_Cnt_lgc |

| LrnPnCtrTCmd_MtrNm_f32 |

| OpTrqOvr_MtrNm_f32 |

| OutputRampMult_Uls_f32 |

|  |

| PowerLimitPerc_Uls_f32 |

| PrkAssistCmd_MtrNm_f32 |

| PullCompCmd_MtrNm_f32 |

| TSMitCommand_MtrNm_f32 |

| ThermalLimitPerc_Uls_f32 |

| ThermalLimit_MtrNm_f32 |

| VehSpd_Kph_f32 |

| WheelImbalanceCmd_MtrNm_f32 |

|  |

|  |

|  |


**Table 7 (from source document):**


| LimitPercentFiltered_Uls_f32 |

| PreLimitForStall_MtrNm_f32 |

| PreLimitTorque_MtrNm_f32 |

| SumLimTrqCmd_MtrNm_f32 |

| TrqLimitMin_MtrNm_f32 |


**Table 8 (from source document):**


| Init | Scheduling Requirements | Trigger |

| AstLmt_Init1 | Called from RTE before any call to the periodic functions | RTE init |
