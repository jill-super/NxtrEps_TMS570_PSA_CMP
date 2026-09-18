---
title: "TMS570 Microcontroller Diagnostics — Model Design Document: OsErrCallouts_MDD"
description: "Model Design Document for TMS570 Microcontroller Diagnostics (converted)."
---

# TMS570 Microcontroller Diagnostics — Model Design Document: OsErrCallouts_MDD

> Source: `TMS570_uDiag/doc/OsErrCallouts_MDD.docx` (139,895 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# High-Level Description

OsErrCallouts provides the error hook functions ErrorHook() and ProtectionHook() to provide diagnostic information for certain errors that result in calls to these hooks.

# Figures

## Diagram – Function Data Sharing

No Shared Data

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

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

(This is for lookup tables (arrays) with fixed values, same name as other tables)

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

RednRpdShtdn()

## Data Hiding Functions

OSErrorGetosCANError()

## Global Functions/Macros Defined by this Module

### Global Function #1

#### Design Rationale

When the error was an unhandled exception, reset with a reset cause indicating unexpected interrupt.  Currently does no handling of other errors.

#### Description

### Global Function #2

#### Design Rationale

When the protection violation was a stack fault, reset with a reset cause of STACKOVERWRITE.  For any other protection violation, reset with a reset cause of MPUVIOLATION.

#### Description

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

None

## Periodic Functions

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

None.

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

| None | None |  |

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| None |  |  |  |  |

|  |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| <None> |  |  |  |  |

|  |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| <None> |

|  |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| None |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| UNUSEDINTERRUPT |

| STACKOVERWRITE |

| MPUVIOLATION |

| osdErrSOStackOverflow |

| osdErrYOStackOverflow |

| osdErrUEUnhandledException |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| <None> |  |  |  |


**Table 8 (from source document):**


| Function Name | ErrorHook | Type | Dir. | Min | Max | UTP Tol. |

| Arguments Passed | ErrorCode | StatusType |  | N/A | N/A |  |

| Return Value | N/A |  |  |  |  |  |
