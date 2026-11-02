# S56K Expanded Edition · Compatibility

[Home](../README.md) · [User guide](USER-GUIDE.md) · [Installation](INSTALLATION.md) · [USB updater](USB-UPDATER.md) · [Downloads](../releases/README.md)

**S56K Expanded Edition V1.1** is designed for the **AKAI S5000 and S6000**, using their shared v2.14 operating-system foundation. One model-aware firmware image supplies the features and appropriate startup artwork for each sampler.

Auto Sample uses the sampler's MIDI outputs and recording inputs. USB is not required for the sampling workflow. The visible **EXPANDED EDITION V1.1** label identifies this project's additions; the underlying OS/settings/protocol identity remains **2.14**.

## Current downloads

| Download | Supported use |
| --- | --- |
| **[Expanded Edition V1.1 — S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/releases/download/expanded-v1.1/S56K-EX.bin)** | Shared S5000/S6000 firmware. Temporary floppy loading or permanent floppy installation. |
| **[Firmware Updater 1.0 RC1](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.0-rc1/releases/updater/1.0-rc1/S56K-Firmware-Updater-1.0-RC1-win64.zip)** | Standalone Intel/AMD Windows x64 app; IB-S56USB card and WinUSB required. Accepts only original Expanded Edition v1 and factory Akai v2.14. **Rejects V1.1.** |

V1.1 firmware SHA-256: `cc3f6c056e0fb032303ee61f2e16c419c22708377cf888f0c1737be74321df93`.

Updater ZIP SHA-256: `bcb49f0354e3a9b5eaf043ed17b8a346bb5acf6a35193d3ec9cef33f0566375c`.

**Use floppy to install V1.1.** The updater has not changed with this firmware release. Its historical USB success does not add the new BIN to its supported-file list.

## Verification evidence

| Area | Evidence and limits |
| --- | --- |
| **V1.1 floppy installation** | On **2 November 2026**, the owner reported “Flashing worked” after receiving the exact V1.1 BIN and floppy-only test procedure. The report did not restate the sampler model or separately confirm each cold-boot/checklist step. This is a successful reported flash, not separate evidence for both models. |
| **V1.1 software verification** | All **16** software-verification suites passed for the exact published BIN, followed by independent review. Checks cover startup, layout, both model boot-render paths, recording, monitoring, looping, cancellation and installer behavior. Bounded emulation and peripheral fixtures do not reproduce every hardware or timing condition. |
| **Pre-release operation** | The owner reported the preceding private T2 build working very well. V1.1 changes only its boot caption and text pointer; executable code and memory layout are identical. The feedback did not restate the model or itemise individual tests. |
| **Earlier Auto Sample on S5000 and S6000** | Successful operation was reported on both models during feature development. This historical result does not separately establish V1.1 flashing on both. |
| **Standalone Windows updater: hardware** | On **23 October 2026**, the owner confirmed an **Expanded Edition v1 → original Akai v2.14 → Expanded Edition v1** USB round-trip after receiving the reboot and visual-check procedure. The established setup was **S6000 / Windows 11 Pro 25H2**. No separate S5000 USB or V1.1 USB result is established by that test. |
| **Standalone Windows updater: software** | Seven native-firmware integration cases, portable protocol tests, ten WinUSB-wrapper cases and GUI checks passed for the unchanged updater. Its supported-file checks still reject V1.1. |
| **Windows / ak.Sys installation** | The standalone updater does not require ak.Sys. Successful use of it does not verify firmware installation through ak.Sys. |
| **Other hosts and configurations** | Windows on ARM, other Windows versions and wider USB-card/host combinations have not been verified. The app is unsigned and remains version 1.0 RC1. |

These hardware results are owner reports. They are not independent flash readback, recorded failure-recovery tests or guarantees for every machine. The published V1.1 BIN is byte-for-byte the file supplied for the reported flash test; its identity is established by the full SHA-256 checksum.

The running sampler OS performs erasure and programming. Factory v2.14 retains its older allocation and final-byte comparison limitations until the new OS is running. Start an installation with a freshly booted sampler and no loaded libraries. Flashing can replace stored settings, and there is no automatic rollback or guaranteed recovery. Read the [flashing disclaimer](../DISCLAIMER.md).

## Before a capture session

- Create a new, empty program and name it before opening Auto Sample.
- Leave generous free sample RAM. Longer recordings, stereo, additional velocities and temporary loop-processing copies need more space.
- Test the input level and attack on one note before capturing a large range.
- Avoid simultaneous sample editing through ak.Sys, the Editor or SysEx while Auto Loop is running.
- Save the program **with its samples** through the normal SAVE page before switching off.

Auto Loop is optional. Results depend on the sound; recordings that fail normal loop checks retain their original audio for review. With **CROP AFTER LOOP OFF**, successful processing preserves the full recorded release. The program's amplitude envelope still determines the audible release. Crossfade may be shortened to protect that audio. See the [loop guide](USER-GUIDE.md#6-loop-the-sustained-part).

V1.1 reserves **4 KiB more CPU RAM than v1**; sample RAM capacity is unchanged. Input monitoring can pause during loop processing and between recordings. The original allocator can wait when its internal memory pools are exhausted, temporarily preventing the UI from responding; this release does not replace that allocator. The original issue reporter's unexplained STOPPED event has not been conclusively attributed, so this update documents specific corrected paths without claiming to resolve every possible stop.

## Loading and installation

The [installation guide](INSTALLATION.md) separates temporary floppy loading from permanent floppy installation. Confirm **EXPANDED EDITION V1.1** on the actual installation boot before choosing **YES** at **Write Flash OS**. The prompt alone can also appear when an older installed OS has booted.

After successful permanent installation, remove the firmware floppy before restarting to verify the image stored in flash. The official **2.14** version field does not distinguish these editions: check the full V1.1 caption.

The [USB guide](USB-UPDATER.md) covers WinUSB driver setup and the unchanged updater's supported **older** images. It is not a V1.1 USB installation procedure.

## About the images

The screen gallery uses native firmware renders at the original **320 × 240** resolution. Program names, settings and progress figures are examples; actual physical LCD appearance varies.

The landing-page studio image is presentation artwork. It illustrates the two sampler models and workflow, rather than documenting a hardware test or measured audio result.
