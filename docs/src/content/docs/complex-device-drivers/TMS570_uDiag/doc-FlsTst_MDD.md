---
title: "TMS570 Microcontroller Diagnostics — Model Design Document: FlsTst_MDD"
description: "Model Design Document for TMS570 Microcontroller Diagnostics (converted)."
---

# TMS570 Microcontroller Diagnostics — Model Design Document: FlsTst_MDD

> Source: `TMS570_uDiag/doc/FlsTst_MDD.docx` (29,489 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module  --

# High-Level Description

This is module implements the FLASH Memory testing requirements specified in “EA3.x FDD 32 - uC Diagnostics 000D” according to the AUTOSAR “Specification of Flash Test v1.2.0 ” API definition.  This SWC is TI TMS570 target specific.

This module extends the AUTOSAR API definition by including a hardware Self Test function and including support for hardware IRQ’s.

# Figures

## Diagram – Function Data Sharing

This diagram shows all data that is shared between functions within the module.

(Note – If no data is shared between functions, the Text “No Shared Data” can be used in place of a graphic.  Also note that init functions need not be shown unless they compute non-zero data to be used by other functions in the module).

### Diagram – Function (Name)

This diagram describes the functional characteristics and data flow of a given function.

(Note – This is not mandatory, only used where a graphical representation helps explain the function.  It is left to the author’s discretion.  New headers of this level (Level 3) should be created for each function.

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

<None>

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

### Global Function #1

#### Description

(Place flowchart/design for local function)

## Local Functions/Macros Used by this MDD only

### Local Function #1

#### Description

(Place flowchart/design for local function)

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

(Note: For multiple init functions, insert new headers at the “Header 2” level – subset of “5.1 Initialization Functions” and follow the same sub-section design shown below)

### Init: _L_Init(n)

#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)

#### Module Outputs

(Initialize all module outputs in this section)

#### Module Internal

(Initialize all module internal variables in this section)

## Periodic Functions

(Note: For multiple periodic functions, insert new headers at the “Header 2” level – subset of “5.2 Periodic Functions” and follow the same sub-section design shown below)

### Per: _L_Per(n)

#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)

#### Program Flow Start

(If program flow is required by the module, the function to store the unique identifier to a temporary variable is done here – start of the function)

#### Store Module Inputs to Local copies

(If not required based on design, insert text “None”)

#### (Processing of function)………

(Breakdown the function into smaller sections to add clarity to the design).

#### Store Local copy of outputs into Module Outputs

(If not required based on design, insert text “None”)

#### Program Flow End

(If program flow is required by the module, the function to add the temporary variable to the global accumulator is done here)

## Fault Recovery Functions

(Note: For multiple functions, insert new headers at the “Header 2” level – subset of “5.3 Fault Recovery Functions” and follow the same sub-section design shown below)

### FaultRec: _L_FaultRec(n)

#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)

#### Program Flow Start

(If program flow is required by the module, the function to store the unique identifier to a temporary variable is done here – start of the function)

#### Store Module Inputs to Local copies

(If not required based on design, insert text “None”)

#### (Processing of function)………

(Breakdown the function into smaller sections to add clarity to the design).

#### Store Local copy of outputs into Module Outputs

(If not required based on design, insert text “None”)

#### Program Flow End

(If program flow is required by the module, the function to add the temporary variable to the global accumulator is done here)

## Shutdown Functions

(Note: For multiple functions, insert new headers at the “Header 2” level – subset of “5.4 Shutdown Functions” and follow the same sub-section design shown below)

### Shtdn: _L_Shtdn(n)

#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)

#### Program Flow Start

(If program flow is required by the module, the function to store the unique identifier to a temporary variable is done here – start of the function)

#### Store Module Inputs to Local copies

(If not required based on design, insert text “None”)

#### (Processing of function)………

(Breakdown the function into smaller sections to add clarity to the design).

#### Store Local copy of outputs into Module Outputs

(If not required based on design, insert text “None”)

#### Program Flow End

(If program flow is required by the module, the function to add the temporary variable to the global accumulator is done here)

## Interrupt Functions

(Note: For multiple functions, insert new headers at the “Header 2” level – subset of “5.5 Interrupt Functions” and follow the same sub-section design shown below)

### Isr: _L_Isr(n)

#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)

#### (Processing of the ISR function)…..

(Note: Multiple headings can be used to break apart the functionality)

## Serial Communication Functions

(Note: For multiple functions, insert new headers at the “Header 2” level – subset of “5.6 Serial Communication Functions” and follow the same sub-section design shown below)

### SComm: _L_SComm(n)

#### Design Rationale

(Add design rationale specifically related to this FUNCTION.  If none required, place the text “None”)

#### Program Flow Start

(If program flow is required by the module, the function to store the unique identifier to a temporary variable is done here – start of the function)

#### Store Module Inputs to Local copies

(If not required based on design, insert text “None”)

#### (Processing of function)………

(Breakdown the function into smaller sections to add clarity to the design).

#### Store Local copy of outputs into Module Outputs

(If not required based on design, insert text “None”)

#### Program Flow End

(If program flow is required by the module, the function to add the temporary variable to the global accumulator is done here)

# Execution Requirements

## Execution Sequence of the Module

(Describe in words relevant details about the execution sequence of the different sub modules.)

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Issues / Limitations With Design

(Item #1)

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| <VarName_Units_Type> | <VarName_Units_Type> | <VarName_Units_Type> |

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| <None> |  |  |  |  |

|  |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| (Name given for the user defined typdef of type struct/union)<br/>(Variable name qualified similar to all other variables) | (Variable name qualified similar to all other variables) | as other variables |  |  |

|  | (Variable name qualified similar to all other variables) |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| <None> |

|  |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| <None> |  |  |  |

|  |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| <None> |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Function Name | (Exact name used) | Type | Min | Max | UTP Tol. |

| Arguments Passed | (if none, write None) |  |  |  |  |

|  | (Insert more rows for additional passed arguments) |  |  |  |  |

| Return Value | (if no value returned, write N/A) |  |  |  |  |
