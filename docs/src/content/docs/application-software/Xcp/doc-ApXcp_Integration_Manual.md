---
title: "Universal Measurement and Calibration Protocol Interface — Integration manual: ApXcp_Integration_Manual"
description: "Integration manual for Universal Measurement and Calibration Protocol Interface (converted)."
---

# Universal Measurement and Calibration Protocol Interface — Integration manual: ApXcp_Integration_Manual

> Source: `Xcp/doc/ApXcp_Integration_Manual.docx` (82,129 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual – ApXcp

Table of Contents

1	Dependencies	2

1.1	SWCs	2

1.2	Functions to be provided to Integration Project	2

2	Configuration	3

2.1	Build Time Config	3

2.2	Configuration Files to be provided by Integration Project	3

2.2.1	Da Vinci Config generation	3

2.2.2	Manual Configuration Changes	3

3	Integration	4

3.1	Required Global Data Inputs	4

3.2	Optional Global Data Inputs	4

3.3	Specific Include Path present	4

4	Runnable Scheduling	5

5	Memory Mapping	6

5.1	Mapping	6

5.2	Usage	6

5.3	NvM Blocks	6

6	Compiler Settings	6

6.1	Preprocessor MACRO	6

6.2	Optimization Settings	6

7	Revision Control Log	7

# Dependencies

## GetSetIndexes() and GetPersIndexes()

### Overview

The integration specific functions below, GetSetIndexes and GetPersIndexes, are used to return an array of tuning identifiers to the tune-on-the-fly (or online calibration as defined in the XCP specs) function. They are used to copy the active sets or personalities into RAM. The functions should be implemented in an integration specific component that determines the desired personality and desired set identifiers sent to tuning select authority SWC.

If tune-on-the-fly functionality is disabled, the functions below do not need to be defined.

If tune-on-the-fly is enabled and the lookup functions are disabled, the functions below do not need to be defined. When a copy cal page XCP command is called, the personalities are copied from 0 to a max limit based on the active tuning set that is currently being used.  In the case of the tuning sets being copied, only the active tuning set is copied in to the RAM.

### Function Prototypes

The actual implementation of the function will vary between programs. However, the function should be structured so the passed arguments are of the same time to provide a common interface to the XCP functions.

### Example 1 -- BMW

The following example illustrates a similar situation found in the BMW program. Active personalities are determined by coding bits. Using the GetPersIndexes function, the function will loop through the personalities to find the index of the personality that contains the matching coding ID. The indexes are returned and the active personalities are copied into RAM.

## ProcessXCPPID()

### Overview

This function must be available to this module to call by the integration manual.  This should be provided by the CMS component which does the processing on XCP PIDs.  This function is required to allow the CMS component to figure out when an XCP PID is finished being read or written.

### Function Prototypes

# Configuration

## Build Time Config

## Configuration Files to be provided by Integration Project

### Da Vinci Parameter Configuration Changes

### DaVinci Interrupt Configuration Changes

### Manual Configuration Changes

### GENy Configuration Changes

# Integration

## Required Global Data Inputs

<Mention any global variable that this component requires for other components>

## Required Global Data Outputs

<Mention any global variable that this component requires for other components>

## Specific Include Path present

Yes

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

<Define all the preprocessor Macros needed and conditions when needed>.

## Optimization Settings

<Define Optimization levels that are needed and conditions when needed>.

# Revision Control Log


**Table 1 (from source document):**


| Module | Required API |

| <Integration Specific Module> | Function outline defined below: |


**Table 2 (from source document):**


| Function Name | GetSetIndexes or GetPersndexes | Type | Dir. | Min | Max | UTP Tol. |

| Arguments Passed | NumOfSets_Cnt_T_u8<br/>or<br/>NumOfPers_Cnt_T_u8 | uint8 | I | 0 | 255 |  |

|  | data | uint8* | I/O | 0 | 255 |  |

| Return Value | N/A |  |  |  |  |  |


**Table 3 (from source document):**


| Module | Required API |

| CMS Common | Function outline defined below: |


**Table 4 (from source document):**


| Function Name | ProcessXCPPID | Type | Dir. | Min | Max | UTP Tol. |

| Arguments Passed | Size_Cnt_T_u08 | uint8 | I | 1 | 8 |  |

| Return Value | N/A |  |  |  |  |  |


**Table 5 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 6 (from source document):**


| Parameter | Notes | SWC |

| D_NUMOFVLDEEMEMRGNS_CNT_U08 | Generated in Ap_ApXcp.Cfg.h if external EEPROM access is set to STD_ON in Configurator. Value will be determined by the EEPROM memory access defined in the ECUC file. | ApXcp |

| BC_XCP_EXTEEPACCESS | Set to STD_ON in Configurator if XCP access to external EEPROM is required. | ApXcp |

| BC_XCP_TUNEONFLY | Set to STD_ON in Configuartor if tune-on-the-fly support is required. | ApXcp |

| BC_XCP_PERSINDEXLOOKUP | Set to STD_ON in Configurator if a function call to GetPersIndexes is required to return the indexes of active personalities. Note: BC_XCP_TUNEONFLY must be set to STD_ON | ApXcp |

| BC_XCP_SETINDEXLOOKUP | Set to STD_ON in Configurator if a function call to GetSetIndexes is required to return the indexes of active sets. Note: BC_XCP_TUNEONFLY must be set to STD_ON | ApXcp |

| <Non Trusted Function Stack Size> | This needs to be configured (to a non-zero value) for the task or ISR that handles the XCP commands.  This is required to support application switching for XCP writes.  Please note this is only required if a program has non-trusted applications configured. | Os |

| <Trusted/Non Trusted functions for XCP writes> | If a program has multiple applications configured, non-trusted or trusted functions must be configured for each application.  This is required to allow the XCP write commands to switch context before performing the write.  These functions should end up calling ApXcpWriteCommon() to perform the write.<br/>Ex:<br/>NtWrapS_XcpWriteAp8()<br/>NtWrapS_XcpWriteAp9()<br/>TWrapS_XcpWriteAp0 | Os |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |


**Table 7 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

|  |  |  |  |


**Table 8 (from source document):**


| Constant | Notes | SWC |

|  |  |  |
