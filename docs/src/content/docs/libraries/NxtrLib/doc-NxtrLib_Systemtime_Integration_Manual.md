---
title: "Standard Software Library (Filters, Interpolation, Math) — Integration manual: NxtrLib_Systemtime Integration_Manual"
description: "Integration manual for Standard Software Library (Filters, Interpolation, Math) (converted)."
---

# Standard Software Library (Filters, Interpolation, Math) — Integration manual: NxtrLib_Systemtime Integration_Manual

> Source: `NxtrLib/doc/NxtrLib_Systemtime Integration_Manual.docx` (26,185 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual – NxtrLib_SystemTime

# Dependencies

# Configuration

## Build Time Config

## Generator Config

### System

# Integration

The following import steps must be completed:

Place CBD project structure to appropriate integration folder

Copy SystemTime_Cfg.h.tt into the Header folder and remove the .tt extension.

Configure the constant D_TickRate_Cnt_u32 to the appropriate Os system tick time.

# Runnable Scheduling

This section specifies the required runnable scheduling.

# Memory Mapping

## Mapping

* Each …START_SEC… constant is terminated by a …STOP_SEC… constant as specified in the AUTOSAR Memory Mapping requirements.

## Usage

Table 1: ARM Cortex R4 Memory Usage

# Revision Control Log


**Table 1 (from source document):**


| Module | Required Feature |

|  |  |


**Table 2 (from source document):**


| Constant | Notes | SWC |

|  |  |  |


**Table 3 (from source document):**


| Constant | Notes | SWC |

|  |  |  |


**Table 4 (from source document):**


| Runnable | Scheduling Requirements | Trigger |

|  |  |  |


**Table 5 (from source document):**


| Constant | Notes |

|  |  |


**Table 6 (from source document):**


| Feature | RAM | ROM |

| Full driver |  |  |


**Table 7 (from source document):**


| Item # | Rev # | Change Description | Date | Author Initials |

| 1 |  | Initial version | 26Jul13 | SAH |
