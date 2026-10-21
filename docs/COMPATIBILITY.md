# Compatibility & testing

[Home](../README.md) · [User guide](USER-GUIDE.md) · [Release status](../releases/README.md)

Personal Edition targets the **AKAI S5000 and S6000**, using the shared v2.14 operating-system foundation. Auto Sample uses the sampler's MIDI outputs and recording inputs. USB is not required for the sampling workflow.

## What is available here?

This repository currently contains documentation and artwork. **No firmware BIN or installation archive has been published here.** The illustrated guide describes the current development feature set; it is not an announcement that a final release has passed every hardware test.

## Verification status

| Area | Current evidence |
| --- | --- |
| Earlier Auto Sample / Personal Edition builds | User-reported operation on both S5000 and S6000. |
| Earlier corrected floppy installer | A successful floppy flash and reboot was reported. |
| Current GUI-cleanup candidate | Passed 15 software verification suites and a scoped independent review. A complete physical test of this exact candidate is still pending. |
| Current floppy and USB installation paths | Passed bounded software checks for writing, read-back verification and restart. |
| Windows / ak.Sys USB installation | Actual host-to-sampler installation remains unverified. |

The software checks exercise native firmware routines with controlled inputs and device models. They are not a complete sampler emulator and do not establish risk-free flashing. Future downloads will carry their own exact build identity, installation instructions and hardware-test status.

## Before a capture session

- Create a new, empty program and name it before opening Auto Sample.
- Leave generous free sample RAM. Longer recordings, stereo, additional velocities and temporary loop-processing copies need more space.
- Test the input level and attack on one note before capturing a large range.
- Avoid simultaneous sample editing through ak.Sys or SysEx while Auto Loop is running.
- Save the program **with its samples** through the normal SAVE page before switching off.

Auto Loop is optional and cannot guarantee a clean musical loop for every sound. Recordings that fail the normal loop checks are kept in their original form for review. See the [loop guide](USER-GUIDE.md#6-loop-the-sustained-part) for cropping and release-tail behaviour.

## Loading and installation

Use the instructions supplied with the specific future release. For current development testing, the established first step is a temporary floppy boot followed by **NO** at the “Write Flash OS” prompt, then checking the feature before considering a permanent installation.

USB updating and temporary floppy booting are separate operations. **USB boot without installation is not an advertised feature.** No new installation should be attempted using these preview documents alone.

## About the images

The screen captures were produced by the current firmware's native rendering routines. They show the implemented menus at the original 320 × 240 resolution. The program name, settings and progress figures are examples; the images do not claim that an illustrated capture was recorded on physical hardware.

The landing-page waveform is decorative artwork. It does not represent a loop-search display or an audio measurement.
