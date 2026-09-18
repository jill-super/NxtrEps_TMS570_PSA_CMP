---
title: "Active Pull Compensation — Model Design Document: Active_Pull_Comp_MDD"
description: "Model Design Document for Active Pull Compensation (converted)."
---

# Active Pull Compensation — Model Design Document: Active_Pull_Comp_MDD

> Source: `ActivePull/doc/Active_Pull_Comp_MDD.docx` (2,162,924 bytes, modern Word). Converted automatically with `python-docx`: headings, lists and up to 8 tables preserved. Figures and embedded objects are not preserved — see the original file for those.

For

Active Pull Compensation

Prepared By:

Nexteer Automotive,

Saginaw, MI, USAChange History

Table of Contents

1	ActivePull  & High-Level Description	4

2	Design details of software module	5

2.1	Graphical representation of ActivePull	5

2.2	Data Flow Diagram	5

2.2.1	Module level DFD	5

2.2.2	Sub-Module level DFD	5

2.3	Component diagram	5

2.4	Variable Data Dictionary	5

2.4.1	User defined ‘typedef’ definition/declaration	5

2.4.2	Variable definition for enumerated types	5

2.5	Constant Data Dictionary	6

2.5.1	Program Constants	6

2.5.2	Module Specific Lookup Tables	6

2.6	Software Module Implementation	6

2.6.1	Sub-Module Functions	6

2.6.2	Interrupt Service Routines	8

2.6.3	_SCOMM () Functions	8

2.6.4	Module Internal (Local) Functions	10

2.6.5	Transition Functions	10

3	Known Limitations with Design	12

4	UNIT TEST CONSIDERATION	13

Appendix A	Abbreviations and Acronyms	14

Appendix B	Glossary	15

Appendix C	References	16

# ActivePull  & High-Level Description

The Active Pull Compensation Function corrects vehicle pull issues by compensating for HW torque offsets detected by the steering system. These torque offsets are classified as short-term and long-term, each of which is compensated for independently by the algorithm. When the compensation is applied, the need for the driver to provide a constant input torque to counter these offsets is reduced.

# Design details of software module

## Graphical representation of ActivePull

## Data Flow Diagram

### Module level DFD

N/A

### Sub-Module level DFD

N/A

## Component diagram

N/A

## Variable Data Dictionary

### User defined ‘typedef’ definition/declaration

N/A

### Variable definition for enumerated types

N/A

## Constant Data Dictionary

### Program Constants

#### Local Constants

Refer .m file

The filter constants were derived from the requirements in SF-09 in conjunction with the following filter analyses.  Note that the upper frequency limits defined in the requirements for some values were not achievable.  The data dictionary reflects the limits of both the requirements and the software limitations.

#### Global Constants

Refer .m file

### Module Specific Lookup Tables

None

## Software Module Implementation

<The detailed design of the function is provided in the FDD. The detail design shall only be add to the MDD when it is not provided in the FDD or the FDD is not adequate and clarification is needed.>

### Sub-Module Functions

#### Initialization sub-module ActivePull_Init1()

#### Design Rationale

This initialization function is used to set values that are based solely on calibrations and constants (values which will not change over the course of an ignition cycle).  This includes preliminary gain calculations, limits, and step sizesStore Module Inputs to Local copies

Refer to FDD

#### (Processing of function)………

Refer to FDD

#### Store Local copy of outputs into Module Outputs

Refer to FDD

#### Periodic sub-module ActivePull_Per1()

Refer ‘ActvPullCmpPer1’ block in the Simulink model.

#### Design Rationale

The requirements in SF-13 show a signal called Reset_Svc.  This is shown as an input flag to the function.  However, the reset service has been implemented as a service call.  In order to avoid any thread-based issues, the service sets a separate variable for each periodic (ResetPer1_Cnt_M_lgc, in this case) to TRUE.  Then, near the beginning of the execution of the periodic, this value is read.  If it has been set to true, it is immediately set to FALSE, and a local copy (ResetSvc_Cnt_T_lgc) is set to TRUE.  In this way, each periodic uses its own local copy just as the design dictates using the input signal.  The local copy will be set to true for one execution of each periodic function.

The SCom function to set the STComp is done in a similar fashion.  The Scom function sets SComSTCompSet_Cnt_M_lgc to TRUE and when ActivePull_Per1 finds this value set to TRUE, it sets it back to FALSE and uses SComSTComp_HwNm_M_f32 as the state variable (instead of STComp_HwNm_M_f32, as it normally would).  The state variable itself is never changed, but the output of the next execution of ActivePull_Per1 will reflect the new value.

#### Store Module Inputs to Local copies

Refer ‘ActvPullCmpPer1’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActvPullCmpPer1’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActvPullCmpPer1’ block in the Simulink model.

#### Periodic sub-module ActivePull_Per2()

