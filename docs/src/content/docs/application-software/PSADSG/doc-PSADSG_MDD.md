---
title: "PSA Diagnostic Service Gateway — Model Design Document: PSADSG_MDD"
description: "Model Design Document for PSA Diagnostic Service Gateway (converted)."
---

# PSA Diagnostic Service Gateway — Model Design Document: PSADSG_MDD

> Source: `PSADSG/doc/PSADSG_MDD.docx` (98,974 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

PSADSG

February 02, 2018

Prepared For:

Software Engineering

Nexteer Automotive,

Saginaw, MI, USA

Prepared By:

SEPG,

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	Introduction	4

1.1	Purpose	4

1.2	Scope	4

2	PSADSG & High-Level Description	5

3	Design details of software module	6

3.1	Graphical representation of PSADSG	6

3.2	Data Flow Diagram	6

3.2.1	Module level DFD	6

3.2.2	Sub-Module level DFD	6

3.3	Component diagram	6

3.4	Variable Data Dictionary	6

3.4.1	User defined ‘typedef’ definition/declaration	6

3.4.2	Variable definition for enumerated types	6

3.5	Constant Data Dictionary	7

3.5.1	Program Constants	7

3.5.2	Module Specific Lookup Tables	7

3.6	Software Module Implementation	7

3.6.1	Sub-Module Functions	7

3.6.2	Interrupt Service Routines	7

3.6.3	_SCOMM () Functions	7

3.6.4	Module Internal (Local) Functions	7

3.6.5	Transition Functions	7

4	Known Limitations with Design	8

5	UNIT TEST CONSIDERATION	9

Appendix A	Abbreviations and Acronyms	10

Appendix B	Glossary	11

Appendix C	References	12

# Introduction

## Purpose

Module Design Document for PSADSG.

## Scope

The following definitions are used throughout this document:

Shall: indicates a mandatory requirement without exception in compliance.

Should: indicates a mandatory requirement; exceptions allowed only with documented justification.

May: indicates an optional action.

# PSADSG & High-Level Description

Define a factor for damping command which is vehicle speed and handwheel torque dependent.

# Design details of software module

## Graphical representation of PSADSG

## Data Flow Diagram

### Module level DFD

Refer FDD

### Sub-Module level DFD

Refer FDD

## Component diagram

Refer FDD

## Variable Data Dictionary

### User defined ‘typedef’ definition/declaration

### Variable definition for enumerated types

## Constant Data Dictionary

### Program Constants

#### Local Constants

#### Global Constants

### Module Specific Lookup Tables

## Software Module Implementation

### Sub-Module Functions

#### Periodic sub-module { PSADSG_Per1()}

Refer FDD

### Interrupt Service Routines

None

### _SCOMM () Functions

None

### Module Internal (Local) Functions

None

### Transition Functions

None

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

None

# Abbreviations and Acronyms

# Glossary

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

# References


**Table 1 (from source document):**


| Description | Author | Version | Date |

| Initial Version | Krzysztof Byrski | 1.0 | 02-Feb-2018 |


**Table 2 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| None |  |  |  |  |


**Table 3 (from source document):**


| Enum  Name | Element Name | Value |

| None |  |  |


**Table 4 (from source document):**


| Constant Name | Resolution | Units | Value |

| None |  |  |  |


**Table 5 (from source document):**


| Constant Name |

| D_MTRTRQCMDHILMT_MTRNM_F32 |

| D_MTRTRQCMDLOLMT_MTRNM_F32 |

| D_ZERO_ULS_F32 |


**Table 6 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 7 (from source document):**


| Abbreviation or Acronym | Description |

| - |  |


**Table 8 (from source document):**


| Term | Definition | Source |

| MDD | Module Design Document |  |

| DFD | Data Flow Diagram |  |
