---
title: "Steering Power Assist Control — Integration manual: Assist_Integration_Manual"
description: "Integration manual for Steering Power Assist Control (converted)."
---

# Steering Power Assist Control — Integration manual: Assist_Integration_Manual

> Source: `Assist/doc/Assist_Integration_Manual.docx` (27,182 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual --

# Dependencies

# Configuration

## Build Time Config

## Generator Config

The  module parameter description file and generator templates are located in the “generate” folder.  The generation scheme at this time relies on the ARTT generation framework developed by BMW.  Following are the recommended steps to integrate the provided generation templates and parameter description with Davinci Configurator:

Copy the “Artt/artt” framework folder into the “Generators” directory (if not already present)

Execute the “Integrate.bat” script from the Tools directory of this component to perform the necessary integration steps:

The script creates the required directories in the integration project, “Generators/Artt/” and “Generators/Components/_Schemes//bswmd”

The script then copies the required files from the CBD generate directory into the new directories.

If this is the first time integration, then perform the Davinci Configurator 3rd party component integration procedure.

## Rte Config

The SWC description included with this component in the “autosar” folder describes only the static portion of the SWC.  A partial SWC description describing the configurable part of the component interface is generated into the _ _Cfg.arxml file.  This description must be imported into the Rte configuration tool (Developer) using the “Merge Object” option to merge the static SWC description with the generated partial SWC description file.

# Runnable Scheduling

This section specifies the required runnable scheduling.

# Memory Mapping

## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

Table 1: ARM Cortex R4 Memory UsageRevision Control Log


**Table 1 (from source document):**


| Module | Required Feature |

| Rte | Port and runnable mapping. |

| WdgM | CheckpointReached() API |


**Table 2 (from source document):**


| Constant | Notes | SWC |

| None |  |  |


**Table 3 (from source document):**


| Constant | Notes | SWC |

| AssistGeneral | General module configuration.  See Assist technical reference for details. | Assist |


**Table 4 (from source document):**


| Runnable | Scheduling Requirements | Privileged Mode | Trigger |

| _Per1() | Scheduled per integration project requirements | Not Required | 2ms |


**Table 5 (from source document):**


| Constant | Notes |

| ASSIST_START_SEC_VAR_CLEARED_16 |  |


**Table 6 (from source document):**


| Feature | RAM | ROM |

| Full SWC |  |  |


**Table 7 (from source document):**


| Item # | Rev # | Change Description | Date | Author Initials |

| 1 | 1 | Initial version |  | JJW |

|  |  |  |  |  |