Refer ‘ActvPullCmpPer2’ block in the Simulink model.

#### Design Rationale

None.

#### Store Module Inputs to Local copies

Refer ‘ActvPullCmpPer2’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActvPullCmpPer2’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActvPullCmpPer2’ block in the Simulink model.

#### Periodic sub-module ActivePull_Per3()

Refer ‘ActvPullCmpPer3’ block in the Simulink model.

#### Design Rationale

Note that the Scom functions will have no effect until the next execution of ActivePull_Per3, which could result in a propagation delay of up to 100 ms.

#### Store Module Inputs to Local copies

Refer ‘ActvPullCmpPer3’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActvPullCmpPer3’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActvPullCmpPer3’ block in the Simulink model.

#### Non Periodic sub-module {_NONPer()}

None

### Interrupt Service Routines

None

### _SCOMM () Functions

#### ActivePull_Scom_ReadParam ()

Refer ‘ActivePull_SCom_ReadParam’ block in the Simulink model.

#### Design Rationale

None

#### Store Module Inputs to Local copies

Refer ‘ActivePull_SCom_ReadParam’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActivePull_SCom_ReadParam’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActivePull_SCom_ReadParam’ block in the Simulink model.

#### ActivePull_Scom_Reset ()

Refer ‘ActivePull_SCom_Reset’ block in the Simulink model.

#### Design Rationale

None

#### Store Module Inputs to Local copies

Refer ‘ActivePull_SCom_Reset’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActivePull_SCom_Reset’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActivePull_SCom_Reset’ block in the Simulink model.

#### ActivePull_Scom_SetLTComp ()

Refer ‘ActivePull_SCom_Reset’ block in the Simulink model.

#### Design Rationale

This function helps to fulfill the requirement that the “Engineering interface tool shall provide ability to set state variable to desired value”.  The state variable itself will not be updated until the next time ActivePull_Per3 is run.

#### Store Module Inputs to Local copies

Refer ‘ActivePull_SCom_SetLTComp’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActivePull_SCom_SetLTComp’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActivePull_SCom_SetLTComp’ block in the Simulink model.

#### ActivePull_Scom_SetSTComp ()

Refer ‘ActivePull_SCom_SetSTComp’ block in the Simulink model.

#### Design Rationale

This function helps to fulfill the requirement that the “Engineering interface tool shall provide ability to set state variable to desired value”.  The state variable itself will not be updated until the next time ActivePull_Per1 is run.

#### Store Module Inputs to Local copies

Refer ‘ActivePull_SCom_SetSTComp’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActivePull_SCom_SetSTComp’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActivePull_SCom_SetSTComp’ block in the Simulink model.

### Module Internal (Local) Functions

#### Local Function ActvCmpEna_lgc

#### Design Rationale

Refer "Active Compensation Enable" Block in Simulink Model

Removed the display variable “PullCmp_STReset_Cnt_D_lgc” from the code because it is redundant with the module level variable “PullCmp_STReset_Cnt_M_lgc”.

#### Local Function CalcIntGain_f32

#### Design Rationale

Refer " Calculate Integrator Gains" Block in Simulink Model

### Transition Functions

#### ActivePull_Trns1()

Refer ‘ActivePull_Trns1’ block in the Simulink model.

#### Design Rationale

This function is run when entering the OPERATE state.  The timers associated with ActivePull_Per1 are initialized.

#### Store Module Inputs to Local copies

Refer ‘ActivePull_Trns1’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActivePull_Trns1’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActivePull_Trns1’ block in the Simulink model.

#### _Trns2()

Refer ‘ActivePull_Trns2’ block in the Simulink model.

#### Design Rationale

This function is run when entering the OFF state.

#### Store Module Inputs to Local copies

Refer ‘ActivePull_Trns2’ block in the Simulink model.

#### (Processing of function)………

Refer ‘ActivePull_Trns2’ block in the Simulink model.

#### Store Local copy of outputs into Module Outputs

Refer ‘ActivePull_Trns2’ block in the Simulink model.

# Known Limitations with Design

None

# UNIT TEST CONSIDERATION

INLINE functions defined in “GlobalMacro.h” are not unit tested

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


| Sl. No. | Description | Author | Version | Date |

| 1 | Initial MDD | LWW | 1.0 | 01Aug11 |

| 2 | Updated to SF-13 rev 001 (started from scratch) | OT | 2.0 | 02-Apr-12 |

| 3 | Fixed buffered reads in Reset Scom function (changed to direct reads) | OT | 3.0 | 18-Apr-12 |

| 4 | Removed PIM from Scom and made LT learned variable to a typH. Added support for FDAD Common manufacturing srvc DID | VK | 4.0 | 22-Apr-12 |

| 5 | Updates to meet SF-13 rev 002 | VK | 5.0 | 26-June-12 |

