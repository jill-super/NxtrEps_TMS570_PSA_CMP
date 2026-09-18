---
title: "Temporal Monitor (Program Flow Monitoring) — Model Design Document: Temporal_Monitor_2_MDD"
description: "Model Design Document for Temporal Monitor (Program Flow Monitoring) (converted)."
---

# Temporal Monitor (Program Flow Monitoring) — Model Design Document: Temporal_Monitor_2_MDD

> Source: `TmprlMon/doc/Temporal_Monitor_2_MDD.docx` (57,599 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module --

# High-Level Description

This module helps ensure valid execution time for the forward path.  It generates the falling edge of the monitor signal used by an external processor to determine execution time.

# Figures

## Component Diagram

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

### User defined typedef definition/declaration

This section documents any user types uniquely used for the module.

# Constant Data Dictionary

## Calibration Constants

This section lists the calibrations used by the module.  For details on calibration constants, refer to the Data Dictionary for the application.

## Program(fixed) Constants

### Embedded Constants

All embedded constants whose values are provided in Eng units will be evaluated to the equivalent counts by using the FPM_InitFixedPoint_m() macro within the #define statement.

#### Local

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

### Module specific Lookup Tables Constants

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

<None>

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

None

## Periodic Functions

### Per: _Per1

#### Design Rationale

This function generates the falling edge of the WdMonitor signal.  It must be mapped at the end of the forward path.

#### Program Flow Start

Rte_Call_TmprlMon2_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

None

#### Set WdMonitor Low

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

Rte_Call_TmprlMon2_Per1_CP1_CheckpointReached()

# Execution Requirements

## Execution Sequence of the Module

_Per1 is executed at the end of the forward path.

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

None

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| <None> | <None> |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| <None> |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| <None> |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| <None> |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| <None> |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| STD_LOW |

| STD_HIGH |


**Table 7 (from source document):**


| Constant Name | Value | Software Segment |

| <None> |  |  |


**Table 8 (from source document):**


| Data | Value |

| <None> |  |
