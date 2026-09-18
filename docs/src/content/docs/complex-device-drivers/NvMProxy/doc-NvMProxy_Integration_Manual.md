---
title: "Non-Volatile Memory Proxy — Integration manual: NvMProxy_Integration_Manual"
description: "Integration manual for Non-Volatile Memory Proxy (converted)."
---

# Non-Volatile Memory Proxy — Integration manual: NvMProxy_Integration_Manual

> Source: `NvMProxy/doc/NvMProxy_Integration_Manual.docx` (46,733 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Integration Manual – NvM Proxy

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

## SWCs

## Global Functions(Non RTE) to be provided to Integration Project

NvMProxy_Init

NvMProxy_MainFunction

NvMProxy_WriteBlock

NvMProxy_WriteAll

NvMProxy_GetErrorStatus

NvMProxy_SetRamBlockStatus

# Configuration

## Build Time Config

## Configuration Files to be provided by Integration Project

### Da Vinci Parameter Configuration Changes

### DaVinci Interrupt Configuration Changes

### Manual Configuration Changes

# Integration

The following import steps must be completed :

Place CBD project structure to appropriate integration folder

Execute the “Integrate.bat” script from the Tools directory of this component to perform the necessary integration steps:

The script creates the required directories in the integration project, “Generators/Artt/NvMProxy” and “Generators/Components/_Schemes/NvMProxy/bswmd”

The script then copies the required files from the CBD generate directory into the new directories.

If this is the first time integration, then perform the Davinci Configurator 3rd party component integration procedure.

Configure NvM proxy component per program needs

Generate NvM proxy and import generated Cd_NvMProxy_swc.arxml into davinci developer and map all NvM service needs on the blocks needing proxies to the NvM Proxy service component (instead of the NvM service component)

## Required Global Data Inputs

N/A

## Required Global Data Outputs

N/A

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


| Module | Required Feature |

| NvM | NvM_WriteBlock()<br/>NvM_GetBlockStatus() |

|  |  |

|  |  |


**Table 2 (from source document):**


| Modules | Notes |  |

| None |  |  |


**Table 3 (from source document):**


| Parameter | Notes | SWC |

| NvMProxyConfigSet/NvMProxyBlock/NvmRamBlockDataAddressSecure | The symbol name of the secured buffer location for the block data <br/>NOTE: For blocks defined by PIM memory in the Rte, this parameter is the symbol name that Developer inserts into the NvM Ram block configuration parameter for the associated NvM block) | NvMProxy |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

| NvMProxyConfigSet/NvMProxyBlock/NvMBlockDescriptorRef | Reference to the NvMBlockDescriptor container that defines the NvM block linked to this proxy configuration. | NvMProxy |

|  |  |  |

|  |  |  |

|  |  |  |


**Table 4 (from source document):**


| ISR Name | VIM # | Priority Dependency | Notes |

| N/A |  |  |  |


**Table 5 (from source document):**


| Constant | Notes | SWC |

| NVMPROXY_EXCLUSIVE_AREA_0 | This exclusive are covers the areas of execution within the component that are operating on the request buffer.  The buffer is operated on by the MainFunction and the WriteBlock functions.  An appropriate level of protection must be employed to maintain exclusive usage of the buffer data. | SchM |


**Table 6 (from source document):**


| Init | Scheduling Requirements | Trigger |

| NvMProxy_Init() | Must be executed after NvM driver has initialized the unsecured block data to be forwarded to the secured memory by this component. | Init |


**Table 7 (from source document):**


| Runnable | Scheduling Requirements | Trigger |

| NvMProxy_MainFunction() | Run prior to NvM_MainFunction for minimal request processing latency | Same as NvM_MainFunction |


**Table 8 (from source document):**


| Memory Section | Contents | Notes |

| NVMPROXY_START_SEC_VAR_NOINIT_8 |  | Typically allocated to application in which NvM driver resides.  <br/>Not required to be allocated to Global shared memeory. |

| NVMPROXY_START_SEC_VAR_CLEARED_16 |  | Must be allocated  into Global Shared memory |

| NVMPROXY_START_SEC_VAR_CLEARED_UNSPECIFIED |  | Must be allocated  into Global Shared memory |

| NVMPROXY_START_SEC_CODE |  |  |

| NVMPROXY_START_SEC_CONST_UNSPECIFIED |  |  |
