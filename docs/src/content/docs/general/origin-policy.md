---
title: "Vector vs in-house code"
description: "How to tell Vector-provided, third-party and in-house code apart."
---

# Vector vs in-house code

## The rule

| Badge on a module page | Meaning | How to verify |
|---|---|---|
| Custom (in-house) | Control logic written for this controller (Nexteer copyright). | Open the module `src/*.c`: logic files carry the in-house copyright. A `Generator: MICROSAR RTE Generator` banner only means the file template was expanded by Vector tooling. |
| Vector-provided | Vector MICROSAR Basic Software, Runtime Environment or DaVinci-generated configuration. | Headers carry `Copyright … by Vector Informatik GmbH` and workspaces point at `*.dcf` / DaVinci paths. |
| Third-party — Texas Instruments | Flash drivers and device headers. | `Copyright Texas Instruments` banners; vendor PDFs in `doc/`. |
| Third-party — TTTech | Watchdog stack. | `Copyright TTTech Automotive GmbH` banners. |
| Third-party — Gliwa | Timing-trace library. | Prebuilt archives plus a thin application interface. |

## Why most files mention both Nexteer and Vector

Application and sensor/actuator components are generated from a Vector template (hence the MICROSAR licence line in the header) and then filled with in-house control code (hence the in-house copyright and version history below it). The behaviour — gains, limits, state machines, diagnostics — is in-house; the template (include guards, memory mapping, generator version log) is Vector. Module pages therefore badge these components **Custom (in-house)** and call out the generator template explicitly.

## Folders that are always third-party or generated

- `SwProject/Source/Basic Software/*` (except the Microcontroller Unit driver adaptation): Vector MICROSAR.
- `SwProject/Source/Generated Configuration Data*`, `GenDataRte`: DaVinci / Runtime Environment Generator output — Vector-provided, do not edit by hand.
- `Fee/src/Device_*`, `Fls/`: Texas Instruments.
- `Source/Basic Software/Wdg*`: TTTech.
- `GliwaT1/*.a`: Gliwa.
