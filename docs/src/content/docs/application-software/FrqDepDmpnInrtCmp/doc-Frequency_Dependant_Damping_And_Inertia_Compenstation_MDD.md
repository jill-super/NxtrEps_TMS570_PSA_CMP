---
title: "Frequency-Dependent Damping and Inertia Compensation — Model Design Document: Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD"
description: "Model Design Document for Frequency-Dependent Damping and Inertia Compensation (converted)."
---

# Frequency-Dependent Damping and Inertia Compensation — Model Design Document: Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD

> Source: `FrqDepDmpnInrtCmp/doc/Frequency_Dependant_Damping_And_Inertia_Compenstation_MDD.docx` (933,563 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

# Module --

# High-Level Description

This MDD describes the methods to provide compensation that is dependent on filter of motor velocity which will compensate for motor inertia at low frequencies and provide damping acting at higher frequencies.

# Figures

## Diagram – Component

## Diagram – Function Data Sharing

N/A

### Diagram – FrqDepDmpnInrtCmp_Per1

# Variable Data Dictionary

For details on module input / output variable, refer to the Data Dictionary for the application.  Input / output variable names are listed here for reference.

(Note: Full variable names required in table.)

(Note: All global variables including End Of Line data used should be shown here)

## Module Internal Variables

This section identifies the name, range and resolutions for module specific data created by this module.  If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

### Module Display Variables

This section identifies the name, range and resolutions for data test points defined by the FDD. If there are no range restrictions on the variable, the term “FULL” is placed into the table for legal range.

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

Abs_f32_m

FPM_FloatToFixed_m

TableSize_m

FPM_FixedToFloat_m

LPF_SvUpdate_s16InFixKTrunc_m

Limit_m

FPM_FloatToFixedWithRound_m

## Data Hiding Functions

IntplVarXY_u16_u16Xu16Y_Cnt

## Global Functions/Macros Defined by this Module

N/A

## Local Functions/Macros Used by this MDD only

### Calculate Driver Velocity

#### Description

### Calculate Gain

#### Description

### Calculate ADD Coefficient

#### Description

### Calculate Filter Coefficients

#### Description

### Generate Command

#### Description

# Software Module Implementation

## Runtime Environment (RTE) Initial Values

This section lists the initial values of data written by this module but controlled by the RTE. After RTE initialization, the data in this table will contain these values.

## Initialization Functions

### FrqDepDmpnInrtCmp_Init

LPF_Init_f32_m(0.0f, k_InrtCmp_TBarVelLPFKn_Hz_f32, D_2MS_SEC_F32, &TbarVelFiltSv_M_str)

## Periodic Functions

### Per: _Per1

#### Design Rationale

This periodic handles all location function calls to calculate the inertia and frequency dependant damping compensation.

#### Program Flow Start

Rte_Call_FrqDepDmpnInrtCmp_Per1_CP0_CheckpointReached()

#### Store Module Inputs to Local copies

#### (Processing of function)………

#### Store Local copy of outputs into Module Outputs

#### Program Flow End

Rte_Call_FrqDepDmpnInrtCmp_Per1_CP1_CheckpointReached();

## Fault Recovery Functions

N/A

## Shutdown Functions

N/A

## Interrupt Functions

N/A

## Serial Communication Functions

N/A

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

# Filter Analysis

# Known Issues / Limitations With Design

INLINE functions defined in globalmacro.h are not unit tested

# Revision Control Log


**Table 1 (from source document):**


| Module Inputs | Module Outputs | Module Outputs |

| HwTorque_HwNm_f32 | HwTorque_HwNm_f32 | FrqDepDmpnInrtCmp_MtrNm_f32 |

| CRFMotorVel_MtrRadpS_f32 | CRFMotorVel_MtrRadpS_f32 |  |

| BaseAssistCmd_MtrNm_f32 | BaseAssistCmd_MtrNm_f32 |  |

| VehicleSpeed_Kph_f32 | VehicleSpeed_Kph_f32 |  |

| WIRCmdAmpBlnd_MtrNm_f32 | WIRCmdAmpBlnd_MtrNm_f32 |  |

| FreqDepDmpSrlComSvcDft_Cnt_lgc | FreqDepDmpSrlComSvcDft_Cnt_lgc |  |

| VehicleLonAccel_KphpS_T_f32 | VehicleLonAccel_KphpS_T_f32 |  |


**Table 2 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| PrevTbarAng_HwDeg_M_f32 | Single Precision Floating Point | -6.6667 | 6.6667 | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| Prev1SclDrvVel_RadpS_M_f32 | Single Precision Floating Point | -12917.3 | 12917.3 | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| Prev2SclDrvVel_RadpS_M_f32 | Single Precision Floating Point | -12917.3 | 12917.3 | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| Prev1PreAttnComp_MtrNm_M_f32 | Single Precision Floating Point | -8.8 | 8.8 | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| Prev2PreAttnComp_MtrNm_M_f32 | Single Precision Floating Point | -8.8 | 8.8 | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| TbarVelFiltSv_M_str | N/A | N/A | N/A | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_UNSPECIFIED |

| TbarVelFiltSv_M_str.K_ULS_F32 | Single Precision Floating Point | 0.001255848 | 0.715390457 |  |

| TbarVelFiltSv_M_str.SV_ULS_F32 | Single Precision Floating Point | -6.6667 | 6.6667 | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| PreDecelGain_Uls_M_f32 | Single Precision Floating Point | 1 | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |


**Table 3 (from source document):**


| Variable Name | Resolution | Legal Range<br/>(min) | Legal Range<br/>(max) | Software Segment |

| ADDCoef_MtrNmSpRad_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_UNSPECIFIED |

| DriverVelocity_MtrRadpS_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_UNSPECIFIED |

| FDDAttenOut_MtrNm_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_UNSPECIFIED |

| InertiaCompCalc_MtrNm_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_UNSPECIFIED |

| FiltFreqLUBlnd_RadpS_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_UNSPECIFIED |

| RawDecelGain_Uls_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |

| TbarVelFiltVal_HwDegpSec_D_f32 | Single Precision Floating Point | FULL | FULL | FRQDEPDMPNINRTCMP_START_SEC_VAR_CLEARED_32 |


**Table 4 (from source document):**


| Typedef Name | Element Name | User Defined Type | Legal Range<br/>(min) | Legal Range<br/>(max) |

| typedef struct filterCoef_T | b0_Uls_f32 | Float32 | FULL | FULL |

|  | b1_Uls_f32 | Float32 | FULL | FULL |

|  | b2_Uls_f32 | Float32 | FULL | FULL |

|  | a0_Uls_f32 | Float32 | FULL | FULL |

|  | a1_Uls_f32 | Float32 | FULL | FULL |

|  | a2_Uls_f32 | Float32 | FULL | FULL |


**Table 5 (from source document):**


| Constant Name |

| k_InrtCmp_MtrInertia_KgmSq_f32 |

| t_InrtCmp_ScaleFactorTblY_Uls_u9p7[12] |

| k_InrtCmp_TBarVelLPFKn_Hz_f32 |

| t_InrtCmp_TBarVel_ScaleFactorTblY_Uls_u9p7[12] |

| k_InrtCmp_MtrVel_ScaleFactor_Uls_f32 |

| t_FDD_ADDStaticTblY_MtrNmpRadpS_um1p17[10] |

| t2_FDD_ADDRollingTblYM_MtrNmpRadpS_um1p17[2][10] |

| t_FDD_BlendTblY_Uls_u8p8[6] |

| t2_FDD_FreqTblYM_Hz_u12p4[2][12] |

| t_FDD_AttenTblX_MtrRadpS_u12p4[2] |

| t_FDD_AttenTblY_Uls_u8p8[2] |

| t_WIRBlndTblX_MtrNm_u8p8[5] |

| t_RIAstWIRBlndTblY_Uls_u2p14[5] |

| t_DmpFiltKpWIRBlndY_Uls_u2p14[5] |

| t_DmpDecelGainSlewY_UlspS_u13p3[6] |

| t_DmpDecelGainSlewX_MtrRadpS_u11p5[6] |

| k_DmpGainOnThresh_KphpS_f32 |

| k_DmpDecelGain_Uls_f32 |

| k_DmpDecelGainFSlew_UlspS_f32 |

| k_DmpGainOffThresh_KphpS_f32 |

| t_CmnVehSpd_Kph_u9p7[12] |

| t_FddADDCoefTblX_MtrNm_u4p12[10] |

| k_CmnTbarStiff_NmpDeg_f32 |

| k_CmnSysKinRatio_MtrDegpHwDeg_f32 |


**Table 6 (from source document):**


| Constant Name | Resolution | Units | Value |

| D_FDDADDCOEFTBLSIZE_ULS_U8 | uint8 | Uls | 24U |

| D_FLOATEIGHT_ULS_F32 | Float32 | Uls | 8.0F |

| D_FLOATFOUR_ULS_F32 | Float32 | Uls | 4.0F |

| D_FLOATTWO_ULS_F32 | Float32 | Uls | 2.0F |

| D_ATTENTBLMAXINPUT_MTRRADPS_F32 | Float32 | MtrRadpS | 4095.9375 |

| D_ATTENTBLMININPUT_MTRRADPS_F32 | Float32 | MtrRadpS | 0.0 |


**Table 7 (from source document):**


| Constant Name |

| D_ONE_ULS_F32 |

| D_PIOVR180_ULS_F32 |

| D_2MS_SEC_F32 |

| D_2PI_ULS_F32 |

| D_MTRTRQCMDHILMT_MTRNM_F32 |

| BC_FREQDEPDAMPING_FAULTINJECTIONPOINT |

| FLTINJ_INERTIACOMP |


**Table 8 (from source document):**


| Constant Name | Resolution | Value | Software Segment |

|  |  |  |  |
