# S56K Expanded Edition · Compatibility

[Home](../README.md) · [User guide](USER-GUIDE.md) · [Installation](INSTALLATION.md) · [USB updater](USB-UPDATER.md) · [Downloads](../releases/README.md)

**S56K Expanded Edition v1** is designed for the **AKAI S5000 and S6000**, using their shared v2.14 operating-system foundation. One model-aware firmware image supplies the features and appropriate startup artwork for each sampler.

Auto Sample uses the sampler's MIDI outputs and recording inputs. USB is not required for the sampling workflow. The visible **EXPANDED EDITION v1** label identifies this project's additions; the underlying OS/settings/protocol identity remains **2.14**.

## Current downloads

| Download | Supported use |
| --- | --- |
| **[Expanded Edition v1 — S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/download/expanded-v1/S56K-EX.bin)** | Shared S5000/S6000 firmware; current EX artwork revision 2. Temporary floppy loading or permanent installation. |
| **[Firmware Updater 1.0 RC1](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/download/updater-v1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip)** | Standalone Intel/AMD Windows x64 app; IB-S56USB card and WinUSB required. Permanent flash installation only. |

Firmware SHA-256: `5b2559d3137f29516130572c754c5cf1be45058a25d70cff5fbbc221944e7f2a`.

Updater ZIP SHA-256: `bcb49f0354e3a9b5eaf043ed17b8a346bb5acf6a35193d3ec9cef33f0566375c`.

## Verification evidence

| Area | Evidence and limits |
| --- | --- |
| **Auto Sample on S5000 and S6000** | Successful operation was reported on both models during feature development. This does not separately establish USB flashing on both. |
| **Permanent installation from floppy** | A successful flash and subsequent reboot were reported for an earlier corrected installer build. |
| **Current EX artwork firmware** | Passed all 15 firmware software-verification suites and a scoped independent review. It is the approved Expanded image supplied for the successful USB round-trip below; that report does not separately confirm the latest S5000 artwork on hardware. |
| **Standalone Windows updater: hardware** | On 2026-10-23, the owner confirmed successful **Expanded → original Akai v2.14 → Expanded** installation after receiving the reboot and visual-check procedure. The established setup was **S6000 / Windows 11 Pro 25H2**; the final confirmation did not restate the model. No separate S5000 USB result has been reported. |
| **Standalone Windows updater: software** | Seven native-firmware integration cases cover successful transfers and injected failures. Portable protocol tests, ten WinUSB-wrapper cases and GUI checks also passed. Those controlled tests complement the hardware report; they are not tests of every electrical or Windows failure. |
| **Windows / ak.Sys installation** | The new standalone updater does not require ak.Sys. The owner's success with it does not verify firmware installation through ak.Sys. |
| **Other hosts and configurations** | Windows on ARM, other Windows versions and wider USB-card/host combinations have not been verified. The app is unsigned and remains version 1.0 RC1. |

The hardware result is the owner's report of a successful round-trip on the supplied files. It is not independent flash readback, a recorded failure-recovery test or a guarantee for every machine. The published BIN and updater executable are unchanged from those supplied for that test. Firmware identity comes from the full SHA-256 checksum, not just the displayed version or filename.

The running sampler OS performs erasure and programming. Factory v2.14 has older allocation and final-byte comparison limitations; selecting Expanded firmware on the PC cannot retroactively repair those running routines. Start an update with a freshly booted sampler and no loaded libraries. Installation writes stored settings as well as the OS. The USB path preserves the boot block, but there is no automatic rollback or guaranteed recovery. Read the [flashing disclaimer](../DISCLAIMER.md).

## Before a capture session

- Create a new, empty program and name it before opening Auto Sample.
- Leave generous free sample RAM. Longer recordings, stereo, additional velocities and temporary loop-processing copies need more space.
- Test the input level and attack on one note before capturing a large range.
- Avoid simultaneous sample editing through ak.Sys or SysEx while Auto Loop is running.
- Save the program **with its samples** through the normal SAVE page before switching off.

Auto Loop is optional. Its native processing can prepare useful sustain loops, but results depend on the sound. Recordings that fail the normal loop checks retain their original audio for review. See the [loop guide](USER-GUIDE.md#6-loop-the-sustained-part) for cropping and release-tail behavior.

## Loading and installation

The [installation guide](INSTALLATION.md) separates temporary floppy loading from permanent flash installation. A temporary check uses a readable OS floppy and **NO** at the “Write Flash OS” prompt. The [USB guide](USB-UPDATER.md) covers WinUSB driver setup and permanent installation with the Windows app.

After any successful permanent installation, remove the firmware floppy before rebooting to verify the image stored in flash. Both factory and Expanded images retain the official **2.14** version: check the EX artwork and Auto Sample menu instead.

## About the images

The screen gallery uses native firmware renders at the original **320 × 240** resolution. Program names, settings and progress figures are examples; actual physical LCD appearance varies.

The landing-page studio image is presentation artwork. It illustrates the two sampler models and the workflow, rather than documenting a hardware test or measured audio result.
