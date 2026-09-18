---
title: "Analog-to-Digital Converter Driver — Model Design Document: Adc_MDD"
description: "Model Design Document for Analog-to-Digital Converter Driver (converted)."
---

# Analog-to-Digital Converter Driver — Model Design Document: Adc_MDD

> Source: `Adc/doc/Adc_MDD.docx` (335,159 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- ADC

# High-Level Description

The ADC module shall control sampling and conversion of voltages from the hardware layer into digital signals. The ADC Register definition has been captured from the TMS570LS31x/21x 16/32-Bit RISC Flash Microcontroller Technical Reference Manual (SPNU499 – September 2011).

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

#### D_ADC1CURRENTMODE_ULS_LGC if True value 1 is selected to proceed. If not value 2 will be used,

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

### Module specific Lookup Tables Constants

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

None

## Data Hiding Functions

<None>

## Global Functions/Macros Defined by this Module

### ADC Init

This function is used to initialize each of the ADC1 Groups (Event, Group1, and Group2).

#### Initialize Module Internal Variables

None

#### Register Configuration

### Setup Result Buffer

This function is the Adc group result buffer setup service. It is responsible for setting up the result buffer pointer of the group.

This Api is provided to support for the standard Autosar API, however the design of this driver does not buffer an intermediate copy of the results and therefore does not require a result buffer.  The hardware provides a sufficient Adc results buffer.

For optimization purposes, this function could be defined as a macro.

#### Setup Group’s Result Buffer

return E_OK

### Start Group Conversion

This function starts a software triggered conversion of all channels of the requested Adc channel group.

In order to provide optimized execution of this single line function, this API should be defined as a macro, however, due to timing it is at the moment defined as a function.  The need for minimal runtime is driven by a Nexteer use case which executes this in the context of the MtrCtrl ISR in some EPS systems.

#### Select Channels to Convert

adcREG1->GxSEL[Group] = T_Adc1GroupConfigData_Cnt_Str[Group].ChannelSelect

### Get Group Status

Returns the conversion status of the requested ADC1 channel group.

#### Get Status

### Read Group Conversions

Reads the group conversion result of the last completed conversion round of the requested group and

stores the channel values starting at the DataBufferPtr address. The group channel values are stored in ascending channel number order (in contrast to the storage layout of the result buffer if streaming access is configured).

Per the design direction in FDD33, direct ADC result buffer acces is used instead of using the hardware FIFO access register.

#### Read Group

## Local Functions/Macros Used by this MDD only

None

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

None

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

## Transition Functions

None

# Execution Requirements

## Execution Sequence of the Module

## Execution Rates for sub-modules called by the Scheduler

This table serves as reference for the Scheduler design

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

This table identifies the software segments for functions identified in this module.

## Local Functions

This table identifies the software segments for local functions identified in this module.

# Known Limitations With Design

INLINE functions defined in “GlobalMacro.h” are not unit tested

Buffer pointer initialization could hang if adc conversion did not complete.  Consider adding a timeout and possible setting of NTC 0x32 bit 1.

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs |

| None |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| None |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| Adc_GroupType | N/A | uint8 | 0 | 2 |

| Adc_GroupConfigDataType | uint8   NumOfChannels,<br/>uint32 ChannelSelect,<br/>uint32* ResultBuf | struct | FULL | FULL |

| Adc_StatusType | ADC_IDLE,<br/>ADC_BUSY,<br/>ADC_COMPLETED,<br/>ADC_STREAM_COMPLETED | enum | 0 | 3 |

| Adc_ValueGroupType | N/A | uint16 | 0 | 4095 |

| Adc_ValueGroupType | N/A | uint16* | FULL | FULL |


**Table 4 (from source document):**


| Constant Name |

| k_VbattOVTransIntConfig_Cnt_u32 |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_NUMOFGROUPS_CNT_U8 | 1 | Counts | 3 |

| D_GROUPEV_CNT_U8 | 1 | Counts | 0 |

| D_GROUP1_CNT_U8 | 1 | Counts | 1 |

| D_GROUP2_CNT_U8 | 1 | Counts | 2 |

| D_NUMOFADCCALREADS_CNT_U8 | 1 | Counts | 8 |

| D_NTCPARMBIT0_CNT_U8 | 1 | Counts | 1 |

| D_NTCPARMBIT1_CNT_U8 | 1 | Counts | 2 |

| D_NTCPARMBIT2_CNT_U8 | 1 | Counts | 4 |

| D_ADC1RSLTBASEADR_CNT_U32 | 1 | Counts | 0xFF3E0000U |

| D_ADC1NUMRSLTBUF_CNT_U08 | 1 | Counts | 64 |

| D_ADC1CURRENTMODE_ULS_LGC | 1 | BOOLEAN | Generated in Adc_Cfg.h. |

| D_ADC1MAGINTMASK1_CNT_U16 | 1 | Counts | 0/0* |

| D_ADC1MAGINTASET_CNT_U16 | 1 | Counts | 1/0* |

| D_ADC1MAGINTCR1_CNT_U32 | 1 | Counts | k_VbattOVTransIntConfig_Cnt_u32/ 0* |

| D_ADC1THRINTENACLR_CNT_U16 | 1 | Counts | 6/7* |

| D_ADC1EVTBUFSZ_CNT_U08 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1G1BUFSZ_CNT_U08 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1G2BUFSZ_CNT_U08 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_GROUPEND_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_GROUPBUSY_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1GEVTSRC_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1GEVTDMACR_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1G1SRC_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1G1DMACR_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1G2SRC_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1G2DMACR_CNT_U32 | 1 | Counts | Generated in Adc_Cfg.h. |

| D_ADC1USEDMA_CNT_LGC | 1 | Counts | Generated in Adc_Cfg.h. |

| D_HWTRGADC1GEVT_CNT_LGC | 1 | Counts | Generated in Adc_Cfg.h. |

| D_HWTRGADC1G1_CNT_LGC | 1 | Counts | Generated in Adc_Cfg.h. |

| D_HWTRGADC1G2_CNT_LGC | 1 | Counts | Generated in Adc_Cfg.h. |


**Table 6 (from source document):**


| Constant Name |

| None |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| T_Adc1GroupConfigData_Cnt_Str[3] | Adc_GroupConfigDataType | {<br/>		D_ADC1NUMEVTCH_CNT_U08,<br/>		D_ADC1EVTCH_CNT_U32,<br/>		&(((uint32*)D_ADC1RSLTBASEADR_CNT_U32)[0]),<br/>	},<br/>	{<br/>		D_ADC1NUMG1CH_CNT_U08,<br/>		D_ADC1G1CH_CNT_U32,<br/>		&(((uint32*)D_ADC1RSLTBASEADR_CNT_U32)[D_ADC1EVTBUFSZ_CNT_U08]),<br/>	},<br/>	{<br/>		D_ADC1NUMG2CH_CNT_U08,<br/>		D_ADC1G2CH_CNT_U32,<br/>		&(((uint32*)D_ADC1RSLTBASEADR_CNT_U32)[D_ADC1EVTBUFSZ_CNT_U08 + D_ADC1G1BUFSZ_CNT_U08]),<br/>	} | CONST_32 |


**Table 8 (from source document):**


| Function Name | Adc_Init_FixedCfg<br/>( macro aliased is Adc_Init(x) ) | Type | Min | Max | UTP Tol. |

| Arguments Passed | None | N/A | N/A | N/A |  |

| Return Value | N/A |  |  |  |  |
