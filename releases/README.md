# Downloads & releases

[Home](../README.md) · [Release history](../CHANGELOG.md) · [Installation](../docs/INSTALLATION.md) · [Windows USB guide](../docs/USB-UPDATER.md) · [Freeware licence](../LICENSE.md) · [Disclaimer](../DISCLAIMER.md)

## Choose your download

The operating system runs on your sampler. **Download V1.2 and install over USB with Firmware Updater 1.1 RC1, or from floppy.** The updated standalone app recognises original Akai v2.14 and Expanded V1, V1.1 and V1.2.

| Release | Download | Instructions |
| --- | --- | --- |
| **Expanded Edition V1.2** · S5000 / S6000 | [S56K-EX.bin](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.2/releases/firmware/v1.2/S56K-EX.bin) · 1 MiB | [Release notes](v1.2.md) · [Install](../docs/INSTALLATION.md) |
| **Firmware Updater 1.1 RC1** · Windows 11 x64 | [Windows ZIP](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.1-rc1/releases/updater/1.1-rc1/S56K-Firmware-Updater-1.1-RC1-win64.zip) · 1,050,167 bytes | [Release notes](updater-1.1-rc1.md) · [Driver setup & use](../docs/USB-UPDATER.md) |
| **Illustrated manual** | [PDF user guide](../docs/S56K-Expanded-Edition-User-Guide.pdf) | Sampling, looping, floppy installation and USB driver/update instructions |

The updater is a release candidate and is unsigned. The earlier user-confirmed S6000 / Windows 11 Pro 25H2 USB round-trip used updater 1.0 RC1 and Expanded V1. Newer supported images and the new driver assistant have software checks; a new physical USB round-trip is not claimed. The owner has confirmed successful V1.2 flashing after receiving the floppy flash-and-reboot procedure; model-specific and USB coverage are described in the compatibility record. An IB-S56USB card and WinUSB driver are required; USB is not needed for the firmware's sampling features. See [compatibility](../docs/COMPATIBILITY.md).

## Check your download

The V1.2 release links its **[SHA256SUMS.txt](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/expanded-v1.2/releases/firmware/v1.2/SHA256SUMS.txt)** in the tagged versioned download folder. The [updater checksum](https://github.com/Tubbritt/S56K-Expanded-Edition/raw/refs/tags/updater-v1.1-rc1/releases/updater/1.1-rc1/SHA256SUMS.txt) accompanies its new tagged download. The primary files are identified by these SHA-256 values:

**S56K-EX.bin** — 1,048,576 bytes

```text
e29e16a1c9dde87dd5ac543bed3ff2d195b56931765cc24b84ba7dfb4a767474
```

**S56K-Firmware-Updater-1.1-RC1-win64.zip** — 1,050,167 bytes

```text
912ee879386676ac6a159a271e7d1f27115988a51bf644eb254224be806372c1
```

In PowerShell, change to the download folder and run:

```powershell
Get-FileHash .\S56K-EX.bin -Algorithm SHA256
Get-FileHash .\S56K-Firmware-Updater-1.1-RC1-win64.zip -Algorithm SHA256
```

Letter case does not matter when comparing hashes. Stop if any character differs. A matching hash identifies the downloaded file; it is not a guarantee against an interrupted flash or a hardware fault.

## What is included

- The **V1.2 firmware release** links the shared OS BIN and checksum from the immutable `expanded-v1.2` tag in `releases/firmware/v1.2/`, plus the current PDF manual and notices. Use those named download links; the release has no separate binary attachments.
- The **updater 1.1 RC1 release** links the Windows app ZIP and its checksums in `releases/updater/1.1-rc1/`, plus the PDF manual. Extract the ZIP before running the app. Firmware is downloaded separately.
- The new ZIP includes the setup guide, README, icons, Freeware Licence, disclaimer, third-party notices and internal checksums. No firmware or development source is bundled.

[All GitHub Releases →](https://github.com/Tubbritt/S56K-Expanded-Edition/releases)

## About this repository

The [release history](../CHANGELOG.md) tracks the firmware and updater separately, with features, dates and links to each version's detailed notes. Previous versions remain identifiable by their tags and checksums. Documentation and licensing updates do not change the released binaries. See [Preparing the next release](../docs/RELEASE-PROCESS.md) for the publication checklist.

This repository distributes compiled downloads, documentation and artwork. Firmware and app source code, build tools and reverse-engineering material are maintained elsewhere. Firmware and updater downloads use immutable tagged copies in versioned **releases/** folders, linked from their GitHub Releases. The previous firmware BIN has been removed from the current repository files; its original tag and historical release remain intact.

GitHub automatically adds **“Source code” ZIP/TAR** links to releases. These are whole-repository snapshots containing documentation and compiled downloads; they do not contain firmware or app development source. Use the explicitly named BIN or updater ZIP above to get the correct file directly.

Read the [installation guide](../docs/INSTALLATION.md), [compatibility notes](../docs/COMPATIBILITY.md) and [disclaimer](../DISCLAIMER.md) before installing.

Use and unchanged sharing of the project's own material are covered by the [Freeware Licence](../LICENSE.md). Keep that licence, the [third-party notices](../THIRD-PARTY-NOTICES.md) and the disclaimer with redistributed copies. Original Akai software and other third-party components retain their own rights and terms. The project's own firmware and app source code will not be published or included in releases.
