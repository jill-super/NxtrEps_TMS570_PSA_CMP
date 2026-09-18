---
title: "Flash Memory Driver (F021 Flash Application Programming Interface) (`Fls`)"
description: "Low-level Flash access (Texas Instruments F021 driver)."
---

# Flash Memory Driver (F021 Flash Application Programming Interface) (`Fls`)

:::caution[Origin: Third-party — Texas Instruments]
Source headers carry Texas Instruments proprietary notices (Flash EEPROM Emulation / F021 Flash Application Programming Interface). Vendor material under `doc/` is redistributed under the vendor licence.
:::

## Purpose and responsibility

Low-level Flash access (Texas Instruments F021 driver). It belongs to the **Microcontroller Abstraction Layer** layer.

## Key files

- Implementation: `src/F021_API_CortexR4_BE_V3D16.lib`
- Public headers: `include/CGT.ARM.h`, `include/CGT.CCS.h`, `include/CGT.GHS.h`, `include/CGT.IAR.h`, `include/CGT.gcc.h`, `include/Compatibility.h`, `include/Constants.h`, `include/F021.h`, `include/FapiFunctions.h`, `include/Helpers.h`, `include/Registers.h`, `include/Registers_FMC_BE.h`, `include/Registers_FMC_LE.h`, `include/Types.h`

## Public interface and runnables

No runnable-style entry points were detected by the source scan (library, driver or configuration-only module). See the design documents and headers for the call interface.

## Dependencies (internal includes)

- `CGT.ARM.h`
- `CGT.CCS.h`
- `CGT.GHS.h`
- `CGT.IAR.h`
- `CGT.gcc.h`
- `Compatibility.h`
- `Constants.h`
- `FapiFunctions.h`
- `Helpers.h`
- `Registers.h`
- `Registers_FMC_BE.h`
- `Registers_FMC_LE.h`
- `Types.h`

## Configuration and calibration

Check `generate/*.tt` templates and the generated `*_Cfg.h/.c` in the integration project (`SwProject/Source/Generated Configuration Data`) for this component's calibration. The [build guide](../general/build-guide/) explains the generate → integrate → compile flow.

## Design documents

| Document | Conversion | Size | Source in repository |
|---|---|---|---|
| | [F021_Flash_API_License_Agreement](./doc-F021_Flash_API_License_Agreement/) | converted | 44,099 bytes | `Fls/doc/F021_Flash_API_License_Agreement.pdf` |
| | [Release_Notes](./doc-Release_Notes/) | converted | 286,491 bytes | `Fls/doc/Release_Notes.pdf` |
| | [SPNA148](./doc-SPNA148/) | converted | 54,935 bytes | `Fls/doc/SPNA148.pdf` |
| | [SPNU501F](./doc-SPNU501F/) | converted | 167,634 bytes | `Fls/doc/SPNU501F.pdf` |
| | [SPNZ210](./doc-SPNZ210/) | converted | 42,058 bytes | `Fls/doc/SPNZ210.pdf` |
| | [build_information](./doc-build_information/) | converted | 197,284 bytes | `Fls/doc/build_information.txt` |
| | [readme](./doc-readme/) | converted | 756 bytes | `Fls/doc/readme.txt` | |

## Verification and safety notes

- No `utp/` evidence folder was found for this module.

