---
title: "Customer Battery Diagnostics — CustomerBattDiagnostic_MDD"
description: "Design document (converted)."
---

# Customer Battery Diagnostics — CustomerBattDiagnostic_MDD.docx

> Source: `PSA_CMP_EPS_TMS570/SwProject/CustBattDiag/doc/CustomerBattDiagnostic_MDD.docx` (1,172,137 bytes). Converted automatically.

Module Design Document

For

Customer Battery Voltage Diagnostics

VERSION:

DATE: -201

Revision History

Table of Contents

# Abbrevations And Acronyms

# References

This section Lists the title & version of all the documents that are referred for development of this document

# Battery Voltage Diagnostic High-Level Description

This module is responsible for applying voltage and time based hysteresis to the battery voltage to determine customer specific over voltage and low voltage faults.  Requirements for all these faults are detailed in the SCIR.

# Design details of software module

## Graphical representation of CustBattDiag

## Data Flow Diagram

None

## Module level DFD

None

## Sub-Module level DFD

None

## COMPONENT FLOW DIAGRAM

# Variable Data Dictionary

## User defined typedef definition/declaration

## Variable definition for enumerated types

# Constant Data Dictionary

## Program(fixed) Constants

## Embedded Constants

## Local

## Global

## Module specific Lookup Tables Constants

## Library Functions / Macros

## Data Hiding Functions

# Software Module Implementation

## Initialization Functions

None

## PERIODIC FUNCTIONS

## Per:

## Design Rationale

The under voltage and over voltage diagnostics(NTC 0xE5 and 0xE7) are specified to run in all states and at a 10ms rate.  Due to the faster diagnostic timing and different enable conditions, these two NTCs were moved into their own periodic.

## Store Module Inputs to Local copies

## Ntc 0xE5 and 0xE7 Diagnostics

## Store Local copy of outputs into Module Outputs

None

## Per: CustBattDiag_Per2

## Design Rationale

The battery voltage diagnostics were split into two periodics.  Per1 handles the faster 10ms diagnostics while Per2 handles the res

## Store Module Inputs to Local copies

## Battery Voltage Diagnostics

## Store Local copy of outputs into Module Outputs

None

## Interrupt Functions

None

## TRANSIENT FUNCTIONS

None

## Serial Communication Functions

None

## Local Function/Macro Definitions

## Description

## GLObAL Function/Macro Definitions

# Known Limitations With Design

# UNIT TEST CONSIDERATION

# Appendix A – Configuration Schemes


**Table 1 (from source document):**


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial version | Steve Horwath | 1 | 15-Oct-2014 |

| 2 | Input update, cleanup | Owen Tosh | 2 | 14-Jan-2015 |

| 3 | Updates for SCIR 003B | Owen Tosh | 3 | 20-Jul-2015 |

| 4 | Corrected E8 timer conditions | Owen Tosh | 4 | 14-Sept-2015 |

| 5 | Implemented NTC E9 | Owen Tosh | 5 | 24-Nov-2015 |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 2 (from source document):**


| Abbreviation | Description |

| MDD | Module design Document |


**Table 3 (from source document):**


| Sr. No. | Title | Version |

| 1 | MDD Guidelines | 1 |

| 2 | Software Naming Conventions | 1 |

| 3 | Coding Standands | 1 |

| 4 | PSA SCIR |  |


**Table 4 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 5 (from source document):**


| Enum  Name | Element Name | Value |

|  |  |  |


**Table 6 (from source document):**


| Constant Name | Resolution | Units | Value |

|  | 1 | Count | 0 |

|  | 1 | Count | 1 |

|  | 1 | Count | 2 |

|  | 1 |  |  |

|  | 1 |  |  |

|  | 1 |  | 0x |

|  | 1 |  |  |

|  | 1 |  | 0x0 |

|  | 1 | Count |  |

|  | 1 | Count |  |

|  | 1 | Count |  |

|  | 1 | Count |  |

|  | 1 | Count |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |


**Table 7 (from source document):**


|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |

|  |  |  |  |


**Table 8 (from source document):**


|  |

|  |

|  |

|  |
