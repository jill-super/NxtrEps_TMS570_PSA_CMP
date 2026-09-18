---
title: "Motor Control (Current Mode) — Model Design Document: TrqCanc_MDD"
description: "Model Design Document for Motor Control (Current Mode) (converted)."
---

# Motor Control (Current Mode) — Model Design Document: TrqCanc_MDD

> Source: `MtrCtrl_CM/doc/TrqCanc_MDD.docx` (1,199,331 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module -- TrqCanc

# High-Level Description

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

(This is for lookup tables (arrays) with fixed values, same name as other tables)

# Functions/Macros used by the Sub-Modules

## Library Functions / Macros

The library and functions / Macros that are called by the various sub modules are identified below,

Abs_s16_m

FPM_FloatToFixed_m

TableSize_m

FPM_FixedToFloat_m

IntplVarXY_u16_u16Xu16Y_Cnt

BilinearXYM_s16_u16Xs16YM_Cnt

sqrtf

atan2f

sinf

Rte_Pim_CogTrqCal

Rte_Pim_CogTrqRplComp

## Data Hiding Functions

MtrCntrl_Read_MtrElecPol_Cnt_s8

MtrCntrl_Read_MtrPosElec_Rev_u0p16

MtrCntrl_Read_ReadFwdPthAccessBfr_Cnt_u16

## Global Functions/Macros Defined by this Module

None

## Local Functions/Macros Used by this MDD only

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

### Per:  TrqCanc_Init

#### Design Rationale

Update the lookup table for ripple’s

#### Processing

## Periodic Functions

### Per:  TrqCanc_Per1

#### Design Rationale

FastDataAccessBufIndex  allows  the buffer synchronization between data calculated on slower periodic loop time(2 milli seconds)  and are  read by faster periodic run time (ie 0.125ms)

#### Program Flow Start

Rte_Call_TrqCanc_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

MRFMtrVel_MtrRadpS_T_f32=Rte_IRead_TrqCanc_Per1_MRFMtrVel_MtrRadpS_f32

DaxRef_Amp_T_f32=Rte_IRead_TrqCanc_Per1_MtrCurrDaxRef_Amp_f32

QaxRef_Amp_T_f32 =Rte_IRead_TrqCanc_Per1_MtrCurrQaxRef_Amp_f32

WriteAccessBufIndex_Cnt_T_u16= (FastDataAccessBufIndex_Cnt_M_u16&1)^1

EstLq_Henry_T_f32=Rte_IRead_TrqCanc_Per1_EstLq_Henry_f32()

MtrTrqCmdMRFScl_MtrNm_T_f32 =Rte_IRead_TrqCanc_Per1_MtrTrqCmdMRFScl_MtrNm_f32()

EstLd_Henry_T_f32=Rte_IRead_TrqCanc_Per1_EstLd_Henry_f32()

EstKe_VpRadpS_T_f32 = Rte_IRead_TrqCanc_Per1_EstKe_VpRadpS_f32()

#### Store Local copy of outputs into Module Outputs

MtrTrqRpl6Mag_MtrNm_M_f32[WriteAccessBufIndex_Cnt_T_u16] =  MtrTrq6thMag_MtrNm_T_f32

MtrTrqRpl12Mag_MtrNm_M_f32[WriteAccessBufIndex_Cnt_T_u16] = MtrTrq12thMag_MtrNm_T_f32

MtrTrq6Ph_Rad_M_f32[WriteAccessBufIndex_Cnt_T_u16] =     MtrTrqRip6thPhs_Rad_T_f32

MtrTrq12Ph_Rad_M_f32[WriteAccessBufIndex_Cnt_T_u16]  =   MtrTrqRip12thPhs_Rad_T_f32

MtrTrqRpl18Mag_MtrNm_M_f32[WriteAccessBufIndex_Cnt_T_u16] =MtrTrq18thMag_MtrNm_T_f32

MtrTrq18Ph_Rad_M_f32[WriteAccessBufIndex_Cnt_T_u16] =    MtrTrqRip18thPhs_Rad_T_f32

TrqCanc_IqtoTrqMulti_VpRadpS_M_f32[WriteAccessBufIndex_Cnt_T_u16] = IqtoTrqMulti_VpRadpS_T_f32

#### Program Flow End

Rte_Call_TrqCanc_Per1_CP1_CheckpointReached()

## Periodic Functions

### Per:  TrqCogCancRefPer1

#### Design Rationale

FastDataAccessBufIndex  allows  the buffer synchronization between data calculated on slower periodic loop time(2 milli seconds)  and are  read by faster periodic run time. SlowDataAccessBufIndex  allows  the buffer synchronization between data calculated on faster periodic loop time(125 micro seconds)  and are  read by slower periodic run time (ie 2ms)

#### Program Flow Start

N/A

#### Store Module Inputs to Local copies

DataAccessBfr_Cnt_T_u16 =FastDataAccessBufIndex_Cnt_M_u16

MtrCntrl_Read_MtrElecPol_Cnt_s8(&MtrElecPol_Cnt_T_s8)

MtrCntrl_Read_MtrPosElec_Rev_u0p16(&MtrPosElec_Rev_T_u0p16)

MtrPosComputDelay_Rad_T_f32=MtrPosComputationDelayRpl_Rad_M_f32[DataAccessBfr_Cnt_T_u16]

EstKe_VpRadpS_T_f32= MtrEstKe_VpRadpS_M_f32[DataAccessBfr_Cnt_T_u16]

MtrTrqRpl6Mag_MtrNm_T_f32 =MtrTrqRpl6Mag_MtrNm_M_f32[DataAccessBfr_Cnt_T_u16] MtrTrqRpl12Mag_MtrNm_T_f32=MtrTrqRpl12Mag_MtrNm_M_f32[DataAccessBfr_Cnt_T_u16]

MtrTrq6Ph_Rad_T_f32  =MtrTrq6Ph_Rad_M_f32[DataAccessBfr_Cnt_T_u16]

MtrTrq12Ph_Rad_T_f32 =MtrTrq12Ph_Rad_M_f32[DataAccessBfr_Cnt_T_u16]

MtrTrqRpl18Mag_MtrNm_T_f32=MtrTrqRpl18Mag_MtrNm_M_f32[DataAccessBfr_Cnt_T_u16]

MtrTrq18Ph_Rad_T_f32  =MtrTrq18Ph_Rad_M_f32[DataAccessBfr_Cnt_T_u16]

IqtoTrqMulti_VpRadpS_T_f32 = TrqCanc_IqtoTrqMulti_VpRadpS_M_f32[DataAccessBfr_Cnt_T_u16] ;

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

## Fault Recovery Functions

None

## Shutdown Functions

None

## Interrupt Functions

None

## Serial Communication Functions

### SComm: TrqCanc_Scom_ReadCogTrqCal

#### Design Rationale

#ifdef RTE_PTR2ARRAYBASETYPE_PASSING

FUNC(void, RTE_AP_TRQCANC_APPL_CODE) TrqCanc_Scom_ReadCogTrqCal(P2VAR(UInt16, AUTOMATIC, RTE_AP_TRQCANC_APPL_VAR) CogTrqCalPtr, UInt16 ID)

#else

FUNC(void, RTE_AP_TRQCANC_APPL_CODE) TrqCanc_Scom_ReadCogTrqCal(P2VAR(CoggingCancTrq, AUTOMATIC, RTE_AP_TRQCANC_APPL_VAR) CogTrqCalPtr, UInt16 ID)

#endif

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### Processing

#### Store Local copy of outputs into Module Outputs

None

Program Flow End

None

### SComm: TrqCanc_Scom_SetCogTrqCal

#### Design Rationale

#### #ifdef RTE_PTR2ARRAYBASETYPE_PASSING

#### FUNC(void, RTE_AP_TRQCANC_APPL_CODE) TrqCanc_Scom_SetCogTrqCal(P2CONST(UInt16, AUTOMATIC, RTE_AP_TRQCANC_APPL_DATA) CogTrqCalPtr, UInt16 ID)

#### #else

#### FUNC(void, RTE_AP_TRQCANC_APPL_CODE) TrqCanc_Scom_SetCogTrqCal(P2CONST(CoggingCancTrq, AUTOMATIC, RTE_AP_TRQCANC_APPL_DATA) CogTrqCalPtr, UInt16 ID)

#endif

#### Program Flow Start

None

#### Store Module Inputs to Local copies

None

#### Processing

#### Store Local copy of outputs into Module Outputs

None

#### Program Flow End

None

## Local Function/Macro Definitions

### CoggingTrqTableUpdate#1

#### Description

### SinLookup #2

#### Description

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

Note for UNIT  TEST:

Rte_Pim_CogTrqCal  and CogTrqRplComp is declared as unit16 with size of 521  with 512 values are used in the look up and 9 values are used in the harmonic table compensation.

Eventhough the values are read as uint16 it will be used as sint16 ( s5p10 preciously) with the range of -1 to 1 .

As Range is from -1 to 1 and Variable is Unit 16, While testing we should use the value as below :

For testing Use the value between 0 to 1024 and  64512 to 65535 only.  so here 0 to 1024  = 0 to 1 and 64512 to 65535 = -1 to 0

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| Refer the Data dictionary | Refer the Data dictionary | Refer the Data dictionary |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |

|  |  |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| Refer the Data dictionary | Refer the Data dictionary | Refer the Data dictionary | Refer the Data dictionary | Refer the Data dictionary |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |

|  |  |  |  |  |


**Table 3 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| CoggingM_Amp_Str | CoggingMX_MtrNm_s2p13 | sint16 | FULL | FULL |

|  | CoggingMY_MtrNm_s2p13 | sint16 | FULL | FULL |

| CogTrqCalPtr | Rte_Pim_CogTrqCal()[512] | Uint16 | -1 | 1 |

| CogTrqCalRplCompPtr | Rte_Pim_CogTrqRplComp()[9] | Uint16 | -1 | 1 |


**Table 4 (from source document):**


| Constant Name |

| k_Harmonic6thElec_Uls_f32 |

| k_Harmonic12thElec_Uls_f32 |

| k_Harmonic18thElec_Uls_f32 |

| t_MtrCurrQaxRpl_Amp_u9p7[] |

| t_MtrCurrDaxRpl_Amp_u9p7[] |

| t2_MtrTrqRpl6X_MtrNm_s2p13 |

| t2_MtrTrqRpl6Y_MtrNm_s2p13 |

| t2_MtrTrqRpl12X_MtrNm_s2p13 |

| t2_MtrTrqRpl12Y_MtrNm_s2p13 |

| t2_MtrTrqRpl18X_MtrNm_s2p13 |

| t2_MtrTrqRpl18Y_MtrNm_s2p13 |

| t_MtrVelX_MtrRadpS_T_u14p2[10] |

| t_MtrTrqCancPIMagRP_Uls_u6p10[10] |

| t_MtrTrqCancPIPhRP_Rev_u0p16[10] |

| t_MtrTrqCmdPIY_MtrNm_u5p11 [] |

| t2_MtrTrqCancPIMagRP_Uls_u6p10[] |

| t2_MtrTrqCancPIPhRP_Rev_u0p16[] |


**Table 5 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_SQRT3OVR2_ULS_F32 | Single precision float | Unit less | 0.866025403784 |

| D_6HARMONICNO_F32 | Single precision float | Unit less | 6 |

| D_12HARMONICNO_F32 | Single precision float | Unit less | 12 |

| D_COGGINGTBLRES_F32 | Single precision float | Counts | 81.48733 |

| D_MAXTBLVALUE_CNT_u16 | 1 | Counts | 511 |

| D_SCALERADTOCNTS_ULS_F32 | Single precision float | Unit less | 10430.3783505 |

| D_30DEGREES_CNT_U16 | 1 | Counts | 5461 |

| D_DEG2RAD_ULS_F32 | Singles precision float | Unit less | 0.0174532925199 |

| D_REVWITHROUND_ULS_F32 | Singles precision float | Unit less | 65536.5 |

| D_ONEHALF_ULS_F32 | Singles precision float | Unit less | 0.5 |

| D_POSITIVEONE_CNT_S8 | 1 | Counts | 1 |

| D_COGTRQ_LOOPLMT | 1 | Unit less | 128 |

| D_DAXRPLTBLSZ_CNT_U8 | 1 | Counts | TableSize_m(t_MtrCurrDaxRpl_Amp_u9p7) |

| D_QAXRPLTBLSZ_CNT_U8 | 1 | Counts | TableSize_m(t_MtrCurrQaxRpl_Amp_u9p7) |

| D_COGTRQRPL_LOOPLMT | 1 | Counts | 3U |

| D_NOOFHARMONIC_CNT_U8 | 1 | Counts | 9U |

| D_MINCOGRANGE_NM_S5P10 | S5P10_T | Nm | -0.1 |

| D_MINCOGRANGE_NM_S5P10 | S5P10_T | Nm | 0.1 |

| D_MINCOGRANGE_NM_S2P13 | S2P13 | Nm | FPM_InitFixedPoint_m(-0.1,s2p13_T) |

| D_MAXCOGRANGE_NM_S2P13 | S2P13 | Nm | FPM_InitFixedPoint_m(0.1,s2p13_T) |

| D_MINTRQRANGE_NM_F32 | Single precision float | Nm | (-0.5F) |

| D_MAXTRQRANGE_NM_F32 | Single precision float | Nm | (-0.5F) |


**Table 6 (from source document):**


| Constant Name |

| D_2PI_ULS_F32 |

| D_ONE_ULS_F32 |

| D_ZERO_ULS_F32 |


**Table 7 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

| t_SinTbl_Cnt_u16 | Uint16 |  | TRQCANC_START_SEC_CONST_16 |


**Table 8 (from source document):**


| Data | Value |

|  |  |

|  |  |
