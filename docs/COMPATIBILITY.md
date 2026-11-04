# S56K Expanded Edition · Compatibility

[Home](../README.md) · [User guide](USER-GUIDE.md) · [Installation](INSTALLATION.md) · [USB updater](USB-UPDATER.md) · [Downloads](../releases/README.md)

**S56K Expanded Edition V1.2** is designed for the **AKAI S5000 and S6000**, using their shared v2.14 operating-system foundation. One model-aware firmware image supplies the features and appropriate startup artwork for each sampler.

Auto Sample uses the sampler's MIDI outputs and recording inputs. USB is not required for the sampling workflow. The visible **EXPANDED EDITION V1.2** label identifies this project's additions; the underlying OS/settings/protocol identity remains **2.14**.

## Current downloads

| Download | Supported use |
| --- | --- |
| **[Expanded Edition V1.2 — S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.2/releases/firmware/v1.2/S56K-EX.bin)** | Shared S5000/S6000 firmware. Temporary floppy loading, permanent floppy installation or USB installation with updater 1.1 RC1. |
| **[Firmware Updater 1.1 RC1](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.1-rc1/releases/updater/1.1-rc1/S56K-Firmware-Updater-1.1-RC1-win64.zip)** | Standalone Intel/AMD Windows x64 app; IB-S56USB card and WinUSB required. Accepts the exact published Expanded V1.2, V1.1 and V1 images, plus original Akai v2.14. Includes USB driver setup assistance. |

V1.2 firmware SHA-256: `e29e16a1c9dde87dd5ac543bed3ff2d195b56931765cc24b84ba7dfb4a767474`.

Updater 1.1 RC1 ZIP SHA-256: `912ee879386676ac6a159a271e7d1f27115988a51bf644eb254224be806372c1`.

**Use updater 1.1 RC1 for V1.2 USB installation, or use floppy.** The older 1.0 RC1 app accepts only Expanded V1 and original Akai v2.14. Each supported BIN is checked against its full SHA-256; unknown or modified images remain rejected.

## Verification evidence

| Area | Evidence and limits |
| --- | --- |
| **V1.2 floppy installation** | On **4 November 2026**, the owner confirmed “flashing works” in response to the supplied V1.2 flash-and-reboot test. The confirmation did not restate the sampler model or itemise each check. It does not separately establish flashing on both models or installation over USB. |
| **V1.2 software verification** | All **20** software-verification suites passed for the exact published BIN, followed by independent review. They include memory recovery, cancellation, startup, both model boot-render paths, recording, native loop processing and flash paths. Bounded emulation and peripheral fixtures do not reproduce every hardware or timing condition. |
| **V1.2 pre-release operation** | The owner reported that the preceding private D2 recovery build was stable and Record Arm was working. V1.2 changes only two version-label strings from D2; instructions and memory layout are identical. No exact run counts or durations were supplied in that confirmation. |
| **V1.1 floppy installation** | On **2 November 2026**, the owner reported “Flashing worked” after receiving the exact V1.1 BIN and floppy-only test procedure. The report did not restate the sampler model or separately confirm each cold-boot/checklist step. This is a successful reported flash, not separate evidence for both models. |
| **V1.1 software verification** | All **16** software-verification suites passed for the exact published BIN, followed by independent review. Checks cover startup, layout, both model boot-render paths, recording, monitoring, looping, cancellation and installer behavior. Bounded emulation and peripheral fixtures do not reproduce every hardware or timing condition. |
| **V1.1 pre-release operation** | The owner reported the preceding private T2 build working very well. V1.1 changes only its boot caption and text pointer; executable code and memory layout are identical. The feedback did not restate the model or itemise individual tests. |
| **Earlier Auto Sample on S5000 and S6000** | Successful operation was reported on both models during feature development. This historical result does not separately establish V1.2 flashing on both. |
| **Updater 1.0 RC1: earlier hardware test** | On **23 October 2026**, the owner confirmed an **Expanded Edition v1 → original Akai v2.14 → Expanded Edition v1** USB round-trip after receiving the reboot and visual-check procedure. The established setup was **S6000 / Windows 11 Pro 25H2**. No separate S5000 USB, V1.1 USB or V1.2 USB result is established by that test. |
| **Updater 1.1 RC1: software verification** | All four approved firmware images passed exact-file validation; 36 altered-image cases were rejected. All 32 host/native-firmware cases passed, covering 16 running/target combinations and 16 transfer-failure cases, with startup checks for all four resulting images. The actual Windows executable passed file-selection, edition-label, rejection, report and driver-assistant checks under Wine. WinUSB wrapper and driver-helper fixtures also passed. These are controlled software checks, not physical USB or flash tests. |
| **Updater 1.1 RC1: hardware scope** | No new physical USB round-trip or real Windows driver reassignment is claimed for this app. The V1.2 hardware flashing confirmation above used the supplied floppy procedure; the earlier USB result belongs to updater 1.0 RC1. |
| **Windows / ak.Sys installation** | The standalone updater does not require ak.Sys. Successful use of it does not verify firmware installation through ak.Sys. |
| **Other hosts and configurations** | Windows on ARM, other Windows versions and wider USB-card/host combinations have not been verified. The current updater is unsigned and remains a release candidate, version 1.1 RC1. |

