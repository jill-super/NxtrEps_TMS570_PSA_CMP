---
title: "Frequency Sweep Excitation (Test Support) — Model Design Document: Sweep2_MDD"
description: "Model Design Document for Frequency Sweep Excitation (Test Support) (converted)."
---

# Frequency Sweep Excitation (Test Support) — Model Design Document: Sweep2_MDD

> Source: `Sweep/doc/Sweep2_MDD.docx` (108,521 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module – Sweep2

# High-Level Description

# Figures

## Component Diagram

# Variable Data Dictionary

## Module Internal Variables

### User defined typedef definition/declaration

# Constant Data Dictionary

## Calibration Constants

## Program(fixed) Constants

### Embedded Constants

#### Local

#### Global

### Module specific Lookup Tables Constants

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

none

## Local Functions/Macros Used by this MDD only

none

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

## Initialization Functions

None

## Periodic Functions

#### Design Rationale

None

#### Store Module Inputs to Local copies Fault Recovery Functions

See below

#### Description

#### Store Local copy of outputs into Module Outputs

See above

## Shutdown Functions

None

## Interrupt Functions

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

# Execution Requirements

## Execution Sequence of the Module

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Global and Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

(Item #1)

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| InputMtrTrq_MtrNm_f32 | InputMtrTrq_MtrNm_f32 | OutputMtrTrq_MtrNm_f32 |


**Table 2 (from source document):**


| Variable Name | Datatype | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment<br/>{Data Type} |

| SweepModeEn_Cnt_M_lgc | Boolean | N/A | FALSE | TRUE |  |

| SweepConfig_Cnt_M_u16 | Uint16 | 1 | 0 | FULL |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

|  |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

|  |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_SWEEPMTRTRQ_CNT_U16 | 1 | Uint16 | 1 |


**Table 6 (from source document):**


| Constant Name |

| D_FALSE_CNT_LGC |

| D_ZERO_ULS_F32 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

|  |  |  |  |


**Table 8 (from source document):**


| Data | Value |

| InputMtrTrq_MtrNm_f32 | 0 |
