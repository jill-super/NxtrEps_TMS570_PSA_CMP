---
title: "Motor Driver Diagnostics (Servo Drive Diagnostics) — Model Design Document: Motor_Driver_Diagnostics_MDD"
description: "Model Design Document for Motor Driver Diagnostics (Servo Drive Diagnostics) (converted)."
---

# Motor Driver Diagnostics (Servo Drive Diagnostics) — Model Design Document: Motor_Driver_Diagnostics_MDD

> Source: `SVDiag/doc/Motor_Driver_Diagnostics_MDD.docx` (1,010,799 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- Motor Driver Diagnostics

# High-Level Description

This function operates as a reporting mechanism for all Gate Drive faults.

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

#### Local

#### Global

This section lists the global constants used by the module.  For details on global constants, refer to the Data Dictionary for the application.

### Module specific Lookup Tables Constants

(This is for lookup tables (arrays) with fixed values, same name as other tables)

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

FPM_InitFixedPoint_m

DiagNStep_m

DiagPStep_m

DiagFailed_m

## Data Hiding Functions

Rte_Call_FetDrvReset_OP_SET

Rte_Call_FetFlt1Data_OP_GET

Rte_Call_FetFlt2Clk_OP_GET

Rte_Call_FetFlt2Clk_OP_SET

Rte_Call_IoHwAbPortConfig_SetFetFlt2ToOutput

Rte_Call_NxtrDiagMgr_GetEventFailed

Rte_Call_NxtrDiagMgr_SetNTCStatus

Rte_Call_SystemTime_DtrmnElapsedTime_mS_u16

Rte_Call_SystemTime_DtrmnElapsedTime_uS_u16

Rte_Call_SystemTime_GetSystemTime_mS_u32

Rte_Call_SystemTime_GetSystemTime_uS_u32

SuspendAllInterrupts

ResumeAllInterrupts

## Global Functions/Macros Defined by this Module

<None>

## Local Functions/Macros Used by this MDD only

### MotorDriverInit

#### Design Rationale

On gate drive startup there is the possibility of its fault register logging fault bits related to startup.  In order to clear these bits the gate drive is reset.  Once called, this operation shall wait a time period defined by k_GateDrvInitDwellTime_mS_u16p0.  Once elapsed, the operation will pulse the Reset line low for nominally 1 uSec.  Once done this operation will return MtrDrvInitComp_Cnt_T_lgc = TRUE.

#### Description

### ProcGateDriveFlt

#### Design Rationale

This function processes gate drive fault.

#### Description

### ProcBridgeFlt

#### Design Rationale

This function processes bridge fault.

#### Description

### ReadMtrDrvFltData

#### Design Rationale

#### The gate drive IC’s fault register is read serially through the fault flag lines.  This is done by clocking the FetFlt2  line and reading in the data on FetFlt1  .

#### The clock signal will have a 500 kHz max frequency.  At that clock frequency the interface circuit shall ensure a minimum positive and negative pulse width at the gate drive input of 750 nSec minimum.  Data is clocked out on the gate drive on the falling edge of its clock input.  This data is to be present at the DSP input for 250 nSec prior to the rising edge of the clock.

#### Description

### ResetGateDrive

#### Design Rationale

This function will pulse the Reset line low for nominally 1 uSec. This will clear the fault logging register fault bits.  An exclusive area is used around this timing to prevent this function from being interrupted during the wait period, as a pulse for longer than 3.5uSec will put the gate drive chip into a sleep mode.

#### Description

### GateDrvWaitTime

#### Design Rationale

The purpose of this function is to provide the delay times required for the bit manipulation used in this module. This function will wait the amount of time in uS of the variable passed into the function.

#### Description

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

None

## Periodic Functions

### Per: MtrDrvDiag_Per1

#### Design Rationale

The Motor Driver Diagnostic Periodic Processing operation systematically deals with the motor driver diagnostics. Each failure diagnosed by the gate drive IC has to be fully qualified by the DSP before a fault is considered present.  The qualification process used in this design is the typical PStep/Nstep fault accumulator method.  This design uses an assumption that each of the individual faults detected by the gate drive IC rarely occurs.  Therefore it is not necessary to track through individual fault accumulators for each of the fault indications provided by the gate drive.  Instead the faults will be placed into two groups, gate drive faults and FET faults each with their own fault accumulator.  For gate drive faults there is no need to identify the exact failure mode.  For FET faults the exact FET failure mode is to be learned but is not required until the FET fault has been fully qualified by the DSP. This function will read in the gate drive fault register. Fault conditions detected by gate drive IC are communicated through two dual purpose fault flag lines, FF1 and FF2.  The first purpose of the fault flag lines is to indicate a fault is present.  The second purpose is to serially transfer an internal fault register indicating which fault was present.

#### Program Flow Start

Rte_Call_MtrDrvDiag_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

#### Processing of function

#### Store Local copy of outputs into Module Outputs

#### Program Flow End

Rte_Call_MtrDrvDiag_Per1_CP1_CheckpointReached()

### Per: MtrDrvDiag_Per2

#### Design Rationale

Configurable checkpoints were not added to this periodic since it doesn’t run in all system states and the current requirements for program flow check require the checkpoint to be called in all system states if it is to be used.

#### Program Flow Start

None

#### Store Module Inputs to Local copies

N/A

#### Processing

Rte_Call_FetDrvReset_OP_SET(STD_LOW)

#### Store Local copy of outputs into Module Outputs

#### Program Flow End

N/A

### Per: MtrDrvDiag_Trns1

#### Design Rationale

This function reinitializes variables on entering WARMINIT state.

#### Program Flow Start

None

#### Processing of function

#### Program Flow End

N/A

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

None

# Execution Requirements

## Execution Rates for sub-modules called by the Scheduler

## Execution Requirements for Serial Communication Functions

# Memory Map Definition Requirements

## Sub Modules (Functions)

## Local Functions

# Known Issues / Limitations With Design

ReadMtrDrvFltData needs to be updated to support manual control of the NHET outputs when a faulted FET is detected.

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

|  |  | FETFaultPhase_Cnt_enum |

| MtrDrvrInitStart_Cnt_lgc | MtrDrvrInitStart_Cnt_lgc | FETFaultType_Cnt_enum |

|  |  | MtrDrvrInitComplete_Cnt_lgc |

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| SVDiag_MtrDrvInitStartTime_mS_M_u32p0 | uint32 | FULL | FULL | MTRDRVDIAG_START_SEC_VAR_CLEARED_32 |

| ResetWaitLoop_Cnt_M_lgc | boolean | FALSE | TRUE | MTRDRVDIAG_START_SEC_VAR_CLEARED_BOOLEAN |

| SVDiag_GateDrvFltSts_Cnt_D_b16 | uint16 | FULL | FULL | MTRDRVDIAG_START_SEC_VAR_CLEARED_16 |

| MtrDrvInitActive_Cnt_M_lgc | boolean | FALSE | TRUE | MTRDRVDIAG_START_SEC_VAR_CLEARED_BOOLEAN |

| FETFaultType_Cnt_M_enum | FETFAULTTYPE_ENUM | NOFAULT , LOWER , UPPER | NOFAULT , LOWER , UPPER | MTRDRVDIAG_START_SEC_VAR_CLEARED_UNSPECIFIED |

| FETFaultPhase_Cnt_M_enum | FETPHASETYPE_ENUM | NOPHASE,  PHASEA ,   PHASEB ,  PHASEC | NOPHASE,  PHASEA ,   PHASEB ,  PHASEC | MTRDRVDIAG_START_SEC_VAR_CLEARED_UNSPECIFIED |

| SVDiag_GateDriveFltAcc_Cnt_M_u16 | uint16 | FULL | FULL | MTRDRVDIAG_START_SEC_VAR_CLEARED_16 |

| SVDiag_GenGateDriveFltAcc_Cnt_M_u16 | uint16 | 0 | 200 | MTRDRVDIAG_START_SEC_VAR_CLEARED_16 |

| MtrDrvInitComp_Cnt_M_lgc | boolean | FALSE | TRUE | MTRDRVDIAG_START_SEC_VAR_CLEARED_BOOLEAN |

| SVDiag_OnStateFltAcc_Cnt_M_u16 | uint16 | FULL | FULL | MTRDRVDIAG_START_SEC_VAR_CLEARED_16 |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| <None> |  |  |  |  |


**Table 4 (from source document):**


| Constant Name |

| k_GateDriveDiag_Cnt_str |

|  |

|  |

| k_OnStateDiag_Cnt_str |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_PHASEALOWER_CNT_U16 | uint16 | Counts | 0U |

| D_PHASEBLOWER_CNT_U16 | uint16 | Counts | 1U |

| D_PHASECLOWER_CNT_U16 | uint16 | Counts | 2U |

| D_PHASEAUPPER_CNT_U16 | uint16 | Counts | 3U |

| D_PHASEBUPPER_CNT_U16 | uint16 | Counts | 4U |

| D_PHASECUPPER_CNT_U16 | uint16 | Counts | 5U |

| D_VREGUV_CNT_U16 | uint16 | Counts | 6U |

| D_BTSTRPAUV_CNT_U16 | uint16 | Counts | 7U |

| D_BTSTRPBUV_CNT_U16 | uint16 | Counts | 8U |

| D_BTSTRPCUV_CNT_U16 | uint16 | Counts | 9U |

| D_NUMOFGDSTATUSBITS_CNT_U16 | uint16 | Counts | 10U |

| D_STATUSALOWER_CNT_B16 | uint16 | Counts | 0x0001U |

| D_STATUSBLOWER_CNT_B16 | uint16 | Counts | 0x0002U |

| D_STATUSCLOWER_CNT_B16 | uint16 | Counts | 0x0004U |

| D_STATUSAUPPER_CNT_B16 | uint16 | Counts | 0x0008U |

| D_STATUSBUPPER_CNT_B16 | uint16 | Counts | 0x0010U |

| D_STATUSCUPPER_CNT_B16 | uint16 | Counts | 0x0020U |

| D_STATUSVREGUV_CNT_B16 | uint16 | Counts | 0x0040U |

| D_STATUSBTSTRPAUV_CNT_B16 | uint16 | Counts | 0x0080U |

| D_STATUSBTSTRPBUV_CNT_B16 | uint16 | Counts | 0x0100U |

| D_STATUSBTSTRPCUV_CNT_B16 | uint16 | Counts | 0x0200U |

| D_STATUSVDDUV_CNT_B16 | uint16 | Counts | 0x0400U |

| D_STATUSOVERTEMP_CNT_B16 | uint16 | Counts | 0x8000U |

| D_FFDATACLKTIME_US_U16P0 | uint16 | Microseconds | 4.0 |

| D_GDRESETTIME_US_U16P0 | uint16 | Microseconds | 2.0 |

|  |  |  |  |

|  |  |  |  |


**Table 6 (from source document):**


| Constant Name |

| <None> |

|  |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| None |  |  |  |


**Table 8 (from source document):**


| Function Name | MotorDriverInit | Type | Min | Max |

| Arguments Passed | void | N/A | N/A | N/A |

| Return Value | MtrDrvInitComp_Cnt_T_lgc | boolean | FALSE | TRUE |