These hardware results are owner reports. They are not independent flash readback, recorded failure-recovery tests or guarantees for every machine. The published V1.2 BIN is byte-for-byte the file supplied for the reported flash test; its identity is established by the full SHA-256 checksum.

The running sampler OS performs erasure and programming. Factory v2.14 retains its older allocation and final-byte comparison limitations until the new OS is running. Start an installation with a freshly booted sampler and no loaded libraries. Flashing can replace stored settings, and there is no automatic rollback or guaranteed recovery. Read the [flashing disclaimer](../DISCLAIMER.md).

## Before a capture session

- Create a new, empty program and name it before opening Auto Sample.
- Leave generous free sample RAM. Longer recordings, stereo, additional velocities and temporary loop-processing copies need more space.
- Test the input level and attack on one note before capturing a large range.
- Close ak.Sys, the Editor and other sampler-control applications during Auto Sample to avoid concurrent recording or memory operations.
- Save the program **with its samples** through the normal SAVE page before switching off.

Auto Loop is optional. Results depend on the sound; recordings that fail normal loop checks retain their original audio for review. With **CROP AFTER LOOP OFF**, successful processing preserves the full recorded release. The program's amplitude envelope still determines the audible release. Crossfade may be shortened to protect that audio. See the [loop guide](USER-GUIDE.md#6-loop-the-sustained-part).

V1.2 reserves **8 KiB more CPU RAM than V1.1**; sample RAM capacity is unchanged. It waits for background sample-memory cleanup and can request native memory organisation when recording workspace is insufficient. After cleanup and a fresh space check, a specific temporary recording-memory error may be retried once. Completed recordings are retained. This corrects the observed Record Arm failure path; genuine insufficient sample RAM and other recorder errors can still stop a run.

Memory organisation can take time, and cancellation waits for the owned cleanup to finish. If cleanup cannot be confirmed and a restart-required fault is displayed, do not start another capture. Save completed work through the ordinary controls if they remain responsive, and restart. Input monitoring can pause during processing and between recordings. The original allocator can also wait when its internal memory pools are exhausted; V1.2 does not replace that allocator or guarantee recovery from every memory condition.

## Loading and installation

The [installation guide](INSTALLATION.md) separates temporary floppy loading from permanent floppy installation. Confirm **EXPANDED EDITION V1.2** on the actual installation boot before choosing **YES** at **Write Flash OS**. The prompt alone can also appear when an older installed OS has booted.

After successful permanent installation, remove the firmware floppy before restarting to verify the image stored in flash. The official **2.14** version field does not distinguish these editions: check the full V1.2 caption.

The [USB guide](USB-UPDATER.md) covers driver setup and V1.2 installation using updater **1.1 RC1**, including its exact-file checks and reboot verification. The same app retains support for the earlier approved images.

## About the images

The screen gallery uses native firmware renders at the original **320 × 240** resolution. Program names, settings and progress figures are examples; actual physical LCD appearance varies.

The landing-page studio image is presentation artwork. It illustrates the two sampler models and workflow, rather than documenting a hardware test or measured audio result.