| 6 | Corrected module internal variable ranges | VK | 6.0 | 29-June-12 |

| 7 | 1) Removed VehSpdRate global input and made necessary changes in Per1<br/>2) Added VehicleSpeedRate logic in Per3 -Ver 003 updates<br/>3) Changed LPF from fixed to float | NRAR | 7.0 | 23-July-12 |

| 8 | Inserted safe watchdog checkpoints | BWL | 8.0 | 15-Sept-12 |

| 9 | Corrected  static variable to MDD format | SSK | 9.0 | 18-sep-12 |

| 10 | Updated calibration table Y datatype to u2p14 for anomaly correction, removed condition checks on SCom function | LWW | 10.0 | 20 Oct 12 |

| 11 | Anomaly 5379 fixed. | SP | 11.0 | 07-Aug-13 |

| 12 | Anomaly 5764 (to revert changes made as part of the previous Anomaly 5379 fix) | LK | 12.0 | 16-Apr-14 |

| 13 | Updated to version 4 and 5 of FDD - Added estimated lateral acceleration, Pull command Enable as a new inputs. And Updated to new template | SB | 13.0 | 09-Dec-15 |

| 14 | Updated the SCom function arguments section | SB | 14.0 | 02-May-16 |

| 15 | Added new Trans function | SB | 15.0 | 19-May-16 |

| 17 | Updated to SF13A FDD version 6.0.0 | SB | 17.0 | 05-Aug-16 |

| 18 | Updated to SF13A FDD version 6.2.0 | SR | 18.0 | 03-Oct-16 |

| 19 | Updated to SF13A FDD version 6.3.0 | KByrski | 19.0 | 24-Jan-17 |

|  |  |  |  |  |


**Table 2 (from source document):**


|  |  | Type | Min | Max | UTP Tol. |

| Arguments Passed | PullCompCmd_HwNm_f32<br/>STComp_HwNm_f32<br/>LTComp_HwNm_f32<br/>EnableLearn_Cnt_lgc | Float32<br/>Float32<br/>Float32<br/>Float32 | -8.8<br/>-10<br/>-10<br/>FALSE | 8.8<br/>10<br/>10<br/>TRUE |  |

| Return Value | None |  |  |  |  |


**Table 3 (from source document):**


|  |  | Type | Min | Max | UTP Tol. |

| Arguments Passed | None |  |  |  |  |

| Return Value | None |  |  |  |  |


**Table 4 (from source document):**


|  |  | Type | Min | Max | UTP Tol. |

| Arguments Passed | LTComp_HwNm_f32 | float32 | -10 | 10 |  |

| Return Value | None |  |  |  |  |


**Table 5 (from source document):**


|  |  | Type | Min | Max | UTP Tol. |

| Arguments Passed | STComp_HwNm_f32 | float32 | -10 | 10 |  |

| Return Value | None |  |  |  |  |


**Table 6 (from source document):**


| Function Name | ActvCmpEna_lgc | Type | Min | Max |

| Arguments Passed | HwTrqFilt_HwNm_T_f32,<br/>YawRateFilt_DegpS_T_f32,<br/>HandwheelPosition_HwDeg_T_f32,<br/>EstLatAcc_MpSecSq_T_f32,<br/>HandwheelVelocity_HwRadpS_T_f32,<br/>HandwheelAuthority_Uls_T_f32,<br/>VehicleSpeed_Kph_T_f32,<br/>VehicleSpeedValid_Cnt_T_lgc,<br/>DisableLearning_Cnt_T_lgc,<br/>DisableOutput_Cnt_T_lgc<br/>PullCmpCustLrngDi_Cnt_T_lgc | Float32<br/>Float32<br/>Float32<br/>Float32<br/>Float32<br/>Float32<br/>Float32<br/>Boolean<br/>Boolean<br/>Boolean<br/>Boolean | -10<br/>-120<br/>-1440.11<br/>-10<br/>-42<br/>0<br/>0<br/>FALSE<br/>FALSE<br/>FALSE<br/>FALSE | 10<br/>120<br/>1440.11<br/>10<br/>42<br/>1<br/>511<br/>TRUE<br/>TRUE<br/>TRUE<br/>TRUE |

|  |  |  |  |  |

| Return Value | EnableLearning_Cnt_T_lgc | Boolean | FALSE | TRUE |


**Table 7 (from source document):**


| Function Name | CalcIntGain_f32 | Type | Min | Max |

| Arguments Passed | HwTorque_HwNm_T_f32,<br/>PrevSTComp_HwNm_T_f32 | Float32<br/>Float32 | -10<br/>-10 | 10<br/>10 |

|  |  |  |  |  |

| Return Value | STIntGain_Uls_T_f32 | Float32 | 0 | 1 |


**Table 8 (from source document):**


| Abbreviation or Acronym | Description |

|  |  |

|  |  |
