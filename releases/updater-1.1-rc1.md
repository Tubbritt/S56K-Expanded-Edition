# S56K Firmware Updater 1.1 RC1

[Home](../README.md) · [Downloads](README.md) · [Release history](../CHANGELOG.md) · [Windows USB guide](../docs/USB-UPDATER.md) · [Compatibility](../docs/COMPATIBILITY.md)

**Install Expanded Edition V1.2 from Windows 11.** This standalone x64 USB updater recognises the exact published V1.2 and V1.1 BINs while retaining support for Expanded V1 and original Akai OS 2.14. It fixes the older updater's rejection of the newer firmware.

**4 November 2026 · Release candidate · Unsigned · Requires IB-S56USB and WinUSB**

**[Download Windows updater ZIP](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.1-rc1/releases/updater/1.1-rc1/S56K-Firmware-Updater-1.1-RC1-win64.zip)** · **[SHA256SUMS.txt](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.1-rc1/releases/updater/1.1-rc1/SHA256SUMS.txt)** · **[Download V1.2 firmware separately](v1.2.md)**

## Changes from 1.0 RC1

- **Added Expanded Edition V1.2 and V1.1.** The exact released BINs are now recognised. Original Akai v2.14 and Expanded V1 remain supported.
- **Shows the selected edition.** File validation, installation confirmation and reports identify the recognised firmware edition.
- **Added USB driver setup assistance.** The app can identify a present Akai device even if its current driver cannot be used. Choose the sampler and **Change Windows driver…** to open Microsoft's driver wizard. This action requests administrator approval and checks the selected device again; it does not silently install a driver.
- **Updated the included guide and notices.** The ZIP includes setup instructions, a README, the Freeware Licence, disclaimer, third-party notices, icons and file checksums.

The updater remains a separate application. It does not require ak.Sys, and firmware installation is not added to the Editor. No firmware BIN is bundled in the ZIP. The published V1.2 firmware itself has not changed.

## Supported firmware

All supported images are exactly **1,048,576 bytes**. The complete SHA-256 identifies the edition, regardless of filename:

| Image | SHA-256 |
| --- | --- |
| Expanded Edition V1.2 | `e29e16a1c9dde87dd5ac543bed3ff2d195b56931765cc24b84ba7dfb4a767474` |
| Expanded Edition V1.1 | `cc3f6c056e0fb032303ee61f2e16c419c22708377cf888f0c1737be74321df93` |
| Expanded Edition V1 / EX artwork revision 2 | `5b2559d3137f29516130572c754c5cf1be45058a25d70cff5fbbc221944e7f2a` |
| Original Akai OS 2.14 | `05e466a7a19e5abde1e53660e0069bf2fb34bb33f705841185883a78b5369402` |

The full-file checks and fixed in-memory copy remain in place. Unknown, corrupted and private test images are rejected before any update command is sent. The factory image is recognised for restoration but is not included in these downloads. All supported images retain the underlying Akai identity **2.14**; the Expanded edition caption distinguishes them after reboot.

## Installation

Extract the complete ZIP and read `START_HERE.html`. Start with a freshly booted sampler and no loaded libraries. Close the Editor, ak.Sys and other USB tools. Connect, choose the BIN and check the model and edition before confirming **Install firmware**.

USB installation writes flash and stored settings. Keep power and USB connected until completion. There is no safe cancellation after erasure starts. After success, save the report, remove any firmware floppy and restart. For V1.2, confirm **EXPANDED EDITION V1.2** on the boot screen and check ordinary operation. Close and reopen the app before another installation.

Follow the [illustrated USB guide](../docs/USB-UPDATER.md) for WinUSB setup and the complete workflow. [Floppy installation](../docs/INSTALLATION.md) remains available.

## Verification

Automated file checks accepted all four approved images and rejected 36 altered-image cases. All **32 host/native-firmware cases** passed: 16 combinations of running and target firmware, plus 16 CRC, retry, erase and programming-failure cases. Startup checks passed for all four resulting images.

The actual Windows executable was exercised under Wine. It accepted all four files with the correct edition labels, rejected a corrupted V1.2 BIN and a wrong-size file, kept installation disabled without a connected sampler, and passed driver-assistant, recheck, report-saving and shutdown checks. Ten WinUSB wrapper cases and the driver-helper tests also passed. These are controlled software tests; they do not reproduce physical flash electronics or every USB timing condition.

The earlier physical USB round-trip used updater **1.0 RC1**, Expanded **V1** and original Akai **v2.14** on the established S6000 / Windows 11 Pro 25H2 setup. The owner separately confirmed flashing the V1.2 firmware after receiving the floppy procedure. Those reports are retained as historical evidence; they are not a physical USB test of updater 1.1 RC1 or a real Windows driver-assignment test. See the [compatibility record](../docs/COMPATIBILITY.md).

The completion message reports the sampler's acknowledgements. It does not independently read back the complete flash or verify reboot. The running sampler OS performs programming, so a factory OS still has its original allocation and comparison limitations until the new OS runs.

## Package identity

**S56K-Firmware-Updater-1.1-RC1-win64.zip** — **1,050,167 bytes**

SHA-256:

```text
912ee879386676ac6a159a271e7d1f27115988a51bf644eb254224be806372c1
```

The ZIP includes internal checksums for every bundled file. It contains the standalone application and documentation, with no firmware, development source or test transport. Previous updater packages remain identifiable under their original tags and checksums.

## Practical notes

- Windows 11 on Intel/AMD x64, an IB-S56USB card and Microsoft WinUSB are required. Assigning WinUSB may affect the original ak.Sys driver association.
- The app is unsigned. Download from this repository and check the checksum; do not disable Windows security or driver-signature enforcement.
- The app blocks its own Close action during installation and asks Windows to stay awake. This cannot prevent power loss, forced termination or every USB interruption.
- The boot block is excluded, but there is no automatic rollback or guaranteed recovery. If an update fails after erasure may have started, leave the sampler powered on initially and save the report before further attempts.

Read the [disclaimer](../DISCLAIMER.md), [Freeware Licence](../LICENSE.md) and [third-party notices](../THIRD-PARTY-NOTICES.md). The app is free for personal and professional use. Firmware and application development source remains private and is not published.
