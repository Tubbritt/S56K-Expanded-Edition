# S56K Expanded Edition · Compatibility

[Home](../README.md) · [User guide](USER-GUIDE.md) · [Installation](INSTALLATION.md) · [Release information](../releases/README.md)

**S56K Expanded Edition v1** is designed for the **AKAI S5000 and S6000**, using their shared v2.14 operating-system foundation. One model-aware firmware image supplies the features and the appropriate startup artwork for each sampler.

Auto Sample uses the sampler's MIDI outputs and recording inputs. USB is not required for the sampling workflow. The visible **EXPANDED EDITION v1** label identifies this project's additions; the underlying OS/settings/protocol identity remains **2.14**.

## Verification evidence

| Area | Evidence and limits |
| --- | --- |
| **Auto Sample on S5000 and S6000** | Successful operation was reported on both models during feature development. |
| **Permanent installation from floppy** | A successful flash and subsequent reboot were reported for an earlier corrected installer build. |
| **Current EX artwork image** | Passed all 15 software verification suites and a scoped independent review. The latest corrected logos and caption still await physical confirmation on both models. |
| **Floppy and USB flash routines** | Passed bounded software checks covering writing, read-back verification and restart behavior. This does not establish every real device or host configuration. |
| **Windows / ak.Sys USB installation** | End-to-end installation on hardware remains unverified. USB boot without installation is not a supported workflow. |

A successful earlier build does not certify every later image. Firmware downloads are identified by a SHA-256 checksum; consult the installation notes and verification status accompanying the exact file you use. The software checks exercise native routines with controlled inputs and device models, rather than a complete hardware emulator. No installation is guaranteed risk-free; read the [risk disclaimer](../DISCLAIMER.md).

## Before a capture session

- Create a new, empty program and name it before opening Auto Sample.
- Leave generous free sample RAM. Longer recordings, stereo, additional velocities and temporary loop-processing copies need more space.
- Test the input level and attack on one note before capturing a large range.
- Avoid simultaneous sample editing through ak.Sys or SysEx while Auto Loop is running.
- Save the program **with its samples** through the normal SAVE page before switching off.

Auto Loop is optional. Its native processing can prepare useful sustain loops, but results depend on the sound. Recordings that fail the normal loop checks retain their original audio for review. See the [loop guide](USER-GUIDE.md#6-loop-the-sustained-part) for cropping and release-tail behavior.

## Loading and installation

The [installation guide](INSTALLATION.md) separates temporary floppy loading from permanent flash installation. The established first check is to boot from a readable floppy and select **NO** at the “Write Flash OS” prompt. Confirm operation before considering a permanent update.

Firmware downloads are withheld from this repository at present. See [Release information](../releases/README.md) for availability. The guide and screenshots are documentation, not an alternative firmware download.

## About the images

The screen gallery uses native firmware renders at the original **320 × 240** resolution. Program names, settings and progress figures are examples; actual physical LCD appearance varies.

The landing-page studio image is presentation artwork. It illustrates the two sampler models and the workflow, rather than documenting a hardware test or measured audio result.
