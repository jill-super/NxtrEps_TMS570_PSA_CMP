---
title: "Diagnostic Event Manager Interface — DemIf_MDD"
description: "Design document (converted)."
---

# Diagnostic Event Manager Interface — DemIf_MDD.docx

> Source: `PSA_CMP_EPS_TMS570/SwProject/DemIf/doc/DemIf_MDD.docx` (671,345 bytes). Converted automatically.

For

DemIf

March 28, 2018

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

S&ES,

Nexteer Automotive,

Tychy, PolandChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	DemIf & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of DemIf	6

3.2	Data Flow Diagram	6

3.2.1	Module level DFD for DTC monitoring functionality	6

3.2.2	Module level DFD for DTC inhibition functionality	7

3.3	Component diagram	7

3.4	Variable Data Dictionary	7

3.4.1	User defined ‘typedef’ definition/declaration	7

3.4.2	Variable definition for enumerated types	7

3.5	Constant Data Dictionary	7

3.5.1	Program Constants	7

3.5.2	Module Specific Lookup Tables	8

3.6	Software Module Implementation	8

3.6.1	Sub-Module Functions	8

3.6.2	Interrupt Service Routines	11

3.6.3	_SCOMM () Functions DemIf_VehSpdControl()	11

3.6.4	Module Internal (Local) Functions	11

3.6.5	Transition Functions	12

4	Known Limitations with Design	13

5	UNIT TEST CONSIDERATION	14

Appendix A	Abbreviations and Acronyms	15

Appendix B	Glossary	16

Appendix C	References	17

# Introduction

## Purpose

Purpose of this document is to present design of the DemIf component software implementation.

## Scope

Document focuses on DemIf component only.

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance.

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.

May: indicates an optional action.

# DemIf & High-Level Description

DemIf component is an interface between AUTOSAR DEM component interface and Nexteer DiagMgr component. Intention of this component is to give flexibility in the interaction between those two components.

DemIf optimizes monitoring of the status of DTC (CTC) events and lets to control which DTC shall be reported and which not.

DemIf is responsible also for deinitialization of DEM component and changing Operational Cycles in DEM on SWC request.

# Design details of software module

## Graphical representation of DemIf

## Data Flow Diagram

### Module level DFD for DTC monitoring functionality

### Module level DFD for DTC inhibition functionality

## Component diagram

## Variable Data Dictionary

### User defined ‘typedef’ definition/declaration

N/A

### Variable definition for enumerated types

N/A

## Constant Data Dictionary

### Program Constants

#### Local Constants

#### Global Constants

N/A

### Module Specific Lookup Tables

See CTCInhibitionMask_Cnt_M_u08 chapter 3.5.1.1

## Software Module Implementation

### Sub-Module Functions

#### Initialization sub-module DemIf_Init()

#### Periodic sub-module DemIf_Per()

#### Non Periodic sub-module DemIf_SetEventStatus ()

#### Non Periodic sub-module DemIf_DTCStatusChanged()

#### Non Periodic sub-module DemIf_SetOperationCycleState()

Function passes operational cycle directly to DEM.

#### Non Periodic sub-module DemIf_RestartDem()

Function initializes DEM component.

#### Non Periodic sub-module DemIf_DemShutdown()

Function shuts down DEM component.

### Interrupt Service Routines

N/A

### _SCOMM () Functions DemIf_VehSpdControl()

Function stores Vehicle Speed Control status reported by Serial Com / Diagnostics

### Module Internal (Local) Functions

#### Module Internal (Local) Function DemIf_CheckVoltageRange()

#### Module Internal (Local) Function DemIf_EvaluateLogicalCondition()

### Transition Functions

N/A

# Known Limitations with Design

Any change in configuration of the DEM Event list may impact content of the CTCInhibitionMask_Cnt_M_u08. DEM sorts Events by DTC number. If event number changes, there is risk of sorting events in different order what changes event IDs.

# UNIT TEST CONSIDERATION

N/A

#### Abbreviations and Acronyms

#### Glossary

Note: Terms and definitions from the source “Nexteer Automotive” take precedence over all other definitions of the same term.  Terms and definitions from the source “Nexteer Automotive” are formulated from multiple sources, including the following:

ISO 9000

ISO/IEC 12207

ISO/IEC 15504

Automotive SPICE® Process Reference Model (PRM)

Automotive SPICE® Process Assessment Model (PAM)

ISO/IEC 15288

ISO 26262

IEEE Standards

SWEBOK

PMBOK

Existing Nexteer Automotive documentation

#### References


**Table 1 (from source document):**


| Description | Author | Version | Date | Approved By |

| Initial Version | Robert Konieczny | 0.9 | 28-03-18 |  |

| Post review | Robert Konieczny | 1.0 | 30-03-18 | Jakub Karpiński |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 2 (from source document):**


| Name | Type | Value | Description |

| CTCInhibitionMask_Cnt_M_u08 | uint8[] | See the code | Holds configuration of all DTC for inhibition scenarios. If flag for particular scenario is set, DTC shall be inhibited if scenario is active |

| D_CTC_INHIB_ESC | uint8 | 0x01u | Flag for ESC inhibition scenario |

| D_CTC_INHIB_BSI | uint8 | 0x02u | Flag for BSI inhibition scenario |

| D_CTC_INHIB_CAV | uint8 | 0x04u | Flag for CAV inhibition scenario |

| D_CTC_INHIB_AAS | uint8 | 0x08u | Flag for AAS inhibition scenario |

| D_CTC_INHIB_CMM | uint8 | 0x10u | Flag for CMM inhibition scenario |

| D_CTC_INHIB_COM | uint8 | 0x40u | Flag for COM inhibition scenario |

| D_CTC_INHIB_ELEC_INT | uint8 | 0x80u | Flag for ELEC_INT inhibition scenario |

|  |  |  |  |

|  |  |  |  |


**Table 3 (from source document):**


| Function Name | DemIf_CheckVoltageRange | Type | Min | Max |

| Arguments Passed | voltage_Volt_T_f32 | float32 | 0 | 31 |

|  | min_Volt_T_f32 | float32 | 0 | 31 |

|  | max_Volt_T_f32 | float32 | 0 | 31 |

|  | time_cnt_T_u32 | uint32 | 0 | 2^32 |

|  | timer_cnt_T_u32 | uint32* | 0 | 2^32 |


**Table 4 (from source document):**


| Function Name | DemIf_EvaluateLogicalCondition | Type | Min | Max |

| Arguments Passed | Time_ms_T_u32 | uint32 | 0 | 2^32 |


**Table 5 (from source document):**


| Abbreviation or Acronym | Description |

| CTC | Customer Trouble Code, equivalent to DTC |

|  |  |


**Table 6 (from source document):**


| Term | Definition | Source |

| MDD | Module Design Document |  |

| DFD | Data Flow Diagram |  |


**Table 7 (from source document):**


| Ref. # | Title | Version |

| 1 | AUTOSAR Specification of Memory Mapping (Link:AUTOSAR_SWS_MemoryMapping.pdf) | v1.3.0 R4.0 Rev 2 |

| 2 | MDD Guideline | EA3 01.04.00 |

| 3 | Software Naming Conventions.doc | 1.0 |

| 4 | Software Design and Coding Standards.doc | 2.0 |
