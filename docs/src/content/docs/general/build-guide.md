---
title: "Build guide"
description: "How the firmware sources, generated code and tools fit together."
---

# Build guide

:::caution[Host assumption]
The build wiring in this repository is Windows batch based (`*_Generate.bat`, `Integrate.bat`, `RteGen.bat`, `postbuild.bat`) and expects the Vector DaVinci / MICROSAR toolchains plus the Texas Instruments compiler. The steps below describe the intended flow; they were reconstructed from the batch files and generator templates, not executed here.
:::

## 1. Generate

Each software component keeps its AUTOSAR description (`autosar/*.dcf`, `*.arxml`) and generator templates (`generate/*.tt`). A per-module `Generate` batch file expands the templates into `*_Cfg.h/.c` and proxy files. Project-wide generation (Runtime Environment, Basic Software configuration) lives in the system integration project under `Tools/AsrProject`.

## 2. Integrate

Per-module `Integrate.bat` copies the component sources, headers and generated configuration into the integration project tree (`SwProject/Source/...`). The top-level `postbuild.bat` finishes the link step with `Linker.cmd`.

## 3. Compile and link

Sources are C (plus a small amount of assembler for startup and trigonometric helpers) targeting the TMS570 with the Texas Instruments compiler. Static-analysis presets for QA-C are stored in the static analysis configuration folder.

## 4. Calibrate and measure

The Universal Measurement and Calibration Protocol interface module and the diagnostics communication helpers expose calibration constants (`Generated Configuration Data/CalConstants.*`) for tooling.

## What lives where

- Component sources: `<Module>/src/*.c`, public headers in `<Module>/include/` where present.
- AUTOSAR descriptions: `<Module>/autosar/`.
- Generator templates and batch wiring: `<Module>/generate/`, `<Module>/tools/`.
- Integration output: system integration project, `SwProject/Source/...`.
- Documentation sources for this site: `docs/src/content/docs/`.
